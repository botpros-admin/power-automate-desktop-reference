# Retrieve Email Messages

## Description
Retrieve email messages from an Outlook account.

## Syntax
```
Outlook.RetrieveEmailMessages.RetrieveEmails Instance: `[instance]` Account: `[account]` MailFolder: `[folder]` EmailsToRetrieve: Outlook.RetrieveMessagesMode.All MarkAsRead: True ReadBodyAsHtml: False Messages=> RetrievedEmails
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Outlook instance | Yes | Outlook instance | - | The Outlook instance to work with |
| Account | Yes | Text value | - | Name of the Outlook account (data file name) |
| Mail folder | Yes | Text value | - | Name of folder to retrieve messages from. Use full path for subfolders (e.g., Inbox\Work) |
| Retrieve | No | All email messages, Unread email messages only, Read email messages only | All email messages | Which messages to retrieve |
| Mark as read | No | Boolean value | True | Whether to mark unread messages as read |
| From contains | No | Text value | - | Filter by sender email address |
| To contains | No | Text value | - | Filter by recipient email address(es) |
| Subject contains | No | Text value | - | Filter by subject text |
| Body contains | No | Text value | - | Filter by body content |
| Attachments | No | Save attachments, Don't save attachments | Don't save attachments | Whether to save message attachments |
| Save attachments into | Yes (if saving) | Folder | - | Path to save attachments |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| RetrievedEmails | List of Outlook mail messages | Retrieved email messages for processing |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to find Outlook account | Specified account doesn't exist |
| Mail-folder specified not valid | Specified folder is invalid |
| Directory for saving attachments not found | Attachment save directory doesn't exist |
| Failed to retrieve email messages | Problem retrieving messages |