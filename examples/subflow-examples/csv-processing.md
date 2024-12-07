# CSV Processing Example

## Description
Demonstrates CSV file processing using both VB.NET and PowerShell scripts, including:
- Reading CSV files
- Adding new columns
- Processing data
- Writing modified data back to files

## Code

```
**REGION Read Initial CSV
# Read the CSV file with UTF-8 encoding
File.ReadFromCSVFile.ReadCSV CSVFile: $'''%filePath%\Temp\ContactOutput.csv''' \
    Encoding: File.CSVEncoding.UTF8 \
    TrimFields: True \
    FirstLineContainsColumnNames: True \
    ColumnsSeparator: File.CSVColumnsSeparator.SystemDefault \
    CSVTable=> CSVTable
**ENDREGION

**REGION Process CSV with VB.NET
# Process the CSV using VB.NET for robust data handling
Scripting.RunDotNetScript Language: System.DotNetActionLanguageType.VisualBasic Script: $'''
' Validate input
If ImpCSV Is Nothing Then
    Throw New Exception("ImpCSV DataTable is missing.")
End If

' Validate required columns
If Not ImpCSV.Columns.Contains("Client Name") Then
    Throw New Exception("Column 'Client Name' not found in ImpCSV.")
End If
If Not ImpCSV.Columns.Contains("Primary Bill To") Then
    Throw New Exception("Column 'Primary Bill To' not found in ImpCSV.")
End If

' Ensure "Completed" column exists
If Not ImpCSV.Columns.Contains("Completed") Then
    ImpCSV.Columns.Add("Completed", GetType(String))
End If

' Create a list to store the output rows
Dim result As New List(Of String)()

' Add headers
Dim headers As String = String.Join(",", ImpCSV.Columns.Cast(Of DataColumn).Select(Function(col) col.ColumnName))
result.Add(headers)

' Process each row
For Each row As DataRow In ImpCSV.Rows
    Dim clientName As String = row("Client Name").ToString().Trim()
    If Not String.Equals(clientName, "Match Not Found", StringComparison.OrdinalIgnoreCase) Then
        ' Mark as completed
        row("Completed") = "X"
    End If

    ' Prepare the row for output
    Dim rowValues As IEnumerable(Of String) = row.ItemArray.Select(Function(item) """" & item.ToString().Replace("""", """""") & """")
    Dim outputRow As String = String.Join(",", rowValues)
    result.Add(outputRow)
Next

' Combine results into the output string
ScriptOutput = String.Join(Environment.NewLine, result)
''' \
    @'name:ImpCSV': CSVTable @'type:ImpCSV': $'''Datatable''' @'direction:ImpCSV': $'''InOut''' \
    @'name:ScriptOutput': $'''''' @'type:ScriptOutput': $'''String''' @'direction:ScriptOutput': $'''Out''' \
    @ImpCSV=> CSVTable @ScriptOutput=> Result
**ENDREGION

**REGION Alternative PowerShell Processing (Disabled)
# Alternative PowerShell approach (currently disabled)
DISABLE Scripting.RunPowershellScript.RunPowershellScript Script: $'''
# Input variable: %CSVTable% (string containing your CSV data)
# Output variable: $CSVTable (string containing the updated CSV data)

# Convert CSV data into objects
$csv = ConvertFrom-Csv -InputObject $InputCsvData

# Check if "Completed" column exists
if (-not ($csv | Get-Member -Name 'Completed' -ErrorAction SilentlyContinue)) {
    $csv = $csv | Select-Object *, @{Name='Completed';Expression={''}}
}

# Process each row
foreach ($row in $csv) {
    if ($row.'Client Name' -ne 'Match Not Found') {
        # Extract "Primary Bill To" value
        $primaryBillTo = $row.'Primary Bill To'
        # Mark as completed
        $row.Completed = 'X'
    }
}

# Convert objects back to CSV
$UpdatedCsvData = $csv | ConvertTo-Csv -NoTypeInformation | Out-String
$UpdatedCsvData = $UpdatedCsvData.Trim()
''' ScriptOutput=> PowershellOutput
**ENDREGION

**REGION Save Results
# Write processed data back to file
File.WriteText File: $'''%filePath%\Temp\ContactOutput2.csv''' \
    TextToWrite: CSVTable \
    AppendNewLine: True \
    IfFileExists: File.IfFileExists.Overwrite \
    Encoding: File.FileEncoding.UTF8

# Show processing results
Display.ShowMessageDialog.ShowMessage Message: PowershellOutput \
    Icon: Display.Icon.None \
    Buttons: Display.Buttons.OK \
    DefaultButton: Display.DefaultButton.Button1 \
    IsTopMost: False
**ENDREGION
```

## Key Features

1. **Input Validation**
   - Checks for missing DataTable
   - Validates required columns
   - Handles missing columns gracefully

2. **Data Processing**
   - Adds new columns as needed
   - Processes rows based on conditions
   - Handles escaping of special characters

3. **Error Handling**
   - Proper exception throwing
   - Column existence checks
   - Data type validation

4. **Best Practices**
   - Uses UTF-8 encoding
   - Proper CSV formatting
   - Clean file handling

## Notes
- Shows both VB.NET and PowerShell approaches
- Demonstrates region-based organization
- Includes commented code alternatives