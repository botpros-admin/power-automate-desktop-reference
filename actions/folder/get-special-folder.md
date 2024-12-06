# Get Special Folder

## Description
Retrieve the path of a Windows' special folder (such as Desktop, My Pictures, Internet Cache etc.).

## Syntax
```
Folder.GetSpecialFolder SpecialFolder: Folder.SpecialFolder.DesktopDirectory SpecialFolderPath=> SpecialFolderPath
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Special folder name | Yes | Programs, Personal, Favorites, Startup, Recent, Send To, Start Menu, Music, Desktop, Templates, Application Data, Local Application Data, Internet Cache, Cookies, History, Common Application Data, System, Program Files, Pictures, Common Program Files | Desktop | Choose the name of the special folder (like My Documents or Desktop). This option is independent of path, to find the special folder on any computer regardless of path specifics |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| SpecialFolderPath | Folder | The special folder object (which is a representation and can access the folder and all its information) |

## Exceptions
This action doesn't include any exceptions.