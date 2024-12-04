# UI Automation - Form Handling Examples

## Data Entry Automation

### Excel to Form Entry
```powershell
# Initialize variables
Variables.CreateNewDatatable InputTable: { } DataTable=> ErrorLog

# Read source data
Excel.ReadFromExcel.ReadRange 
    Instance: %ExcelInstance% 
    StartColumn: "A" 
    StartRow: 2 
    EndColumn: "D" 
    EndRow: -1 
    ReadAsText: False 
    ExcelData=> SourceData

# Process each record
LOOP FOREACH Record IN %SourceData%
    BLOCK "Process Record"
    ON BLOCK ERROR
        # Log error
        Variables.AddRowToDataTable.AppendRowToDataTable 
            DataTable: %ErrorLog% 
            RowToAdd: {
                "RecordID": %Record.ID%,
                "Error": %LastError%,
                "Timestamp": %CurrentDateTime%
            }
        NEXT LOOP
    END
        # Fill form fields
        UIAutomation.PopulateTextField.PopulateTextField 
            TextField: %NameField% 
            Text: %Record.Name% 
            Mode: UIAutomation.PopulateTextMode.Replace
        
        UIAutomation.PopulateTextField.PopulateTextField 
            TextField: %EmailField% 
            Text: %Record.Email% 
            Mode: UIAutomation.PopulateTextMode.Replace
        
        # Handle dropdowns
        UIAutomation.SetDropDownListValue.SelectOptionByName 
            DropDownList: %StatusDropdown% 
            OptionName: %Record.Status%
        
        # Click save
        UIAutomation.Click.Click 
            Element: %SaveButton% 
            ClickType: UIAutomation.ClickType.LeftClick
        
        # Wait for confirmation
        UIAutomation.WaitForElement 
            Element: %ConfirmationMessage% 
            Timeout: 10
        
        # Clear form for next entry
        UIAutomation.Click.Click 
            Element: %NewButton% 
            ClickType: UIAutomation.ClickType.LeftClick
    END
END LOOP

# Export error log if any errors occurred
IF DataTable.RowCount(%ErrorLog%) > 0 THEN
    Excel.WriteToExcel.WriteTable 
        Instance: %ExcelInstance% 
        Value: %ErrorLog% 
        StartColumn: "A" 
        StartRow: 1
    
    Excel.SaveExcel.SaveAs 
        Instance: %ExcelInstance% 
        DocumentPath: "ErrorLog_%CurrentDate%.xlsx"
END
```

### Form Validation
```powershell
# Custom form validation function
SUBFLOW "ValidateFormFields"
INPUT FormData
OUTPUT IsValid, ErrorMessages
    # Initialize validation
    Variables.SetVariable IsValid: True
    Variables.SetVariable ErrorMessages: []
    
    # Required field checks
    IF Text.IsNullOrEmpty(%FormData.Name%) THEN
        Variables.SetVariable IsValid: False
        List.AddItem List: %ErrorMessages% Item: "Name is required"
    END
    
    # Email format validation
    IF NOT Text.Contains(%FormData.Email%, "@") THEN
        Variables.SetVariable IsValid: False
        List.AddItem List: %ErrorMessages% Item: "Invalid email format"
    END
    
    # Date validation
    IF DateTime.Parse(%FormData.Date%) > %CurrentDateTime% THEN
        Variables.SetVariable IsValid: False
        List.AddItem List: %ErrorMessages% Item: "Date cannot be in future"
    END
END SUBFLOW
```