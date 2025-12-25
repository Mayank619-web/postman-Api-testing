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

API1: GET All Products List
•	API URL: https://automationexercise.com/api/productsList
•	Request Method: GET
•	Response Code: 200
•	Response JSON: All products list
 
How Test Scripts Are Created (As per Screenshot)
testing:
GET https://automationexercise.com/api/productsList
Step-by-Step Process
1.	Open the API request in Postman
2.	Click Scripts
3.	Select post-response (this is the Tests section)
4.	Write assertions using pm.test()
5.	Click Send
6.	View results in the Test Results panel
________________________________________
Test Scripts Used in Your Screenshot (Explained)
1) Status Code Validation
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
What it validates
•	Confirms the API returned HTTP 200 OK
Result
•	PASSED → API is reachable and successful
________________________________________
2) Response Time Validation
pm.test("Response time is greater than 1000ms", function () {
    pm.expect(pm.response.responseTime).to.be.above(1000);
});
What it validates
•	Confirms response time is above 1000 ms
Note (Best Practice)
•	Normally performance tests check for less than a threshold.
Example:
•	pm.expect(pm.response.responseTime).to.be.below(1000);
________________________________________
3) Header Validation (Content-Type)
pm.test("Content-Type is JSON", function () {
    pm.response.to.have.header("Content-Type");
});
What it validates
•	Ensures the response contains the Content-Type header
•	Confirms JSON response format
________________________________________
How Test Results Are Generated
After clicking Send:
•	Postman executes each pm.test() block
•	Results appear under Test Results (3/3)
•	Each assertion shows:
o	PASSED or FAILED
o	Clear message name
•	Response summary shows:
o	Status: 200 OK
o	Time: 1.13 s
o	Size: 1.77 KB

 
API2: POST To All Products List
•	API URL: https://automationexercise.com/api/productsList
•	Request Method: POST
•	Response Code: 405
•	Response Message: This request method is not supported.
 

API3: GET All Products List
•	API URL: https://automationexercise.com/api/brandsList
•	Request Method: GET
•	Response Code: 200
•	Response Message: All brands list.
 
API4: PUT To All Brands List
•	API URL: https://automationexercise.com/api/brandsList
•	Request Method: PUT
•	Response Code: 405
•	Response Message: This request method is not supported.
 
API5: POST To Search Product
•	API URL: https://automationexercise.com/api/searchProduct
•	Request Method: POST
•	Request Parameter: search_product (For example: top, tshirt, jean)
•	Response Code: 200
•	Response JSON: Searched products list
 

API6: POST To Search Product without search_product_paramater
•	API URL: https://automationexercise.com/api/searchProduct
•	Request Method: POST
•	Request Parameter: search_product (For example: top, tshirt, jean)
•	Response Code: 400
•	Response JSON: Bad request, search_product parameter is missing in POST request.
 
API7: POST To Verify Login with valid details
•	API URL: https://automationexercise.com/api/verifyLogin
•	Request Method: POST
•	Request Parameters: email, password
•	Response Code: 200
•	Response Message: User exists!
 

API8: POST To Verify Login without email parameter
•	API URL: https://automationexercise.com/api/verifyLogin
•	Request Method: POST
•	Request Parameters:  password
•	Response Code: 400
•	Response Message: Bad request, email or password parameter is missing in POST request.
 

API9: DELETE To Verify Login 
•	API URL: https://automationexercise.com/api/verifyLogin
•	Request Method: DELETE
•	Response Code: 405
•	Response Message: This request method is not supported.
 

API10: POST To Verify Login with invalid details
•	API URL: https://automationexercise.com/api/verifyLogin
•	Request Method: POST
•	Request Parameters:  email, password (invalid values)
•	Response Code: 404
•	Response Message: User not Found!
 

API11: POST To Create/Register User Account
•	API URL: https://automationexercise.com/api/createAccount 
•	Request Method: POST
•	Request Parameters: name, email, password, title (for example: Mr, Mrs, Miss), birth_date, birth_month, birth_year, firstname, lastname, company, address1, address2, country, zipcode, state, city, mobile_number
•	Response Code: 201
•	Response Message: User created!
 

API12: DELETE Method to Delete User Account
•	API URL: https://automationexercise.com/api/deleteAccount
•	Request Method: DELETE
•	Request Parameters:  email, password
•	Response Code: 200
•	Response Message: Account deleted!
 

API13: PUT Method to Update User Account
•	API URL: https://automationexercise.com/api/updateAccount
•	Request Method: PUT
•	Request Parameters:  name, email, password, title (for example: Mr, Mrs, Miss), birth_date, birth_month, birth_year, firstname, lastname, company, address1, address2, country, zipcode, state, city, mobile_number
•	Response Code: 200
Response Message: User updated!
 



🔗 Useful Links
Postman Documentation
Newman Documentation
Node.js Documentation
