# File System Operation Examples

## File Processing Patterns

### Batch File Processing
```powershell
# Initialize logging
Variables.CreateNewDatatable InputTable: {
    "Columns": [
        {"Name": "Timestamp", "Type": "DateTime"},
        {"Name": "FileName", "Type": "Text"},
        {"Name": "Status", "Type": "Text"},
        {"Name": "Error", "Type": "Text"}
    ]
} DataTable=> ProcessLog

# Get files to process
Folder.GetFiles 
    Folder: %InputFolder% 
    FileFilter: "*.txt" 
    IncludeSubfolders: True 
    Files=> FilesToProcess

# Process each file
LOOP FOREACH InputFile IN %FilesToProcess%
    BLOCK "Process File"
    ON BLOCK ERROR
        # Log error
        Variables.AddRowToDataTable.AppendRowToDataTable 
            DataTable: %ProcessLog% 
            RowToAdd: {
                "Timestamp": %CurrentDateTime%,
                "FileName": %InputFile%,
                "Status": "Error",
                "Error": %LastError%
            }
        NEXT LOOP
    END
        # Read file
        File.ReadTextFromFile.ReadText 
            File: %InputFile% 
            Encoding: File.TextFileEncoding.UTF8 
            Content=> FileContent
        
        # Process content
        ProcessFileContent 
            Content: %FileContent% 
            ProcessedContent=> ProcessedContent
        
        # Save processed file
        File.WriteText 
            File: Text.Replace(%InputFile%, "\input\", "\output\") 
            Text: %ProcessedContent%
        
        # Log success
        Variables.AddRowToDataTable.AppendRowToDataTable 
            DataTable: %ProcessLog% 
            RowToAdd: {
                "Timestamp": %CurrentDateTime%,
                "FileName": %InputFile%,
                "Status": "Success",
                "Error": ""
            }
    END
END LOOP

# Export processing log
Excel.LaunchExcel.Launch Visible: True Instance=> ExcelInstance
Excel.WriteToExcel.WriteTable 
    Instance: %ExcelInstance% 
    Value: %ProcessLog% 
    StartColumn: "A" 
    StartRow: 1
Excel.SaveExcel.SaveAs 
    Instance: %ExcelInstance% 
    DocumentPath: "ProcessingLog_%CurrentDate%.xlsx"
```

### File Monitoring
```powershell
# Set up monitoring
Variables.SetVariable MonitoringActive: True
Variables.SetVariable CheckInterval: 30  # seconds

# Start monitoring loop
WHILE MonitoringActive
    # Check for new files
    Folder.GetFiles 
        Folder: %WatchFolder% 
        FileFilter: "*.docx" 
        Files=> CurrentFiles
    
    # Process new files
    LOOP FOREACH NewFile IN %CurrentFiles%
        IF NOT List.Contains(%ProcessedFiles%, %NewFile%) THEN
            # Process new file
            ProcessNewDocument File: %NewFile%
            
            # Add to processed list
            List.AddItem List: %ProcessedFiles% Item: %NewFile%
        END
    END LOOP
    
    # Wait before next check
    System.Wait Seconds: %CheckInterval%
END WHILE
```

### File Archiving
```powershell
# Set up archive parameters
Variables.SetVariable ArchiveAge: 30  # days
Variables.SetVariable ArchiveFolder: "C:\Archive"

# Get files to archive
Folder.GetFiles 
    Folder: %SourceFolder% 
    IncludeSubfolders: True 
    Files=> AllFiles

# Process each file
LOOP FOREACH FileToCheck IN %AllFiles%
    # Get file age
    File.GetFileInfo 
        File: %FileToCheck% 
        LastModified=> FileDate
    
    # Check if file should be archived
    IF DateTime.Subtract(%CurrentDateTime%, %FileDate%) > %ArchiveAge% THEN
        # Create archive structure
        Variables.SetVariable ArchivePath: 
            Text.Format("{0}\\{1}\\{2}", 
                       %ArchiveFolder%,
                       DateTime.Format(%FileDate%, "yyyy-MM"),
                       File.GetFileName(%FileToCheck%))
        
        # Move to archive
        File.Move 
            Files: %FileToCheck% 
            Destination: %ArchivePath%
    END
END LOOP
```