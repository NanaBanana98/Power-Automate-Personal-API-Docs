# Test 'Save Email As PDF'

## Analysis

### Cause-Effect Analysis

#### Conditions

- **C1:** Path provided exists
- **C2:** Path provided is in a valid format
- **C3:** Valid JSON Email Object must be passed

#### Effects

- **E1:** Returns status code 0
- **E2:** Returns status code -1
- **E3:** Returns file id for created PDF
- **E4:** Returns empty string

#### Design Table

| Symbol | Description                                  |
| ------ | -------------------------------------------- |
| T      | denotes that conditions met                  |
| F      | indicates that requirements **not** met      |
| X      | means that the program should execute effect |
| \-     | denotes not applicable                       |

| Descion ID     | D1  | D2  | D3  | D4  | D5  | D6  |
| -------------- | --- | --- | --- | --- | --- | --- |
| **Conditions** |     |     |     |     |     |     |
| C1             | T   | T   | F   | F   | F   | F   |
| C2             | T   | T   | T   | T   | F   | F   |
| C3             | T   | F   | T   | F   | T   | F   |
| **Effects**    |     |     |     |     |     |     |
| E1             | X   | -   | -   | -   | -   | -   |
| E2             | -   | X   | X   | X   | X   | X   |
| E3             | X   | -   | -   | -   | -   | -   |
| E4             | -   | X   | X   | X   | X   | X   |

### Equivelence Class Partitioning


| Class: JSON Email      | Valid Equivlence Classes | Invalid Equivlence Classes             |
| -----------------------| ------------------------ | -------------------------------------- |
| **JSON Object**        | 1- JSON email Object     | 2 - blank space                        |
|                        |                          | 3 - alphanumeric string                |
|                        |                          | 4 - string with object embedded within |
|                        |                          | 5- no curly braces                     |
|                        |                          | 6 - array                              |
|                        |                          | 7 - float                              |
|                        |                          | 8 - integer                            |
|                        | 9- has 'subject' prop    |17 - subject prop dne                        
|                        |10 -has 'body' prop       |18-  body prop dne
|                        |11- has 'toRecipients' prop|19- 'toRecipients' prop dne
|                        |12- has 'from' prop       |20- 'from' prop dne
|                        |13- has 'recivedDatetime' |21- 'recivedDatetime' prop dne
|                        |15- has 'attachments' prop|
|                        |16- 'attachments' prop dne|
|**subject Prop**        |23- Empty String          |     
|                        |24- Alphanumeric string   |
|                        |                          |25- Number
|                        |                          |26- Boolean
|                        |                          |27- Array
|                        |                          |28- Float
|                        |                          |29- Object
|**body Prop**           |30- Empty String          |  
|                        |31- Alphanumeric string   |
|                        |                          |32- Number
|                        |                          |33- Boolean
|                        |                          |34- Array
|                        |                          |35- Float
|                        |                          |36- Object
|**toRecipients Prop**   |37- Empty String          |  
|                        |38- Alphanumeric string   |
|                        |                          |39- Number
|                        |                          |40- Boolean
|                        |                          |41- Array
|                        |                          |42- Float
|                        |                          |43- Object
|**from Prop**           |44- Empty String          |  
|                        |45- Alphanumeric string   |
|                        |                          |46- Number
|                        |                          |47- Boolean
|                        |                          |48- Array
|                        |                          |49- Float
|                        |                          |50- Object
|**recivedDatetime Prop**|51- Empty String          |  
|                        |52- Alphanumeric string   |
|                        |                          |53- Number
|                        |                          |54- Boolean
|                        |                          |55- Array
|                        |                          |56- Float
|                        |                          |57- Object
|**attachments Prop**    |58-Array                  |59- Number
|                        |                          |60- Float
|                        |                          |61- String
|                        |                          |62- Object
|**attachments Array**   |63- Empty                 |64- array of numbers
|                        |63.5-array of objects     |65- array of floats
|                        |                          |66- array of booleans
|                        |                          |67- array of strings
|                        |                          |68- array of arrays
|**Array Object**        |69- contains contentBytes |70- Does not contentBytes prop
|                        |85 - contains content type|86- No contentType prop
|**contentBytes**        |71- string                |72-Boolean
|                        |                          |73-Interger
|                        |                          |74-Float
|                        |                          |75-Object
|                        |                          |76-Array
|**contentType**         |87- 'image/png'           |103- 'audio/mpeg'
|                        |88- 'image/avif'
|                        |89- 'image/bmp'
|                        |90- 'image/gif'
|                        |91- 'image/jpeg'
|                        |92- 'image/tiff'
|                        |93- 'image/webp'
|                        |94- 'application/msword'
|                        |95- 'application/vnd.openxmlformats-officedocument.wordprocessingml.document'
|                        |96- 'application/json'
|                        |97- 'application/pdf'
|                        |98- 'application/x-httpd-php'
|                        |99- 'application/vnd.ms-powerpoint'
|                        |100- 'application/vnd.openxmlformats-officedocument.presentationml.presentation'
|                        |101- 'text/html'
|                        |102- 'text/plain'
[Common Content Types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types)


