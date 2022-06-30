#Utilities
Flows that are reusable and no similar templates could be found.
Contents:
* [Save Email to PDF](#save-email-to-pdf)
* [Verifiy that Excel Table Exists](#verifiy-that-excel-table-exists)
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
Checks if an Excel table with a given name exists at a given location. If the location does not exist or a table cannot be found ``` false``` is returned. If the table is found ```true``` is returned.

### Input
#### File Path (required)
The value is a string that indicates the location of the search.
Do not end path with a ```/```

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

Sample Output
```javascript
{
  "table_exists": "False"
}
```