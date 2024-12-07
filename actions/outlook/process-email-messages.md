# Process Email Messages in Outlook

## Description
Move or delete an email (or a list of email messages) retrieved by a 'Retrieve emails from Outlook' action.

## Syntax
```
Outlook.ProcessEmailMessages.MoveEmails Instance: `[instance]` Account: `[account]` EmailsToProcess: `[messages]` MailFolder: `[folder]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Outlook instance | Yes | Outlook instance | - | The Outlook instance to work with |
| Account | Yes | Text value | - | Name of the Outlook account |
| Email messages to process | Yes | List of Outlook mail messages | - | Messages to process |
| Operation | Yes | Delete email messages, Move email messages to mail folder, Mark as unread | Move email messages to mail folder | Operation to perform |
| Mail folder | Yes (if moving) | Text value | - | Destination folder path |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to find Outlook account | Account doesn't exist |
| Specified mail-folder doesn't exist | Destination folder invalid |
| Failed to process email messages | Problem processing messages |