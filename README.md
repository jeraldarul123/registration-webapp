# Registration WebApp

This is a serverless registration web application built using **AWS Lambda, API Gateway, DynamoDB, IAM Roles, and S3 for hosting**. The frontend is stored in an S3 bucket and interacts with the backend via API Gateway and Lambda.

## **Tech Stack**
- **Frontend:** Hosted on AWS S3
- **Backend:** AWS Lambda (Python/Node.js)
- **Database:** AWS DynamoDB
- **API Management:** Amazon API Gateway
- **Security:** IAM Roles for permissions

---

## **Architecture**
1. The frontend (HTML/CSS/JS) is hosted in an S3 bucket.
2. API Gateway acts as the entry point to invoke AWS Lambda functions.
3. AWS Lambda handles user registration and stores data in DynamoDB.
4. IAM roles grant Lambda permissions to interact with DynamoDB.
5. CORS is enabled on API Gateway to allow frontend-backend communication.

---

## **Deployment Steps**
### **1. Set Up the S3 Frontend**
- Upload the frontend files (`index.html`, `script.js`, `styles.css`, etc.) to an **S3 bucket**.
- Enable **Static Website Hosting** in the S3 bucket properties.
- Adjust **Bucket Policy** to allow public access (if required).

### **2. Set Up DynamoDB Table**
- Create a **DynamoDB table** (e.g., `Users`).
- Define `Primary Key` (e.g., `email` or `userID`).

### **3. Deploy the Lambda Function**
- Write the Lambda function in **Python/Node.js**.
- Assign an **IAM Role** with DynamoDB access.
- Deploy the function and get the **Lambda ARN**.

### **4. Configure API Gateway**
- Create a **REST API** in API Gateway.
- Add a **POST method** and integrate it with your Lambda function.
- Enable **CORS** for frontend-backend communication.
- Deploy the API and obtain the **Invoke URL**.

### **5. Connect Frontend with API Gateway**
- In `script.js`, replace `API_URL` with your **API Gateway Invoke URL**.

### **6. Hosting the WebApp**
- Upload the frontend files to the S3 bucket.
- Access your web app via the **S3 bucket URL**.

---

## **How to Use**
1. Open the **S3 bucket URL** in your browser.
2. Enter details in the registration form.
3. Click **Register** to send data to **DynamoDB** via **API Gateway** and **Lambda**.
4. Check DynamoDB to verify the stored user details.

---

## **Setup for Local Development**
### Prerequisites
- **AWS CLI** configured  
- **Node.js/Python** installed  
- **SAM CLI** (optional for local Lambda testing)  


