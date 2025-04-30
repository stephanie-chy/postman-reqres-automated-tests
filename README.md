# Postman API Tests for Reqres.in

This repository contains a Postman collection for testing the [Reqres API](https://reqres.in/). It includes automated test scripts for user-related endpoints and global variables to support dynamic test data.

---

## 🧪 Test Coverage

### ✅ `POST /api/users`
Creates a new user with random name and job.

- **TC01**: Verify response status is `201 Created`.
- **TC02**: Check if response contains `name`, `job`, `id`, and `createdAt`.
- **TC03**: Assert `name` matches request data.
- **TC04**: Assert `job` matches request data.
- **TC05**: Validate `id` is not null.
- **TC06**: Check `createdAt` follows ISO 8601 format.

---

### ✅ `GET /api/users/:id`
Retrieves user information by ID.

- **TC01**: Verify response status is `200 OK`.
- **TC02**: Check response includes `data` and `support` as objects.
- **TC03**: Validate that `data` includes `id`, `email`, `first_name`, `last_name`, and `avatar`.
- **TC04**: Validate `support` includes `url` and `text`.

---

### ✅ `PUT /api/users/:id`
Updates user details with new random name and job.

- **TC01**: Verify response status is `200 OK`.
- **TC02**: Check response includes `name`, `job`, and `updatedAt`.
- **TC03**: Assert `name` matches request data.
- **TC04**: Assert `job` matches request data.
- **TC05**: Validate `updatedAt` follows ISO 8601 format.

---

### ✅ `DELETE /api/users/:id`
Deletes a user by ID.

- **TC01**: Verify response status is `204 No Content`.
- **TC02**: Confirm the response body is empty.

---

## ⚙️ Setup Instructions

1. **Download the Files**:
   - `ReqRes API Tests.postman_collection.json`
   - `workspace.postman_globals.json`

2. **Open Postman**.

3. **Import the Collection**:
   - Click **Import** and select `ReqRes API Tests.postman_collection.json`.

4. **Import Global Variables**:
   - Click **Import** again and select `workspace.postman_globals.json`.

5. **Run the Tests**:
   - Use the **Collection Runner** or **Newman** (if using CLI) to run the tests.

> ⚠️ Ensure the global variable `base-url` is set to `https://reqres.in` before running the collection.

---

## 📁 Files

- `ReqRes API Tests.postman_collection.json`: The Postman collection containing all API test requests and scripts.
- `workspace.postman_globals.json`: Global variables used in the tests, including dynamic user data and base URL.

---

## 🛠 Optional: Run Tests via Newman (CLI)

If you'd like to run the tests from the terminal:

1. Install Newman:
   ```bash
   npm install -g newman
