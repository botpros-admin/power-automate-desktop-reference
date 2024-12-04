# Folder Operations

## Available Actions

### Folder Management
1. [If folder exists](./if-folder-exists.md)
2. [Get files in folder](./get-files-in-folder.md)
3. [Get subfolders in folder](./get-subfolders-in-folder.md)
4. [Create folder](./create-folder.md)
5. [Delete folder](./delete-folder.md)
6. [Empty folder](./empty-folder.md)
7. [Copy folder](./copy-folder.md)
8. [Move folder](./move-folder.md)
9. [Rename folder](./rename-folder.md)
10. [Get special folder](./get-special-folder.md)

## Common Usage Patterns

### Folder Operations with Error Handling
```powershell
BLOCK "Folder Operations"
ON BLOCK ERROR
    System.LogMessage "Error: %LastError%"
    # Handle cleanup
END
    # Main folder operations
END
```

## Best Practices
1. Always check folder existence before operations
2. Use appropriate error handling
3. Clean up temporary folders
4. Handle permissions appropriately
5. Consider path length limitations