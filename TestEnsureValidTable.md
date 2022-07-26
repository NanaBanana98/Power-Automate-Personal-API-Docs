# Test 'Ensure Valid Excel Table'

[Docs for Ensure Valid Excel Table](utilities.MD)

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

| Descion ID     | D1  | D2  | D3  | D4  | D5  | D6  | D7  | D8  | D9  | D10 | D11 | D12 | D13 | D14 | D15 | D16 | D17 | D18 | D19 | D20 | D21 | D22 | D23 | D24 | D25 | D26 | D27 | D28 | D29 | D30 | D31 | D32 | D33 | D34 | D35 | D36 | D37 | D38 | D39 | D40 | D41 | D42 | D43 | D44 | D45 | D46 | D47 | D48 | D49 | D50 | D51 | D52 | D53 | D54 | D55 | D56 | D57 | D58 | D59 | D60 | D61 |
| -------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Conditions** |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| C0             | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   |
| C1             | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   |
| C2             | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   |
| C3             | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   |
| C4             | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   | F   |
| C5             | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | F   | F   | F   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | T   | F   | F   | F   | F   |
| C6             | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | F   | T   | T   | T   | T   |
| C7             | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | F   | T   | F   | T   | F   |
| **Effects**    |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| E0             | X   |
| E1             | -   |
| E2             | -   |
| E3             | -   |
| E4             | -   |
| E5             | -   |
| E6             | -   |
| E7             | -   |
| E8             | -   |
| E9             | X   |
| E10            | -   |
