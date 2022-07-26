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

| Class : Path        | Valid Equivlence Classes      | Invalid Equivlence Classes    |
| ------------------- | ----------------------------- | ----------------------------- |
| **Root Format**     | 1. is ''                      | 2. Is '/'                     |
|                     |                               | 3. Is './'                    |
| **Subdir Format**   | 4. is in the form '/location' | 5. Is in form '/location/'    |
|                     |                               | 5.5. has spec chars[><:/\|?*] |
| **Subdir Location** | 6. Exists                     | 7. DNE                        |

[See Valid Folder Names](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names)

| Class: JSON Email    | Valid Equivlence Classes | Invalid Equivlence Classes             |
| -------------------- | ------------------------ | -------------------------------------- |
| **JSON Object**      | 1- JSON email Object     | 2 - blank space                        |
|                      |                          | 3 - alphanumeric string                |
|                      |                          | 4 - string with object embedded within |
|                      |                          | 5- no curly braces                     |
|                      |                          | 6 - array                              |
|                      |                          | 7 - float                              |
|                      |                          | 8 - integer                            |
| **Subject**          | 9 - Exists               | 10 - DNE                               |
| **body**             | 11 - Exists              | 12 - DNE                               |
| **toRecipients**     | 13 - Exists              | 14 - DNE                               |
| **from**             | 15 - Exists              | 16 - DNE                               |
| **receivedDateTime** | 17 - Exists              | 18 - DNE                               |
| **hasAttachments**   | 19 - Exists              | 20 - DNE                               |
| **attachments**      | 21 - Exists              | 22 - DNE                               |
|                      | 23 - Is Empty            |
|                      |

## Test Cases

### ID: 0

**Scenario:**
When inputs are:

- root: ''
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 1,8,11,13,16

**Covers Design:** D1
