# Test 'Get Excel Table Columns'

[Docs for Get Excel Table Columns](utilities.MD)

## Contents

- [Analysis](#analysis)
  - [Cause-Effect Analysis](#cause-effect-analysis)
    - [Conditions](#conditions)
    - [Effects](#effects)
    - [Table](#design-table)
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

## Analysis

### Cause-Effect Analysis

#### Conditions

- **C1:** Path provided exists
- **C2:** Path provided is in a valid format
- **C3:** File name provided exists
- **C4:** File name provided is in a valid format
- **C5:** Table name provided exists
- **C6:** Table name provided is a valid table name

#### Effects

- **E1:** Returns status code 0
- **E2:** Returns status code 1
- **E3:** Returns status code 2
- **E4:** Returns status code 3
- **E5:** Empty stringified Array returned
- **E6:** Returns Array containing Excel table names

#### Design Table

| Symbol | Description                                  |
| ------ | -------------------------------------------- |
| T      | denotes that conditions met                  |
| F      | indicates that requirements **not** met      |
| X      | means that the program should execute effect |
| \-     | denotes not applicable                       |

| Descion ID     | D1  | D2  | D3  | D4  | D5  | D6  | D7  | D8  | D9  | D10 | D11 | D12 | D13 | D14 | D15 | D16 | D17 | D18 | D19 | D20 |
| -------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Conditions** |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| C1             | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | F   | F   | T   | T   | F   | F   |
| C2             | T   | T   | T   | T   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | T   | T   | F   | F   |
| C3             | T   | T   | F   | F   | T   | T   | F   | F   | T   | T   | F   | F   | F   | F   | F   | F   | T   | F   | T   | F   |
| C4             | T   | T   | F   | F   | T   | T   | F   | F   | T   | T   | F   | F   | T   | T   | T   | T   | T   | F   | T   | F   |
| C5             | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | F   | F   | F   | F   |
| C6             | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | F   | T   | T   | T   | T   |
| **Effects**    |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| E1             | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |
| E2             | -   | -   | -   | -   | X   | X   | X   | X   | X   | X   | X   | X   | -   | -   | X   | -   | -   | X   | X   | X   |
| E3             | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   | -   | -   | -   |
| E4             | -   | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | X   | X   | -   | -   | -   |
| E5             | -   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   | X   |
| E6             | X   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |

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

### ID: 1

**Scenario:**
When inputs are:

- root: ""
- filename = 'name' and location exists
- tablename include \* with backticks and exists

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 1,8,11,14,16

**Covers Design:** D1

### ID: 2

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 4,6,8,11,13,16

**Covers Design:** D1

### ID: 3

**Scenario:**
When inputs are

- Path in the format '/location' and exists.
- filename = 'name' and location exists
- tablename include \* with backticks and exists

Then return the columns of that table with status code 0

**Covers Equivalence Classes:** 4,6,8,11,14,16

**Covers Design:** D1

### ID: 4

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 3

**Covers Equivalence Classes:** 4,6,8,11

**Covers Invalid Class:** 15

**Covers Design:** D2

### ID: 5

**Scenario:**
When inputs are

- Path in the format '/location and exists.'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6,13,16

**Covers Invalid Class:** 9

**Covers Design:** D3

### ID: 6

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6,13,16

**Covers Invalid Class:** 10

**Covers Design:** D3

### ID: 6

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6

**Covers Invalid Class:** 15, 9

**Covers Design:** D4

### ID: 7

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = name includes reserved characters
- tablename includes [*] without backticks

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6

**Covers Invalid Class:** 15, 10

**Covers Design:** D4

### ID: 8

**Scenario:**
When inputs are

- Path in the format '/'.
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 2

**Covers Design:** D5

### ID: 9

**Scenario:**
When inputs are

- path in format './'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 3

**Covers Design:** D5

### ID: 10

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 5

**Covers Design:** D5

### ID: 11

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 5.5

**Covers Design:** D5

### ID: 12

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 2, 15

**Covers Design:** D6

### ID: 13

**Scenario:**
When inputs are

- path in format './'
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 3, 15

**Covers Design:** D6

### ID: 14

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 5, 15

**Covers Design:** D6

### ID: 15

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11

**Covers Invalid Class:** 5.5, 15

**Covers Design:** D6

### ID: 16

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 8,11,13,16

**Covers Invalid Class:** 2

**Covers Design:** D7

### ID: 17

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 13,16

**Covers Invalid Class:** 3, 9

**Covers Design:** D7

### ID: 18

**Scenario:**
When inputs are

- path in format './'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 13,16

**Covers Invalid Class:** 3, 10

**Covers Design:** D7

### ID: 19

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 13,16

**Covers Invalid Class:** 5, 9

**Covers Design:** D7

### ID: 20

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 13,16

**Covers Invalid Class:** 5, 10

**Covers Design:** D7

### ID: 21

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 13,16

**Covers Invalid Class:** 5.5, 9

**Covers Design:** D7

### ID: 22

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1
**Covers Equivalence Classes:** 13,16
**Covers Invalid Class:** 5.5, 10
**Covers Design:** D7

### ID: 23

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 3, 9, 15

**Covers Design:** D8

### ID: 24

**Scenario:**
When inputs are

- path in format './'
- filename = name includes reserved characters
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 3, 10, 15

**Covers Design:** D8

### ID: 25

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 5, 9, 15

**Covers Design:** D8

### ID: 26

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 5, 10, 15

**Covers Design:** D8

### ID: 27

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 5.5, 9, 15

**Covers Design:** D8

### ID: 28

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes reserved characters
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 5.5, 10, 15

**Covers Design:** D8

### ID: 29

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,7,8,11,13,16

**Covers Invalid Class:** 7

**Covers Design:** D9

### ID: 30

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = 'name' and location exists
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,7,8,11,15

**Covers Invalid Class:** 7, 15

**Covers Design:** D10

### ID: 31

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,7,9,13,16

**Covers Invalid Class:** 7, 9

**Covers Design:** D11

### ID: 32

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,7,10,13,16

**Covers Invalid Class:** 7, 10

**Covers Design:** D11

### ID: 33

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,7,9,15

**Covers Invalid Class:** 7, 9, 15

**Covers Design:** D12

### ID: 34

**Scenario:**
When inputs are

- Path in format '/location' and DNE
- filename = name includes reserved characters
- tablename includes [*] without backticks

Then return an empty stringified array with status code 1

**Covers Invalid Class:** 7, 9, 15

**Covers Design:** D12

### ID: 35

**Scenario:**
When inputs are

- Path in format '/location' and exists.
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6,8,12,13,16

**Covers Invalid Class:** 12

**Covers Design:** D13

### ID: 36

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 2

**Covers Equivalence Classes:** 4,6,8,12,15

**Covers Invalid Class:** 7, 15

**Covers Design:** D14

### ID: 37

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 12,13,16

**Covers Invalid Class:** 2, 12

**Covers Design:** D15

### ID: 38

**Scenario:**
When inputs are

- path in format './'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 12,13,16

**Covers Invalid Class:** 3, 12

**Covers Design:** D15

### ID: 39

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 12,13,16

**Covers Invalid Class:** 5, 12

**Covers Design:** D15

### ID: 40

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = 'name' and location dne
- tablename includes only [A-Za-z_] and exists

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 12,13,16

**Covers Invalid Class:** 5.5, 12

**Covers Design:** D15

### ID: 41

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 3

**Covers Equivalence Classes:** 3,8, 12, 15

**Covers Invalid Class:** 3, 12, 15

**Covers Design:** D16

### ID: 42

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 3

**Covers Equivalence Classes:** 5,8, 12, 15

**Covers Invalid Class:** 5, 12, 15

**Covers Design:** D16

### ID: 43

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes extension
- tablename includes [*] without backticks

Then return an empty stringified array with status code 3

**Covers Equivalence Classes:** 5.5,8, 12, 15

**Covers Invalid Class:** 5.5, 12, 15

**Covers Design:** D16

### ID: 44

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 3

**Covers Equivalence Classes:** 4,6,8,11,13,17

**Covers Invalid Class:** 17

**Covers Design:** D17

### ID: 45

**Scenario:**
When inputs are

- Path in format '/location' and exists
- filename Includes extension
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,6,9,13,17

**Covers Invalid Class:** 9,17

**Covers Design:** D18

### ID: 46

**Scenario:** When inputs are

- Path in format '/location' and exists
- filename Includes reserved characters
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 4,6,10,13,17

**Covers Invalid Class:** 10,17

**Covers Design:** D18

### ID: 47

**Scenario:**
When inputs are

- Path in format '/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 2,8,11,13,17

**Covers Invalid Class:** 2,17

**Covers Design:** D19

### ID: 48

**Scenario:**
When inputs are

- path in format './'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 3,8,11,13,17

**Covers Invalid Class:** 3,17

**Covers Design:** D19

### ID: 49

**Scenario:**
When inputs are

- path in format '/location/'
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5,8,11,13,17

**Covers Invalid Class:** 5,17

**Covers Design:** D19

### ID: 50

**Scenario:**
When inputs are

- Path has spec chars[><:/\|?*]
- filename = 'name' and location exists
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5.5,8,11,13,17

**Covers Invalid Class:** 5.5,17

**Covers Design:** D19

### ID: 51

**Scenario:**
When inputs are

- path in format './'
- filename = name includes extension
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 3,9,13,17

**Covers Invalid Class:** 3, 9, 17

**Covers Design:** D20

### ID: 52

**Scenario:**
When inputs are

- path in format './'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 3,10,13,17

**Covers Invalid Class:** 3, 10, 17

**Covers Design:** D20

### ID: 53

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes extension
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5,9,13,17

**Covers Invalid Class:** 5, 9, 17

**Covers Design:** D20

### ID: 54

**Scenario:**
When inputs are

- path is in form '/location/'
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5,10,13,17

**Covers Invalid Class:** 5, 10, 17

**Covers Design:** D20

### ID:

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes extension
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5.5,9,13,17

**Covers Invalid Class:** 5.5, 9, 17

**Covers Design:** D20

### ID: 55

**Scenario:**
When inputs are

- path name has reserved chars[><:/\|?*]
- filename = name includes reserved characters
- tablename includes only [A-Za-z_] and dne

Then return an empty stringified array with status code 1

**Covers Equivalence Classes:** 5.5,10,13,17

**Covers Invalid Class:** 5.5, 10, 17

**Covers Design:** D20

## Test Run Results

```javascript

```
