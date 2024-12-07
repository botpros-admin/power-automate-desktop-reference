# Respond to Outlook Mail Message

## Description
Respond to an Outlook message, by replying, replying to all or forwarding it.

## Syntax
```
Outlook.RespondToMailMessage.ReplyToEmail Instance: `[instance]` Account: `[account]` MailMessage: `[message]` Body: $'''[body]'''
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Outlook instance | Yes | Outlook instance | - | The Outlook instance to work with |
| Account | Yes | Text value | - | Name of the Outlook account |
| Mail message | Yes | Outlook mail message | - | Message to respond to |
| Response action | Yes | Reply, Reply all, Forward | Reply | Type of response |
| To | Yes | Text value | - | Recipient email address(es) |
| CC | No | Text value | - | CC recipient email address(es) |
| BCC | No | Text value | - | BCC recipient email address(es) |
| Body | No | Text value | - | Response content |
| Attachment(s) | No | List of Files | - | Files to attach |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to find Outlook account | Account doesn't exist |
| Failed to send email | Problem sending response |
| Attachment not found | Attachment missing |