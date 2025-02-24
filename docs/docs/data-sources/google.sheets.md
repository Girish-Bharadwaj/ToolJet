---
sidebar_position: 8
---

# Google Sheets

ToolJet can connect to Google Sheet using OAuth 2.0, which helps us to limit an application's access to a user's account.

## Authorization Scopes 

You can create a Google Sheets datasource with one of either of the two permission scopes :
  1. **Read Only**
  2. **Read and Write**

<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/googlesheets.gif)

</div>

## Operations

Using Google sheets data source you can perfom several operations from your applications like:

  1. **[Read data from a sheet](/docs/data-sources/google.sheets#read-data-from-a-sheet)**
  2. **[Append data to a sheet](/docs/data-sources/google.sheets#append-data-to-a-sheet)**
  3. **[Update single row of a sheet](/docs/data-sources/google.sheets#update-single-row-of-a-sheet)**
  4. **[Delete row from a sheet](/docs/data-sources/google.sheets#delete-row-from-a-sheet)**
  5. **[Get spreadsheet info](/docs/data-sources/google.sheets#get-spreadsheet-info)**

### Read data from a sheet

This operation returns the table data from the spreadsheet in the form of json object. 

| Fields      | description |
| ----------- | ----------- |
| Spreadsheet ID | It is mandatory to enter the spreadsheet-id. The spreadsheet-id can be found in the URL of the spreadsheet. Example URL: https://docs.google.com/spreadsheets/d/1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM/edit#gid=0 - in this URL, the `1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM` is the spreadsheet-id. |
| Range | This is optional. You can specify the range of cells in this field. If left empty, it will select the range `A1:Z500`. |
| Sheet | This is optional. You can specify `sheet name` if it has more than 1 sheets, else it will automatically choose the first sheet. |


<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/read-data-op.png)

</div>

### Append data to a sheet

You can add more rows to the table using the append operation.

| Fields      | description |
| ----------- | ----------- |
| Spreadsheet ID | It is mandatory to enter the spreadsheet-id. The spreadsheet-id can be found in the URL of the spreadsheet. Example URL: https://docs.google.com/spreadsheets/d/1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM/edit#gid=0 - in this URL, the `1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM` is the spreadsheet-id. |
| Sheet | This is optional. You can specify `sheet name` if it has more than 1 sheets, else it will automatically choose the first sheet. |
| Rows  | Enter the row data in the json array form. Each object in an array will represent a single row. Example: `[ {"name":"John", "email":"John@tooljet.com"},{...},{...} ]` In each object, the `key` represents the **column name** and the `value` represents the **cell data**.   |

<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/append-data-op.png)

</div>

### Update single row of a sheet

You can update the existing data in sheet using this operation.

| Fields      | description |
| ----------- | ----------- |
| Spreadsheet ID | It is mandatory to enter the spreadsheet-id. The spreadsheet-id can be found in the URL of the spreadsheet. Example URL: https://docs.google.com/spreadsheets/d/1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM/edit#gid=0 - in this URL, the `1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM` is the spreadsheet-id. |
| Where | Enter the column name such as `id` for choosing a row. |
| Operator | Choose the `===` operator to check the equality. |
| Value | Enter the any `id` number/name that you want to update. |
| Rows  | Enter the row data. Example: `{{({id: components.textinput4.value, company: components.textinput1.value, position: components.textinput2.value, url: components.textinput3.value, 'date-applied': components.datepicker1.value, status: components.dropdown1.value})}}`  |

<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/update-data-op.png)

</div>

### Delete row from a sheet

Use this operation delete a specific row from the sheet.

| Fields      | description |
| ----------- | ----------- |
| Spreadsheet ID | It is mandatory to enter the spreadsheet-id. The spreadsheet-id can be found in the URL of the spreadsheet. Example URL: https://docs.google.com/spreadsheets/d/1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM/edit#gid=0 - in this URL, the `1W2S4re7zNaPk9vqv6_CqOpPdm_mDEqmLmzjVe7Nb9WM` is the spreadsheet-id. |
| GID | You'll find the GID in the end of the URL of spreadsheet. In the example mentioned above, the GID is 0 |
| Delete row number |  Just enter the row number that you want to delete.  |


<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/delete-row-op.png)

</div>

### Get spreadsheet info

This operation can be used to get some basic information of the spreadsheet such as the number of sheets, theme, time-zone, format, and url etc.

Here is the `Preview` of the query that used the get spreadsheet info operation.

<div style={{textAlign: 'center'}}>

![ToolJet - ToolJet - Datasource Google Sheets](/img/datasource-reference/google-sheets/get-info2.png)

</div>