| Class : Path        | Valid Equivlence Classes      | Invalid Equivlence Classes    |
| ------------------- | ----------------------------- | ----------------------------- |
| **Root Format**     | 77. is ''                     | 78. Is '/'                    |
|                     |                               | 79. Is './'                   |
| **Subdir Format**   | 80. is in the form '/location'| 81. Is in form '/location/'   |
|                     |                               | 82. has spec chars[><:/\|?*]  |
| **Subdir Location** | 83. Exists                    | 84. DNE                       |

[See Valid Folder Names](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names)

## Test Cases

### ID: 0

**Scenario:**
When inputs are:
    - path: ''
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 1,9,10,11,12,13,15,23,30,37,44,51,58,63,77, 83

**Covers Design:** D1

### ID: 1

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - attachments DNE

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 1,9,10,11,12,13,16,23,30,37,44,51,80,83

**Covers Design:** D1

### ID: 2

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -all is string
                    -Has object with 'image/png' contentType
                    -Has object with 'image/avif' contentType
                    -Has object with 'image/bmp' contentType
                    -Has object with 'image/gif' contentType
                    -Has object with 'image/jpeg' contentType
                    -Has object with 'image/tiff' contentType
                    -Has object with 'image/webp' contentType
                    -Has object with 'application/msword' contentType
                    -Has object with 'application/vnd.openxmlformats-officedocument.wordprocessingml.document' contentType
                    -Has object with 'application/json' contentType
                    -Has object with 'application/pdf' contentType
                    -Has object with 'application/x-httpd-php' contentType
                    -Has object with 'application/vnd.ms-powerpoint' contentType
                    -Has object with 'application/vnd.openxmlformats-officedocument.presentationml.presentation' contentType
                    -Has object with 'text/html' contentType
                    -Has object with 'text/plain' contentType

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 1,9,10,11,12,13,15,24,31,38,45,52,58,63.5,69,71,80,83,85,87,88,89,90,91,92,93,94,95,96,97,98,99,100,101,102

**Covers Design:** D1

### ID: 3

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is blank space

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 2

**Covers Design:** D2

### ID: 4

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is alphanumeric string 

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 3

**Covers Design:** D2

### ID: 5

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is string with object embedded within

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 4

**Covers Design:** D2

### ID: 6

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object has no curly braces

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 5

**Covers Design:** D2

### ID: 7

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 6

**Covers Design:** D2

### ID: 8

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is float

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 7

**Covers Design:** D2

### ID: 9

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object is integer

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 8

**Covers Design:** D2

### ID: 10

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - No subject prop
            - Has body prop
                - Alphanumeric string
            - Has toRecipients props
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 17

**Covers Design:** D2

### ID: 11

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - No toRecipients prop
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 18

**Covers Design:** D2

### ID: 12

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - No toRecipients prop
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 19

**Covers Design:** D2

### ID: 13

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - No from prop
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 20

**Covers Design:** D2

### ID: 14

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - No recivedDatetime
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 21

**Covers Design:** D2

### ID: 15

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Number
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 25

**Covers Design:** D2#

## ID: 16

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - boolean
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 26

**Covers Design:** D2

### ID: 17

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Array
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 27

**Covers Design:** D2

### ID: 18

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - float
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 28

**Covers Design:** D2

### ID: 19

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Object
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 29

**Covers Design:** D2

### ID: 20

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - integer
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 32

**Covers Design:** D2

### ID: 21

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - boolean
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 33

**Covers Design:** D2

