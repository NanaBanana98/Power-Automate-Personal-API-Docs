# Save AR Data

Flows that are reusable and no similar templates could be found.
Contents:

- [Extract AR Data](#extract-ar-data)
- [Populate Excel Table with AR Data](#populate-excel-table-with-ar-data)
- [Request Approval for AR Data](#request-approval-for-ar-data)
- [Get Customer From AR PDF](#get-customer-from-ar-pdf)

---


## Extract AR Data

Gets required AR information from a file passed

### Input

##### File ID (required)

*(String)* Id of the AR file
Sample Input

```b!ejnbUIYXZkSV8liQhxO-WJ4Z8TX-OSBAntZBWA7_UNUF_8bx4-_cRrnhasAO8ciG.01LKSRAJ4QU4KHGYGJLREIBSUEMP4TW4CU```


### Output

##### Content Bytes

*(String)* The contents of the file that has been analyzed

##### Invoice Number

*(String)* Unique ID generated by Vendor. Commonly starts with JC


#### Amount
*(Float, Precsision 2)* Amount Paid

#### Vendor

*(String)* Name of the vendor


#### Payment Date

*(String)* Day paid, in format YY/MM/DD


#### Cheque Number

*(String)* May also be labeled as voucher number or remittance number. If none exists then use date


#### Status Code

*(Integer)*

- **0** Success
- **-1:** Invalid File ID
- **-2:** Extract AR Data has not been trained for this customer's Invoice

#### Sample Output
```javascript

```

---

## Get Customer From AR PDF

##### File ID (required)

*(String)* Id of the AR file
Sample Input

```b!ejnbUIYXZkSV8liQhxO-WJ4Z8TX-OSBAntZBWA7_UNUF_8bx4-_cRrnhasAO8ciG.01LKSRAJ4QU4KHGYGJLREIBSUEMP4TW4CU```

### Output

#### Vendor
*(String)* Stringified JSON object with properties:
- name
- key

#### Status Code
*(Integer)*

- **0:** Success
- **-1:** Invalid File ID
- **-2:** Customer not found

#### Sample Output
```javascript

```

---

## Populate Excel Table with AR Data

### Inputs

##### Content Bytes

*(String)* The contents of the file that has been analyzed

##### Invoice Number

*(String)* Unique ID generated by Vendor. Commonly starts with JC


#### Amount
*(Float, Precsision 2)* Amount Paid

#### Vendor

*(String)* Name of the vendor


#### Payment Date

*(String)* Day paid, in format YY/MM/DD


#### Cheque Number

*(String)* May also be labeled as voucher number or remittance number. If none exists then use date


### Outputs

#### Status Code
*(Integer)*

- **0:** Success
- **-1:** Content Bytes provided
- **-2:** Invalid invoice number provided
- **-3:** Invlaid amount provided
- **-4:** Invalid Vendor provided
- **-5:** Invalid Payment Date provided
- **-6:** Invalid Cheque Number provided
- **-10:**  Internal Error. Try checking variables for path, filename, and table. Ensure that they are valid

#### Sample Output
```javascript

```

---

## Request Approval for AR Data

### Inputs

### Outputs

#### Status Code

#### Sample Output
```javascript

```

---