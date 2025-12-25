🌐 API Testing with Postman and Newman

Automated API testing for Automation Exercise using Postman and Newman.

📖 About:

This project contains Postman collections for testing the Automation Exercise website API. The goal is to automate API testing, ensuring the backend services work as expected and return the correct responses.

🚀 Prerequisites

Make sure you have the following installed before starting:

1.Node.js

2.Git

▶️ Running API Tests
1. Running Tests with Postman
Import the Postman collection from the /postman directory into your Postman app.
Use Postman to manually run the API requests.
2. Running Tests with Newman
To run the tests using Newman in the command line, execute the following:

npm test
You can also generate HTML reports with Newman:

newman run report
🧩 Test Structure
The test files are structured as follows:

📁 postman
 ┗📄 Automation-exercise.postman_collection.json    # Postman collection
Example API request:

{
    "method": "GET",
    "url": "https://automationexercise.com/api/products",
    "header": [],
    "body": {},
    "description": "Get all products"
}

🔗 Useful Links
Postman Documentation
Newman Documentation
Node.js Documentation
