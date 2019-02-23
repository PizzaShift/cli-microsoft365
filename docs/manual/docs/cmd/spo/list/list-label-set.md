# spo list label set

Sets classification label on the specified list

## Usage

```sh
spo list label set  [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`-u, --webUrl <webUrl>`|The URL of the site where the list is located
`--label <label>`|The label to set on the list
`-t, --listTitle [listTitle]`|The title of the list on which to set the label. Specify only one of `listTitle`, `listId` or `listUrl`
`-l, --listId [listId]`|The ID of the list on which to set the label. Specify only one of `listTitle`, `listId` or `listUrl`
`--listUrl [listUrl]`|Server- or web-relative URL of the list on which to set the label. Specify only one of `listTitle`, `listId` or `listUrl`
`--syncToItems`|Specify, to set the label on all items in the list
`--blockDelete`|Specify, to disallow deleting items in the list
`--blockEdit`|Specify, to disallow editing items in the list
`-o, --output [output]`|Output type. `json|text`. Default `text`
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

!!! important
    Before using this command, log in to a SharePoint Online site, using the [spo login](../login.md) command.

## Remarks

To set a list classification label, you have to first log in to SharePoint using the [spo login](../login.md) command, eg. `spo login https://contoso.sharepoint.com`.

## Examples

Sets classification label "Confidential" for list _Shared Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
spo list label set --webUrl https://contoso.sharepoint.com/sites/project-x --listUrl 'Shared Documents' --label 'Confidential'
```

Sets classification label "Confidential" and disables editing and deleting items on the list and all existing items for list for list _Documents_ located in site _https://contoso.sharepoint.com/sites/project-x_

```sh
spo list label set --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle 'Documents' --label 'Confidential' --blockEdit --blockDelete --syncToItems
```