### ID: 22

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Array
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 34

**Covers Design:** D2

### ID: 24

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Float
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 35

**Covers Design:** D2

### ID: 25

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Object
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 36

**Covers Design:** D2

### ID: 26

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - integer
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 39

**Covers Design:** D2

### ID: 27

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - boolean
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 40

**Covers Design:** D2

### ID: 28

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - array
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 41

**Covers Design:** D2

### ID: 29

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - float
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 42

**Covers Design:** D2

### ID: 30

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Object
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 43

**Covers Design:** D2

### ID: 31

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - integer
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 46

**Covers Design:** D2

### ID: 32

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - boolean
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 47

**Covers Design:** D2

### ID: 33

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - array
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 48

**Covers Design:** D2

### ID: 34

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - float
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 49

**Covers Design:** D2

### ID: 35

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Object
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 50

**Covers Design:** D2

### ID: 36

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - integer
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 53

**Covers Design:** D2

### ID: 37

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - boolean
            - Has attachments
                -Empty array


Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 54

**Covers Design:** D2

### ID: 38

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alrray
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 55

**Covers Design:** D2

### ID: 39

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - float
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 56

**Covers Design:** D2

### ID: 40

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Object
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 57

**Covers Design:** D2

### ID: 41

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - integer

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 59

**Covers Design:** D2

### ID: 42

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - float

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 60

**Covers Design:** D2

### ID: 43

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - string

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 61

**Covers Design:** D2

### ID: 44

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Is object

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 62

**Covers Design:** D2

### ID: 45

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of integers

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 64

**Covers Design:** D2

### ID: 46

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of floats

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 65

**Covers Design:** D2

### ID: 47

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of booleans

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 66

**Covers Design:** D2

### ID: 48

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of strings

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 67

**Covers Design:** D2

### ID: 49

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of arrays

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 68

**Covers Design:** D2

### ID: 50

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has no contentBytes prop

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 70

**Covers Design:** D2

### ID: 63

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentType prop
                        - Is invalid value ie: audio/mpeg

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 103

**Covers Design:** D2

### ID: 51

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is boolean

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 72

**Covers Design:** D2

### ID: 52

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is integer

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 73

**Covers Design:** D2

### ID: 53

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is float

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 74

**Covers Design:** D2

### ID: 54

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is Object

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 75

**Covers Design:** D2

### ID: 55

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 76

**Covers Design:** D2

### ID: 64

**Scenario:**
When inputs are:
    - path: in format '/location'
    - JSON Object
        - Email Object
            - Has subject prop
                - Alphanumeric string
            - Has body prop
                - Alphanumeric string
            - Has toRecipients prop
                - Alphanumeric string
            - Has from prop
                - Alphanumeric string
            - Has recivedDatetime
                - Alphanumeric string
            - Has attachments
                - Array of object
                    - Has contentBytes prop
                        -Is array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 76

**Covers Design:** D2

### ID: 56

**Scenario:**
When inputs are:
    - path: in format '/location' and does not map to existing location
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - attachments DNE

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 84

**Covers Design:** D3

### ID: 57

**Scenario:**
When inputs are:
    - path: in format '/location' and does not map to existing location
    - JSON Object
        - Email Object
            - No subject prop
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - attachments DNE

Then return the columns of that table with status code 0

**Covers Design:** D4

### ID: 58

**Scenario:**
When inputs are:
    - path: '/'
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 78

**Covers Design:** D5

### ID: 59

**Scenario:**
When inputs are:
    - path: './'
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 79

**Covers Design:** D5

### ID: 60

**Scenario:**
When inputs are:
    - path: '/location/'
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 81

**Covers Design:** D5

### ID: 61

**Scenario:**
When inputs are:
    - path has spec chars[><:/\|?*]
    - JSON Object
        - Email Object
            - Has subject prop
                - Empty string
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 82

**Covers Design:** D5

### ID: 62

**Scenario:**
When inputs are:
    - path has spec chars[><:/\|?*]
    - JSON Object
        - Email Object
            - Has no subject prop
            - Has body prop
                - Empty string
            - Has toRecipients prop
                - Empty string
            - Has from prop
                - Empty string
            - Has recivedDatetime
                - Empty string
            - Has attachments
                -Empty array

Then return the columns of that table with status code 0

**Covers Design:** D6
