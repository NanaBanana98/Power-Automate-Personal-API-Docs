# Test 'Get Prop Names'
[Utilities Docs](utilities.md)

## Analysis

### Cause Effect Analysis

#### Conditions
**C1:** Valid JSON object must be passed

#### Effects
**E1:** An empty array is returned
**E2:** A status code of -1 is returned
**E3:** Array containing JSON object prop names is returned
**E4:** A status code of 0 is returned

#### Descion Table
|Symbol | Description                            |
|-------|----------------------------------------|
|T      |denotes that condition has been met     |
|F      |denotes that condition has NOT been met |
|X      |denotes that effect should be rendered  |
|\-     | denotes that effect should not be rendered |

|Descion ID     |   D1  |D2 |
----------------|-------|---|
|**Conditions** |       |   |
|C1             |   T   | F |
|**Effects**    |       |   |
|E1             |   -   | x |
|E2             |   -   | x |
|E3             |   x   | - |
|E4             |   x   | - |

### Equivelence Class Partitioning
|Class                      | Valid Equivlence Classes      |Invalid Equivlence Classes          |
|---------------------------|-------------------------------|------------------------------------|
|**JSON Object**            |1 - Empty Object (no props)    |7 - blank space                     |
|                           |2 - Object with string prop    |8 - alphanumeric string             |  
|                           |3 - Object with integer prop   |9 - string with object embedded within|
|                           |4 - Object with bool prop      |10- no curly braces                |
|                           |5 - Object with array prop     |11 - array                         |
|                           |6 - Object with object prop    |12 - float                         |
|                           |29 - Object with float prop    |13 - integer                       |
|**Object string prop**     |14 - stringified array         |20 - no string prop exists         |
|                           |15 - stringified object        |                                   |
|                           |16 - includes :                |                                   |
|                           |17 - includes \"               |                                   |
|                           |18 - includes '[' but not ']'  |                                   |
|                           |19 - includes '{' but not '}'  |                                   |
|                           |31 - includes ']' but not '['  |                                   |
|                           |32 - includes '}' but not '{'  |                                   |
|                           |30 - empty string              |                                   |
|**Object array prop**      |21 - array of objects          |28 - no array prop exists          |
|                           |22 - array of strings          |                                   |
|                           |23 - array of arrays           |                                   |
|                           |24 - array of integers         |                                   |
|                           |25 - array of floats           |                                   |
|                           |26 - empty array               |                                   |
|                           |27 - array of bools            |                                   |

## Test Cases
### ID: VALID_EMPTY
**Scenario:** When Given an empty object, 
Then return an empty array with status code 0
**Covers Equivelence Classes:** 1, 20, 28
**Covers Descion:** D1

### ID: VALID_FILLED
**Scenario:** When Given an object with the props:
1. integer
2. bool
3. float
4. string with a value of stringified array 
5. string with a value that include :, \", [ but not ] and { but not }
6. string with a value that is a stringified object
7. string with an empty value
8. An empty array
9. An array of bools
10. An array of objects
11. An array of integers
12. An array of floats
13. An array of arrays
14. string with a value that include :, \", } but not { and ] but not [

 Then return an array of length 14 containing the name of each prop and a status code of 0
**Covers Equivelence Classes:** 2, 14, 15, 16, 17, 18, 19, 3, 4, 5, 21, 22, 23, 24, 25, 26, 27, 6, 29, 30, 31, 32
**Covers Descion:** D1

### ID: INVALID_BLANK
**Scenario:** When Given blank space 
Then return an empty array and status code -1
**Covers Equivelence Classes:** 7
**Covers Descion:** D2

#### ID: INVALID_ALPHA_NUMERIC
**Scenario:** When Given an alphanumeric string 
Then return an empty array and status code -1
**Covers Equivelence Classes:** 8
**Covers Descion:** D2

### ID: INVALID_ALPHA_NUMERIC_OBJECT
**Scenario:** When Given an alphanumeric string with an object embedded within
Then return an empty array and status code -1
**Covers Equivelence Classes:** 9
**Covers Descion:** D2

### ID: INVALID_NO_CURLYS
**Scenario:** When Given an object without curly braces
Then return an empty array and status code -1
**Covers Equivelence Classes:** 10
**Covers Descion:** D2

### ID: INVALID_ARRAY
**Scenario:** When Given an array
Then return an empty array and status code -1
**Covers Equivelence Classes:** 11
**Covers Descion:** D2

### ID: INVALID_FLOAT
**Scenario:** When Given a float
Then return an empty array and status code -1
**Covers Equivelence Classes:** 12
**Covers Descion:** D2

### ID: INVALID_INTEGER
**Scenario:** When Given an integer
Then return an empty array and status code -1
**Covers Equivelence Classes:** 13
**Covers Descion:** D2

## Test Run Results
```javascript
```