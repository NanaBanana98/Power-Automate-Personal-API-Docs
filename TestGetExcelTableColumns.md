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
**E1:** 

#### Descion Table
|Symbol | Description                            |
|-------|----------------------------------------|
|T      |denotes that condition has been met     |
|F      |denotes that condition has NOT been met |
|X      |denotes that effect should be rendered  |
|\-     |denotes not applicable                  |

|Descion ID     |   D1  |D2 |
----------------|-------|---|
|**Conditions** |       |   |
|C1             |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |
|C2             |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |T |d |D |D |D |D |D |D |D |D |D |D |D |D |d |d |D |
|C3             |T |T T T T T T T
|C4             |T |T |T |T |F |F |F |F |T |T |T |T |F |F |F |F |T |T |T |T |F |F |F |F |T |T |T |T |F |F |F |F |
|C5             |T |T |F |F |T |F |F |T |T |F |F |T |T |F |F |T |T |F |F |T |T |F |F |T |T |F |F |T |T |F |F |T |
|C6             |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |T |F |
|**Effects**    |       |   |
|               |       |   |


### Equivelence Class Partitioning
|Class                      | Valid Equivlence Classes      |Invalid Equivlence Classes          |
|---------------------------|-------------------------------|------------------------------------|

## Test Cases
### ID: VALID_EMPTY
**Scenario:** When Given , 
Then 
**Covers Equivelence Classes:** 
**Covers Descion:** 


## Test Run Results
```javascript
```