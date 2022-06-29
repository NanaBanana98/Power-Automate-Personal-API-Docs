# Utilities
---
## Save Email to PDF
This flow saves an email to a PDF at a given path. The PDF saves as ```FROM_sender@email.com_TO_reciver1@email.com;reciver2@email.com_SENT_dayMonthYear_hourMinute.pdf```
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
Indicates the save location. Do not include a file name and only a pass location. By default, the path is set to ```/```.
If you wish to save to the root **do not** pass any value.
If you wish to provide a new location **do not** end the path with```/```.
Doing either of the above actions will result in an error.

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
