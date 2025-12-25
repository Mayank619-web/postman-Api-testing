## 🌐 API Testing with Postman and Newman

Automated API testing for [Automation Exercise](https://www.automationexercise.com/) using Postman and Newman.

## 📖 About:

This project contains Postman collections for testing the [Automation Exercise](https://www.automationexercise.com/) website API. The goal is to automate API testing, ensuring the backend services work as expected and return the correct responses.

## 🚀 Prerequisites

Make sure you have the following installed before starting:

1.[Node.js](https://nodejs.org)

2.[Git](https://git-scm.com/)

# ▶️ Running API Tests
## 1. Running Tests with Postman
-Import the Postman collection from the /postman directory into your Postman app.

-Use Postman to manually run the API requests.
## 2. Running Tests with Newman

To run the tests using Newman in the command line, execute the following:
### npm test
You can also generate HTML reports with Newman:

newman run report

## 🧩 Test Structure
The test files are structured as follows:

📁 postman
 ┗📄 Automation-exercise.postman_collection.json    # Postman collection
## Example API request:

{
    "method": "GET",
    "url": "https://automationexercise.com/api/products",
    "header": [],
    "body": {},
    "description": "Get all products"
}

## API1: GET All Products List
## •	API URL: https://automationexercise.com/api/productsList

## •	Request Method: GET

## •	Response Code: 200

## •	Response JSON: All products list
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/41acc001-b124-4b57-99de-db46d6f1f328" />

 
## How Test Scripts Are Created (As per Screenshot)
testing:
## GET https://automationexercise.com/api/productsList
### Step-by-Step Process
1.	Open the API request in Postman
2.	Click Scripts
3.	Select post-response (this is the Tests section)
4.	Write assertions using pm.test()
5.	Click Send
6.	View results in the Test Results panel
________________________________________
## Test Scripts Used in Your Screenshot (Explained)
### 1) Status Code Validation
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

### What it validates
•	Confirms the API returned HTTP 200 OK

### Result
•	PASSED → API is reachable and successful
________________________________________
### 2) Response Time Validation
pm.test("Response time is greater than 1000ms", function () {
    pm.expect(pm.response.responseTime).to.be.above(1000);
});

### What it validates
•	Confirms response time is above 1000 ms

### Note (Best Practice)
•	Normally performance tests check for less than a threshold.

### Example:
•	pm.expect(pm.response.responseTime).to.be.below(1000);
________________________________________
### 3) Header Validation (Content-Type)
pm.test("Content-Type is JSON", function () {
    pm.response.to.have.header("Content-Type");
});

### What it validates
•	Ensures the response contains the Content-Type header
•	Confirms JSON response format
________________________________________
### How Test Results Are Generated
#### After clicking Send:
#### •	Postman executes each pm.test() block
#### •	Results appear under Test Results (3/3)
####•	Each assertion shows:
#### o	PASSED or FAILED
#### o	Clear message name
#### •	Response summary shows:
#### o	Status: 200 OK
#### o	Time: 1.13 s
#### o	Size: 1.77 KB
<img width="940" height="494" alt="image" src="https://github.com/user-attachments/assets/0f5efbdc-a845-40a2-b60d-acf2694d1168" />

 
## API2: POST To All Products List
## •	API URL: https://automationexercise.com/api/productsList
## •	Request Method: POST
## •	Response Code: 405
## •	Response Message: This request method is not supported.
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/28ac5ef3-537f-4392-8c00-53fe9e31b358" />

 

## API3: GET All Products List
## •	API URL: https://automationexercise.com/api/brandsList
## •	Request Method: GET
## •	Response Code: 200
## •	Response Message: All brands list.
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/b20b8c81-c6f9-4471-aa9b-f9d6d9c63617" />

 
## API4: PUT To All Brands List
## •	API URL: https://automationexercise.com/api/brandsList
## •	Request Method: PUT
## •	Response Code: 405
## •	Response Message: This request method is not supported.
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/bf59bdee-9f9e-43f2-a162-2e36e2a5a2fa" />

 
## API5: POST To Search Product
## •	API URL: https://automationexercise.com/api/searchProduct
## •	Request Method: POST
## •	Request Parameter: search_product (For example: top, tshirt, jean)
## •	Response Code: 200
### •	Response JSON: Searched products list
<img width="940" height="501" alt="image" src="https://github.com/user-attachments/assets/76ce8413-567f-4a5a-b41b-60194ec4f4fc" />

 

## API6: POST To Search Product without search_product_paramater
## •	API URL: https://automationexercise.com/api/searchProduct
## •	Request Method: POST
## •	Request Parameter: search_product (For example: top, tshirt, jean)
## •	Response Code: 400
### •	Response JSON: Bad request, search_product parameter is missing in POST request.
<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/092b303a-4c7e-4825-91dc-a929fcc9b2e9" />

 
## API7: POST To Verify Login with valid details
## •	API URL: https://automationexercise.com/api/verifyLogin
## •	Request Method: POST
## •	Request Parameters: email, password
## •	Response Code: 200
### •	Response Message: User exists!
<img width="940" height="491" alt="image" src="https://github.com/user-attachments/assets/8dcacef8-8db4-4c3d-954e-1c9aade23747" />

 

## API8: POST To Verify Login without email parameter
## •	API URL: https://automationexercise.com/api/verifyLogin
## •	Request Method: POST
## •	Request Parameters:  password
## •	Response Code: 400
### •	Response Message: Bad request, email or password parameter is missing in POST request.
<img width="940" height="499" alt="image" src="https://github.com/user-attachments/assets/0ec0949d-f904-4a69-ad91-6b1ebb2dbf8c" />

 

## API9: DELETE To Verify Login 
## •	API URL: https://automationexercise.com/api/verifyLogin
## •	Request Method: DELETE
## •	Response Code: 405
### •	Response Message: This request method is not supported.
<img width="940" height="486" alt="image" src="https://github.com/user-attachments/assets/ebf392db-4389-40ba-b4a8-1838950fc8b7" />

 

## API10: POST To Verify Login with invalid details
## •	API URL: https://automationexercise.com/api/verifyLogin
## •	Request Method: POST
## •	Request Parameters:  email, password (invalid values)
## •	Response Code: 404
### •	Response Message: User not Found!
<img width="940" height="499" alt="image" src="https://github.com/user-attachments/assets/f4619b58-042e-43c1-9aac-c9565ddd5b06" />

 

## API11: POST To Create/Register User Account
## •	API URL: https://automationexercise.com/api/createAccount 
## •	Request Method: POST
## •	Request Parameters: name, email, password, title (for example: Mr, Mrs, Miss), birth_date, birth_month, birth_year, firstname, lastname, company, address1, address2, country, zipcode, state, city, mobile_number
## •	Response Code: 201
### •	Response Message: User created!
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/de121f5e-0766-4f88-96c3-d8b2bc8a4f6d" />

 

## API12: DELETE Method to Delete User Account
## •	API URL: https://automationexercise.com/api/deleteAccount
## •	Request Method: DELETE
## •	Request Parameters:  email, password
## •	Response Code: 200
## •	Response Message: Account deleted!
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/68f1dfdc-6000-42ec-90b0-335bfcfa7422" />

 

## API13: PUT Method to Update User Account
## •	API URL: https://automationexercise.com/api/updateAccount
## •	Request Method: PUT
## •	Request Parameters:  name, email, password, title (for example: Mr, Mrs, Miss), birth_date, birth_month, birth_year, firstname, lastname, company, address1, address2, country, zipcode, state, city, mobile_number
## •	Response Code: 200
### Response Message: User updated!
<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/81cf9b88-4b9e-4768-a1b4-c1c656330ebf" />

 



## 🔗 Useful Links
•[Postman Documentation](https://learning.postman.com/docs/getting-started/introduction/)

•[Newman Documentation](https://www.npmjs.com/package/newman)

•[Node.js Documentation](https://nodejs.org/en/docs/)
