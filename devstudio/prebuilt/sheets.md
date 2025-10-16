---
title: "Google Sheets Integration"
description: "Read and write rows in Google Sheets."
---

## Parameters

<ParamField body="spreadsheetId" type="string" required>Spreadsheet ID</ParamField>
<ParamField body="range" type="string" required>A1 notation range</ParamField>
<ParamField body="values" type="array">Values to write</ParamField>

## Example

<RequestExample>
```json Tool Input
{
  "spreadsheetId": "sheet_123",
  "range": "Sheet1!A1:C1",
  "values": [["A","B","C"]]
}
```
</RequestExample>

<ResponseExample>
```json Success
{ "updated": 1 }
```
</ResponseExample>
