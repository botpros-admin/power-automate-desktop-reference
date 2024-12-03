# Create Group Action

## Description
Creates a group in the Active Directory.

## Syntax
```
ActiveDirectory.CreateGroup ParentDirectoryEntry: `` GroupName: `` Location: $'''''' GroupScope: ActiveDirectory.GroupScope.GlobalScope GroupType: ActiveDirectory.GroupType.Security
```

## Parameters
- ParentDirectoryEntry (Required): The parent entry of the Active Directory server
- GroupName (Required): The name of the newly created group
- Location (Optional): The location that the group will be created in
- GroupScope: Local, Global, Universal (Default: Global)
- GroupType: Security, Distribution (Default: Security)

## Exceptions
- Authentication error
- Invalid operation
- The server isn't operational
- Unauthorized access
- Active Directory entry not found
- Object already exists