# Test 'Get Excel Table Columns'
[Docs for Get Excel Table Columns](utilities.md)

## Analysis

### Cause Effect Analysis

#### Conditions
**C1:** Path provided exists
**C2:** Path provided is in a valid format
**C3:** File name provided exists
**C4:** File name provided is in a valid format
**C5:** Table name provided exists
**C6:** Table name provided is a valid table name

#### Effects
**E1:** Status code 0 is returned
**E2:** Status code 1 is returned
**E3:** Status code 2 is returned
**E4:** Status code 3 is returned
**E5:** Empty stringified array returned
**E6:** Array containing Excel table names is returned  
#### Descion Table
|Symbol | Description                            |
|-------|----------------------------------------|
|T      |denotes that condition has been met     |
|F      |denotes that condition has NOT been met |
|X      |denotes that effect should be rendered  |
|\-     |denotes not applicable                  |

|Descion ID     |   D1  |D2 |D3 |D4 |D5 |D6 |D7 |D8 |D9 |D10|D11 |D12 |D13 |D14 |D15 |D16 |D17 |D18 |D19 |D20 |
----------------|-------|---|---|---|---|---|---|---|---|---|----|----|----|----|----|----|----|----|----|----|
|**Conditions** |       |   |   |   |   |   |   |   |   |   |    |    |    |    |    |    |    |    |    |    |
|C1             |T      |T  |T  |T  |F  |F  |F  |F  |F  |F  |F   |F   |T   |T   |F   |F   |T   |T   |F   |F   |
|C2             |T      |T  |T  |T  |F  |F  |F  |F  |T  |T  |T   |T   |T   |T   |F   |F   |T   |T   |F   |F   |
|C3             |T      |T  |F  |F  |T  |T  |F  |F  |T  |T  |F   |F   |F   |F   |F   |F   |T   |F   |T   |F   |
|C4             |T      |T  |F  |F  |T  |T  |F  |F  |T  |T  |F   |F   |T   |T   |T   |T   |T   |F   |T   |F   |
|C5             |T      |F  |T  |F  |T  |F  |T  |F  |T  |F  |T   |F   |T   |F   |T   |F   |F   |F   |F   |F   |
|C6             |T      |F  |T  |F  |T  |F  |T  |F  |T  |F  |T   |F   |T   |F   |T   |F   |T   |T   |T   |T   |
|**Effects**    |       |   |   |   |   |   |   |   |   |   |    |    |    |    |    |    |    |    |    |    |
|E1             |X      |-  |-  |-  |-  |-  |-  |-  |-  |-  |-   |-   |-   |-   |-   |-   |-   |-   |-   |-   |
|E2             |-      |-  |-  |-  |X  |X  |X  |X  |X  |X  |X   |X   |-   |-   |X   |-   |-   |X   |X   |X   |
|E3             |-      |-  |X  |X  |-  |-  |-  |-  |-  |-  |-   |-   |X   |X   |-   |-   |-   |-   |-   |-   |
|E4             |-      |X  |-  |-  |-  |-  |-  |-  |-  |-  |-   |-   |-   |-   |-   |X   |X   |-   |-   |-   |
|E5             |-      |X  |X  |X  |X  |X  |X  |X  |X  |X  |X   |X   |X   |X   |X   |X   |X   |X   |X   |X   |
|E6             |X      |-  |-  |-  |-  |-  |-  |-  |-  |-  |-   |-   |-   |-   |-   |-   |-   |-   |-   |-   |

### Equivelence Class Partitioning
|Class                      | Valid Equivlence Classes              |Invalid Equivlence Classes             |
|---------------------------|---------------------------------------|---------------------------------------|
|**Path**                   | 1 - Contains only valid chars         | 6 - Contains invalid chars            |
|**Contains valid chars**   | 2 - To Root                           | 7 - Ends with '/'                     | 
|                           | 3 - To Subdir                         |                                       |
|**To Root**                | 4 - Is ''                             | 8 - Is '/'                            |
|**To subdir**              | 5 - Maps to valid subdir              | 9 - Does not map to valid subdir      |

|Class                      | Valid Equivlence Classes              |Invalid Equivlence Classes             |
|---------------------------|---------------------------------------|---------------------------------------|
|**Filename**               | 10 - Contains only valid chars        | 12 - Contains Invalid Chars           |
|**Contains valid chars**   | 11 - Maps to existing file            | 13 - Does not map to existing file    |
|                           |                                       | 14 - Includes extension               |

|Class                      | Valid Equivlence Classes              |Invalid Equivlence Classes             |
|---------------------------|---------------------------------------|---------------------------------------|
|**Table Name**             | 15 - Is in a valid format             | 17 - Is not in a valid format         |
|**Is In a Valid Format**   | 16 - Maps to existing table           | 18 - Does not map to existing table   |
          

## Test Cases
### ID: VALID_ROOT
**Scenario:** When Given a valid Root Path = '', A filename that maps to an existing file, and a table name that maps to an existing table
Then return the columns of that table with status code 0
**Covers Equivelence Classes:**  1, 2, 4, 10, 11, 15, 16
**Covers Descion:** D1

### ID: VALID_SUBDIR
**Scenario:** When Given a valid SubDir Path = '', A filename that maps to an existing file, and a table name that maps to an existing table
Then return the columns of that table with status code 0
**Covers Equivelence Classes:**  1, 3, 5, 10, 11, 15, 16
**Covers Descion:** D1

### ID: INVALID_TABLENAME
**Scenario:** When Given a valid Root Path = '', A filename that maps to an existing file, and a table name in an invalid format
Then return an empty array with status code 0
**Covers Equivelence Classes:**  1, 2, 4, 10, 11, 17
**Covers Descion:** D2

### ID: INVALID_FILENAME
**Scenario:** When Given a valid Root Path = '', a filename that is in an invalid format, and a table name that maps to an existing table
Then return an empty array with status code 0
**Covers Equivelence Classes:**  1, 2, 4, 12, 16
**Covers Descion:** D3

### ID: INVALID_FILENAME_EXT
**Scenario:** When Given a valid Root Path = '', a filename that is in an invalid format, and a table name that maps to an existing table
Then return an empty array with status code 0
**Covers Equivelence Classes:**  1, 2, 4, 14, 16
**Covers Descion:** D3

### ID: VALID_FILENAME_DNE
**Scenario:** When Given a valid Root Path = '', a filename that is in a valid format but does not map to an existing file, and a table name in an invalid format
Then return an empty array with status code 0
**Covers Equivelence Classes:**  1, 2, 4, 10, 13, 17
**Covers Descion:** D4

## Test Run Results
```javascript
```