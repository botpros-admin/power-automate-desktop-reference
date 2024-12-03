# Active Directory Actions

## Available Actions

### Group Management
1. [Create group](./create-group.md)
2. [Get group info](./get-group-info.md)
3. [Get group members](./get-group-members.md)
4. [Modify group](./modify-group.md)

### Object Management
1. [Create object](./create-object.md)
2. [Delete object](./delete-object.md)
3. [Move object](./move-object.md)
4. [Rename object](./rename-object.md)

### User Management
1. [Create user](./create-user.md)
2. [Get user info](./get-user-info.md)
3. [Modify user](./modify-user.md)
4. [Unlock user](./unlock-user.md)
5. [Update user info](./update-user-info.md)

### Connection Management
1. [Connect to server](./connect-to-server.md)
2. [Close connection](./close-connection.md)

## Usage Examples

```powershell
# Example: Creating a new AD group
ActiveDirectory.ConnectToServer.ConnectToServer LdapPath: "LDAP://DC=example,DC=com" ParentDirectoryEntry=> PDEntry

ActiveDirectory.CreateGroup ParentDirectoryEntry: %PDEntry% GroupName: "TestGroup" Location: "OU=Groups,DC=example,DC=com" GroupScope: ActiveDirectory.GroupScope.GlobalScope GroupType: ActiveDirectory.GroupType.Security
```