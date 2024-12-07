# Remove Item from List

## Description
Remove one or multiple items from a list.

## Syntax
```
Variables.RemoveItemFromList.RemoveItemFromListByIndex ItemIndex: `[index]` List: `[list]`
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Remove item by | Yes | Index, Value | Index | Remove by index or value |
| At index | Yes (if by index) | Numeric value | - | Index of item to remove |
| With value | Yes (if by value) | General value | - | Item to remove |
| Remove all item occurrences | No | Boolean value | False | Remove all matching occurrences |
| From list | Yes | List of General values | - | The list with items to remove |

## Output Variables
This action doesn't produce any variables.

## Exceptions

| Exception | Description |
|-----------|-------------|
| Item index is out of range | Indicates that item index is out of range |
| Item not found | Indicates that item doesn't exist in the list |