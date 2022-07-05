# Utilities
Flows that are reusable and no similar templates could be found.
Contents:
* [Save Email to PDF](#save-email-to-pdf)
* [Verifiy that Excel Table Exists](#verifiy-that-excel-table-exists)
* [Get Excel Table Columns](#get-excel-table-columns)
* [Ensure Valid Excel Table](#ensure-valid-excel-table)
---
## Save Email to PDF
This flow saves an email to a PDF at a given path. The PDF saves as ```FROM_sender@email.com_TO_reciver1@email.com;reciver2@email.com_SENT_dayMonthYear_hourMinute.pdf```
The PDF includes:
* Recipients
* Sender
* Date Received
* Email Subject
* Email Body
* Any attachments

### Input
##### Email (required)
An email in JSON format. 
Properties must include:
* subject - (string)  email subject
* body - (string) the email message
* toRecipients - (string) who the email was sent to
* from - (string) who the email was sent from
* receivedDateTime - (string) Time email was recived
* hasAttachments - (bool) indicates if attachments exist
* attachments - (array) Files attached to the email
    * contentBytes - (base64 string) Attachment contents
    * If there are no attachments then provide an empty array

Sample Input
```javascript
{
  "receivedDateTime": "2022-06-29T18:03:53+00:00",
  "hasAttachments": true,
  "subject": "Email Subject",
  "body": "<html><head></head><body><p>content</p></body></html>",
  "from": "arianaavdoulos@essexpower.ca",
  "toRecipients": "email@email.ca;email@email.ca",
  "attachments": [
    {
      "contentBytes": "Y29udGVudCBieXRlcw=="
    }
  ]
}
```
If you are using an automatic trigger to get an email, you can pass the entirety of the email to the input as such:
1. **Get the body property**
    a. When a new email arrives (V3) => body 
    b. make sure you are selecting the lowercase 'body' attribute. 'Body' indicates the email body, not the JSON body
2. **Cast the body property to string**
    a. ```string(triggerOutputs()?['body'])```
3. **Pass the casted value to the Email input**
##### Path
Indicates the save location. 
 By default, the path is set to ```/``` *(root)*.

Not following the listed requirements will result in error:
* **Do not** include a file name and only a pass location.
* If you wish to save to the root **do not** pass any value.
* If you wish to provide a new location **do not** end the path with```/```.

Sample Input
```
/powerAutomate/emails/pdf
```

### Output
##### file

The File ID of the created PDF

Sample Output
```javascript
{
  "file": "b!ejnbUIYXZkSV8liQhxO-WJ4Z8TX-OSBAntZBWA7_UNUF_8bx4-_cRrnhasAO8ciG.01LKSRAJ4QU4KHGYGJLREIBSUEMP4TW4CU"
}
```

---

## Verifiy that Excel Table Exists
Checks if an Excel table with a given name exists at a given location. If the location does not exist or a table cannot be found ``` false``` is returned. If the table is found ```true``` is returned. If the table is found, the index of the table in the file is also returned; otherwise the index is set to -1.

### Input
#### File Path
The value is a string that indicates the location of the search.
 By default, the path is set to ```/``` *(root)*.

Not following the listed requirements will result in error:
* **Do not** include a file name and only a pass location.
* If you wish to save to the root **do not** pass any value.
* If you wish to provide a new location **do not** end the path with```/```.

Sample Input
```/location/location2```

### File Name (required)
The name of the file to search.
Do not include extension, only name. 

Sample Input
```filename```

#### Table Name (required)
The value is a string that is used to identify the table.

Sample Input
```Table Name```

### Output
#### Table Exists
It is used to indicate if the table has been found. ```Table Exists``` is set to ```true``` if the table has been found. ```Table Exists``` is set to ```false``` if the table is not found. 
The value is passed through ```Respond to a PowerApp or flow``` so any parent apps will have ready access to the value.

#### Table Index
Indicates the index of the table in the array returned when `Get all Tables in File` is called. If the table is not found then ```-1``` is output

#### Sample Output
```javascript
{
  "table_exists": "False",
  "index": "-1"
}
```

## Get Excel Table Columns
Returns an array of column names in an excel table.

### Inputs
#### File Name (required)
This field is a string representing the file's name where the table is located.
Do not include extension, only name. 

##### Sample Input
```filename```

#### Table Name (required)
A string representing the table's name where the flow will fetch the columns from.
##### Sample Input
```Table Name```

#### File Path
The value is a string that indicates the location of the search.
 The path is,  by default, set to ```/``` *(root)*.

Not following the listed requirements will result in an error:
* **Do not** include a file name and only a pass location.
* If you wish to save to the root **do not** pass any value.
* If you wish to provide a new location **do not** end the path with```/```.

##### Sample Input
```/location/location2```

### Outputs
#### Columns
A stringified array containing the names of the columns in the table. 
##### Sample Output
```javascript
{
  "columns": "[\"@odata.etag\",\"ItemInternalId\",\"Date Posted\",\"Payment Date\",\"Invoice Number\",\"Vendor\",\"Amount\",\"Remittance Number\",\"Attachment\",\"Approved\"]"
}
```

### Error Codes

#### 1 - Path not found
The file Path provided does not map to any existing path. 
#### 2 - File Name not found.
The file Name provided does not match any file at the path location.
#### 3 - Table not found.
The table Name provided does not match an existing table in the file.

## Ensure Valid Excel Table
Checks that an Excel table that matches the given parameters exists. One is created/modified to fit the given parameters if one does not exist. No columns are dropped when changing a table, only added if the columns listed do not exist. 

### Inputs
#### File Name (required)
This field is a string representing the file's name where the table is located.
Do not include extension, only name. 

##### Sample Input
```filename```

#### Table Name (required)
A string representing the table's name where the flow will fetch the columns from.
##### Sample Input
```Table Name```

#### Columns (required)
An array of names of columns that the table MUST include.
##### Sample Input
```['col1', 'col2', 'col3']```

#### File Path
The value is a string that indicates the location of the search.
 The path is,  by default, set to ```/``` *(root)*.

Not following the listed requirements will result in an error:
* **Do not** include a file name and only a pass location.
* If you wish to save to the root **do not** pass any value.
* If you wish to provide a new location **do not** end the path with```/```.

##### Sample Input
```/location/location2```

### Outputs
#### Excel File ID
String. The ID of the file where the table is located. 

#### Sample Output
```javascript
{
  "excel_file_id": "RXhjZWwgRmlsZSBJRA=="
}
```