# Save Outlook Email Messages

## Description
Save Outlook email messages given an account.

## Syntax
```
Outlook.SaveOutlookEmailMessages.SaveEmails Instance: `[instance]` Account: `[account]` EmailsToSave: `[messages]` SaveFormat: Outlook.MessageType.OutlookMessageFormatUnicode SaveEmailsTo: `[folder]` MessagesFiles=> StoredMessagesFiles
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Outlook instance | Yes | Outlook instance | - | The Outlook instance to work with |
| Account | Yes | Text value | - | Name of the Outlook account |
| Email message(s) to save | Yes | List of Outlook mail messages | - | Messages to save |
| Save format | Yes | Text only (.txt), Outlook template (.oft), Outlook message format (.msg), Outlook message format - Unicode (.msg), HTML (.html), MHT files (.mht) | Outlook message format (.msg) | Format for saving |
| File name | Yes | Default, Custom | Default | Use default (subject) or custom name |
| Save as | Yes (if custom) | Text value | - | Custom filename pattern |
| Save email message(s) to | Yes | Folder | - | Destination folder |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| StoredMessagesFiles | List of Text values | File paths of saved messages |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to find Outlook account | Account doesn't exist |
| Directory not found | Save directory missing |
| Email message is deleted or moved | Message no longer available |
| Failed to save email message(s) | Problem saving messages |