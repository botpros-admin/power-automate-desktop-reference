# Send Email Through Outlook

## Description
Create and send a new email message through Outlook.

## Syntax
```
Outlook.SendEmailThroughOutlook.SendEmail Instance: `[instance]` Account: `[account]` SendTo: `[recipients]` IsBodyHtml: False IsDraft: False
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Outlook instance | Yes | Outlook instance | - | The Outlook instance to work with |
| Account | Yes | Text value | - | Name of the Outlook account to use |
| Send email from | No | Account, Other mailbox | Account | Whether to use account or different mailbox |
| Send from | Yes (if other) | Text value | - | Name of mailbox to send from |
| To | Yes | Text value | - | Recipient email address(es), separated by spaces or semicolons |
| CC | No | Text value | - | CC recipient email address(es) |
| BCC | No | Text value | - | BCC recipient email address(es) |
| Subject | No | Text value | - | Email subject |
| Body | No | Text value | - | Email body content |
| Body is HTML | No | Boolean value | False | Whether body contains HTML |
| Attachment(s) | No | List of Files | - | Files to attach |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to find Outlook account | Account doesn't exist |
| Failed to send email | Problem sending email |
| Attachment not found | Specified attachment missing |