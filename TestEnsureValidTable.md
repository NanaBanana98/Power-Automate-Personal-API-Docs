# Test 'Ensure Valid Excel Table'

[Docs for Ensure Valid Excel Table](utilities.MD)

## Contents

- [Analysis](#analysis)
  - [Cause-Effect Analysis](#cause-effect-analysis)
    - [Conditions](#conditions)
    - [Effects](#effects)
    - [Table](#table)
  - [Equivelence Class Partitioning](#equivelence-class-partitioning)
- [Test Cases](#test-cases)
  - [Test Case 0](#id-0)
  - [Test Case 1](#id-1)
  - [Test Case 2](#id-2)
  - [Test Case 3](#id-3)
  - [Test Case 4](#id-4)
  - [Test Case 5](#id-5)
  - [Test Case 6](#id-6)
  - [Test Case 7](#id-7)
  - [Test Case 8](#id-8)
  - [Test Case 9](#id-9)
  - [Test Case 10](#id-10)
  - [Test Case 11](#id-11)
  - [Test Case 12](#id-12)
  - [Test Case 13](#id-13)
  - [Test Case 14](#id-14)
  - [Test Case 15](#id-15)
  - [Test Case 16](#id-16)
  - [Test Case 17](#id-17)
  - [Test Case 18](#id-18)
  - [Test Case 19](#id-19)
  - [Test Case 20](#id-20)
  - [Test Case 21](#id-21)
  - [Test Case 22](#id-22)
  - [Test Case 23](#id-23)
  - [Test Case 24](#id-24)
  - [Test Case 25](#id-25)
  - [Test Case 26](#id-26)
  - [Test Case 27](#id-27)
  - [Test Case 28](#id-28)
  - [Test Case 29](#id-29)
  - [Test Case 30](#id-30)
  - [Test Case 31](#id-31)
  - [Test Case 32](#id-32)
  - [Test Case 33](#id-33)
  - [Test Case 34](#id-34)
  - [Test Case 35](#id-35)
  - [Test Case 36](#id-36)
  - [Test Case 37](#id-37)
  - [Test Case 38](#id-38)
  - [Test Case 39](#id-39)
  - [Test Case 40](#id-40)
  - [Test Case 41](#id-41)
  - [Test Case 42](#id-42)
  - [Test Case 43](#id-43)
  - [Test Case 44](#id-44)
  - [Test Case 45](#id-45)
  - [Test Case 46](#id-46)
  - [Test Case 47](#id-47)
  - [Test Case 48](#id-48)
  - [Test Case 49](#id-49)
  - [Test Case 50](#id-50)
  - [Test Case 51](#id-51)
  - [Test Case 52](#id-52)
  - [Test Case 53](#id-53)
  - [Test Case 54](#id-54)
  - [Test Case 55](#id-55)
  - [Test Case 56](#id-56)
  - [Test Case 57](#id-57)
  - [Test Case 58](#id-58)
  - [Test Case 59](#id-59)
  - [Test Case 60](#id-60)
  - [Test Case 61](#id-61)
  - [Test Case 62](#id-62)
  - [Test Case 63](#id-63)
  - [Test Case 64](#id-64)
  - [Test Case 65](#id-65)
  - [Test Case 66](#id-66)
  - [Test Case 67](#id-67)
  - [Test Case 68](#id-68)
  - [Test Case 69](#id-69)
  - [Test Case 70](#id-70)
  - [Test Case 71](#id-71)
  - [Test Case 72](#id-72)
  - [Test Case 73](#id-73)
  - [Test Case 74](#id-74)
  - [Test Case 75](#id-75)
  - [Test Case 76](#id-76)
  - [Test Case 77](#id-77)
  - [Test Case 78](#id-78)
  - [Test Case 79](#id-79)
  - [Test Case 80](#id-80)
  - [Test Case 81](#id-81)
  - [Test Case 82](#id-82)
  - [Test Case 83](#id-83)

## Analysis

### Cause-Effect Analysis

#### Conditions

**C0:** Path provided exists

**C1:** Path provided is in a valid format

**C2:** File name provided exists

**C3:** File name provided is in a valid format

**C4:** Table name provided exists

**C5:** Table name provided is a valid table name

**C6:** Valid JSON string Array Passed

**C7:** Columns passed exists in table

#### Effects

**E0:** Returns status code 0

**E1:** Returns status code 1

**E2:** Returns status code 2

**E3:** Returns status code 3

**E4:** Returns status code 4

**E5:** Create Folder

**E6:** Create File

**E7:** Create Table

**E8:** Create columns

**E9:** Returns file id of where table is located

**E10:** Returns an empty string

#### Table

| Symbol | Description                                  |
| ------ | -------------------------------------------- |
| T      | denotes that conditions met                  |
| F      | indicates that requirements **not** met      |
| X      | means that the program should execute effect |
| \-     | denotes not applicable                       |

| Descion ID     | D1  | D2  | D3  | D4  | D5  | D6  | D7  | D8  | D9  | D10 | D11 | D12 | D13 | D14 | D15 | D16 | D17 | D18 | D19 | D20 | D21 | D22 | D23 | D24 | D25 | D26 | D27 | D28 | D29 | D30 | D31 | D32 | D33 | D34 | D35 | D36 | D37 | D38 | D39 | D40 | D41 | D42 | D43 | D44 | D45 | D46 | D47 | D48 | D49 | D50 | D51 | D52 | D53 | D54 | D55 | D56 | D57 | D58 | D59 |
| -------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Conditions** |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| C0             | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   |
| C1             | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   |
| C2             | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   |
| C3             | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | T   | T   |
| C4             | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   |
| C5             | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   |
| C6             | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   |
| C7             | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   |
| **Effects**    |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| E0             | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   |
| E1             | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   |
| E2             | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| E3             | -   | -   | -   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   |
| E4             | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   |
| E5             | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   |
| E6             | -   | -   | -   | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | X   | X   |
| E7             | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | X   | -   | -   |
| E8             | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | -   | -   | -   |
| E9             | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   |
| E10            | -   | -   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | -   | -   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | -   | -   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | -   | -   | X   | X   | X   |

### Equivelence Class Partitioning

| Class : Path        | Valid Equivlence Classes      | Invalid Equivlence Classes    |
| ------------------- | ----------------------------- | ----------------------------- |
| **Root Format**     | 1. is ''                      | 2. Is '/'                     |
|                     |                               | 3. Is './'                    |
| **Subdir Format**   | 4. is in the form '/location' | 5. Is in form '/location/'    |
|                     |                               | 5.5. has spec chars[><:/\|?*] |
| **Subdir Location** | 6. Exists                     | 7. DNE                        |

[See Valid Folder Names](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names)

| Class: Filename | Valid Equivlence Classes | Invalid Equivlence Classes       |
| --------------- | ------------------------ | -------------------------------- |
| **Format**      | 8. In format 'name'      | 9. Includes extension            |
|                 |                          | 10. Includes reserved characters |
| **Location**    | 11. Exists               | 12. DNE                          |

[See Valid File Name](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names)

| Class: Tablename | Valid Equivlence Classes      | Invalid Equivlence Classes         |
| ---------------- | ----------------------------- | ---------------------------------- |
| **Format**       | 13. includes only [A-Za-z_]   | 15. includes [*] without backticks |
|                  | 14. include \* with backticks |                                    |
| **Exists**       | 16. True                      | 17. False                          |

[See Valid Table Name](https://docs.microsoft.com/en-us/sql/odbc/microsoft/table-name-limitations?view=sql-server-ver16)

| Class: Columns     | Valid Equivlence Classes      | Invalid Equivlence Classes         |
| ------------------ | ----------------------------- | ---------------------------------- |
| **JSON Str Array** | 18. Empty Array               | 19. Blank Space                    |
|                    |                               | 20. JSON Object                    |
|                    |                               | 21. Number                         |
|                    |                               | 22. Boolean                        |
|                    |                               | 23. Float                          |
|                    |                               | 24. Non-Empty String               |
| **Array Contains** | 25. Strings                   | 26. JSON Objects                   |
|                    |                               | 27. Numbers                        |
|                    |                               | 28. Floats                         |
|                    |                               | 29. Booleans                       |
| **String**         | 30. Includes only [A-Za-z_]   | 32. Includes [*] without backticks |
|                    | 31. Include \* with backticks |                                    |

[See Valid Column Names](https://docs.microsoft.com/en-us/sql/odbc/microsoft/column-name-limitations?view=sql-server-ver16)

## Test Cases

### ID: 0

**Scenario:**
When inputs are:

- root: ''
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an empty array

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,13,16, 18
**Covers Design:** D1

### ID: 1

**Scenario:**
When inputs are:

- root: ""
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an empty array

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,14,16, 18
**Covers Design:** D1

### ID: 2

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an empty array

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,13,16,18
**Covers Design:** D1

### ID: 3

**Scenario:**
When inputs are

- Path in the format '/location' and exists.
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an empty array

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,14,16,18
**Covers Design:** D1

### ID: 4

**Scenario:**
When inputs are:

- root: ''
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,13,16,25,30
**Covers Design:** D1

### ID: 5

**Scenario:**
When inputs are:

- root: ""
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,14,16,25,30
**Covers Design:** D1

### ID: 6

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,13,16,25,30
**Covers Design:** D1

### ID: 7

**Scenario:**
When inputs are

- Path in the format '/location' and exists.
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,14,16,25,30
**Covers Design:** D1

### ID: 8

**Scenario:**
When inputs are:

- root: ''
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format \* with backticks and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,13,16,25,31
**Covers Design:** D1

### ID: 9

**Scenario:**
When inputs are:

- root: ""
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an array of strings in format \* with backticks and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 1,8,11,14,16, 25,31
**Covers Design:** D1

### ID: 10

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format \* with backticks and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,13,16,25,31
**Covers Design:** D1

### ID: 11

**Scenario:**
When inputs are

- Path in the format '/location' and exists.
- filename = 'name' and location exists
- tablename include \* with backticks and exists
- columns is an array of strings in format \* with backticks and each exists in excel table

Then return id of excel table and status code 0
**Covers Equivalence Classes:** 4,6,8,11,14,16,25,31
**Covers Design:** D1

### ID: 12

**Scenario:**
When inputs are:

- Path in the format '/location' and exists.
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- tablename includes only [A-Za-z_] and values dne in excel table

Then return id of excel table, and status code 0, missing columns included in table
**Covers Design:** D2

### ID: 13

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns ' '

Then return empty string and status code 4
**Covers Invlaid:** 19
**Covers Design:** D3

### ID: 14

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is JSON object ie: '{}'

Then return empty string and status code 4
**Covers Invlaid:** 20
**Covers Design:** D3

### ID: 15

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is Number ie: 0

Then return empty string and status code 4
**Covers Invlaid:** 21
**Covers Design:** D3

### ID: 16

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is Boolean ie: true

Then return empty string and status code 4
**Covers Invlaid:** 22
**Covers Design:** D3

### ID: 17

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is Float ie: 0.25

Then return empty string and status code 4
**Covers Invlaid:** 23
**Covers Design:** D3

### ID: 18

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is non-empty string ie: 'Abc4\*6/'

Then return empty string and status code 4
**Covers Invlaid:** 24
**Covers Design:** D3

### ID: 19

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of JSON objects ie: [{},{},{}]

Then return empty string and status code 4
**Covers Invlaid:** 26
**Covers Design:** D3

### ID: 20

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of Numbers ie: [1,2,3,4]

Then return empty string and status code 4
**Covers Invlaid:** 27
**Covers Design:** D3

### ID: 21

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of Floats ie: [1.1,2.1,3.1,4.1]

Then return empty string and status code 4
**Covers Invlaid:** 28
**Covers Design:** D3

### ID: 22

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of Booleans ie: [true,false,true,false]

Then return empty string and status code 4
**Covers Invlaid:** 29
**Covers Design:** D3

### ID: 23

**Scenario:**
When inputs are:

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of Strings with invalid col chars ie: [`|`,Hello World,1 2,|]

Then return empty string and status code 4
**Covers Invlaid:** 32
**Covers Design:** D3

### ID: 24

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 3
**Covers Invalid Class:** 15
**Covers Design:** D4

### ID: 25

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 3
**Covers Design:** D5

### ID: 26

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is blank space

Then return empty string and status code 3,missing file created
**Covers Design:** D6

### ID: 27

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 2
**Covers Invalid Class:** 9
**Covers Design:** D7

### ID: 28

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 2
**Covers Invalid Class:** 10
**Covers Design:** D7

### ID: 29

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 2
**Covers Design:** D8

### ID: 30

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return empty string and status code 2
**Covers Design:** D9

### ID: 31

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 2
**Covers Design:** D10

### ID: 32

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 2
**Covers Design:** D11

### ID: 33

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = name includes extension
- tablename includes [*] without backticks
- columns is blank space

Then return empty string and status code 2
**Covers Design:** D12

### ID: 34

**Scenario:**
When inputs are

- Path in the format '/'.
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Invalid Class:** 2
**Covers Design:** D13

### ID: 35

**Scenario:**
When inputs are

- path in format './'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Invalid Class:** 3
**Covers Design:** D13

### ID: 36

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Invalid Class:** 5
**Covers Design:** D13

### ID: 37

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Invalid Class:** 5.5
**Covers Design:** D13

### ID: 38

**Scenario:**
When inputs are

- Path in the format '/'.
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 1
**Covers Design:** D14

### ID: 39

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return empty string and status code 1
**Covers Design:** D15

### ID: 40

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Design:** D16

### ID: 41

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 1
**Covers Design:** D17

### ID: 42

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes [*] without backticks
- columns is blank space

Then return empty string and status code 1
**Covers Design:** D18

### ID: 43

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Design:** D19

### ID: 44

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 1
**Covers Design:** D20

### ID: 45

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return empty string and status code 1
**Covers Design:** D21

### ID: 46

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 1
**Covers Design:** D22

### ID: 47

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 1
**Covers Design:** D23

### ID: 48

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is blank space

Then return empty string and status code 1
**Covers Design:** D24

### ID: 49

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 2
**Covers Design:** D25

### ID: 50

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 2
**Covers Design:** D26

### ID: 51

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return empty string and status code 2
**Covers Design:** D27

### ID: 52

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return empty string and status code 2
**Covers Design:** D28

### ID: 53

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return empty string and status code 2
**Covers Design:** D29

### ID: 54

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes [*] without backticks
- columns is blank space

Then return empty string and status code 2
**Covers Design:** D30

### ID: 55

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 2
**Covers Invalid Class:** 12
**Covers Design:** D31

### ID: 56

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 2
**Covers Design:** D32

### ID: 57

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return an empty stringified array with status code 2
**Covers Design:** D33

### ID: 58

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 2
**Covers Design:** D34

### ID: 59

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 2
**Covers Design:** D35

### ID: 60

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return an empty stringified array with status code 2
**Covers Design:** D36

### ID: 61

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D37

### ID: 62

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D38

### ID: 63

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists
- columns is blank space

Then return an empty stringified array with status code 1
**Covers Design:** D39

### ID: 64

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 3
**Covers Equivalence Classes:** 3,8, 12, 15
**Covers Invalid Class:** 3, 12, 15
**Covers Design:** D40

### ID: 65

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 3
**Covers Equivalence Classes:** 3,8, 12, 15
**Covers Invalid Class:** 3, 12, 15
**Covers Design:** D41

### ID: 66

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks
- columns is blank space

Then return an empty stringified array with status code 3
**Covers Design:** D42

### ID: 67

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 3
**Covers Invalid Class:** 17
**Covers Design:** D43

### ID: 68

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 3
**Covers Design:** D44

### ID: 69

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is blank space

Then return an empty stringified array with status code 3
**Covers Design:** D45

### ID: 70

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename Includes extension
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D46

### ID: 71

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename Includes extension
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D47

### ID: 72

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename Includes extension
- tablename includes only [A-Za-z_] and dne
- columns is blank space

Then return an empty stringified array with status code 1
**Covers Design:** D48

### ID: 73

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D49

### ID: 74

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D50

### ID: 75

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne
- columns is blank space

Then return an empty stringified array with status code 1
**Covers Design:** D51

### ID: 76

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D52

### ID: 77

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D53

### ID: 78

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and dne
- columns is blank space

Then return an empty stringified array with status code 1
**Covers Design:** D54

### ID: 79

**Scenario:**
When inputs are

- path in format '/location' and dne
- filename = 'name' and dne
- tablename includes only [A-Za-z_] and dne
- columns is empty array

Then return an empty stringified array with status code 1
**Covers Design:** D55

### ID: 80

**Scenario:**
When inputs are

- path in format '/location' and dne
- filename = 'name' and dne
- tablename includes only [A-Za-z_] and dne
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D56

### ID: 81

**Scenario:**
When inputs are

- path in format '/location' and dne
- filename = 'name' and dne
- tablename includes only [A-Za-z_] and dne
- columns is blank space

Then return an empty stringified array with status code 1
**Covers Design:** D57

### ID: 82

**Scenario:**
When inputs are

- path in format '/location' and dne
- filename = 'name' and dne
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each exists in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D58

### ID: 83

**Scenario:**
When inputs are

- path in format '/location' and dne
- filename = 'name' and dne
- tablename includes [*] without backticks
- columns is an array of strings in format [A-Za-z_] and each dne in excel table

Then return an empty stringified array with status code 1
**Covers Design:** D59
