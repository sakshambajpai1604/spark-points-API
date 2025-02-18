# Display Spark Points API  

This API endpoint retrieves the number of spark points a user has earned. It requires the User ID to be sent in the header for authentication.  

---

## 📚 Table of Contents  
- [Description](#description)  
- [Tech Stack](#tech-stack)  
- [API Endpoint](#api-endpoint)  
- [How to Test the API](#how-to-test-the-api)
- [Error Handling](#error-handling)  

---

## 📄 Description  
The **Display Spark Points API** allows users to check their current spark points balance. This is useful for tracking rewards, achievements, or other point-based systems.  

---

## 🚀 Tech Stack  
- **Backend:** Flask  
- **Database:** PostgreSQL 

---

## 🔗 API Endpoint  

### ➡️ GET /user/spark-points    

#### 📝 Description  
- Retrieves the number of spark points a user has earned.

### ➡️ POST /user/spark-points

#### 📝 Description  
- Creates/Updates the user's spark points.

---

## 🚀 How to Test the API

### ✅ Get User Spark Points (GET)
Retrieve the spark points balance for a specific user.
```
curl -H "User-ID: 101" -X GET http://127.0.0.1:5000/user/spark-points
```
Response:
```
{
  "user_id": "101",
  "spark_points": 250
}
```
### ✅ Update/Create Spark Points (POST)
Update the spark points for a specific user.
```
curl -H "Content-Type: application/json" -H "User-ID: 101" -X POST -d '{"spark_points": 500}' http://127.0.0.1:5000/user/spark-points
```
Response:
```
{
  "message": "Spark Points updated",
  "user_id": "101",
  "spark_points": 500
}
```


---

## ⚠️ Error Handling
- 400 Bad Request: If the input data is invalid (e.g., negative points).
- 401 Unauthorized: If the User ID is missing or invalid.
- 404 Not Found: If no user is found with the given User ID.
- 500 Internal Server Error: If an unexpected error occurs on the server.

---
