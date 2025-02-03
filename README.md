# Data Scientist's To-Do List Web Application - Flask API

## Project Overview

This is a simple Flask-based web application designed to manage the To-Do list of tasks for data scientists. The app provides an interface to perform basic CRUD (Create, Read, Update, Delete) operations on a list of tasks. It can be used by data scientists to manage their daily tasks such as data cleaning, feature engineering, model training, and much more. The app serves as a practice project for using Flask, REST APIs, and JSON data handling.

## Features

1. **GET Request to Retrieve All Items**:
   - Fetches the entire list of tasks in JSON format.
   - **Endpoint**: `/items`

2. **GET Request to Retrieve a Specific Item by ID**:
   - Fetches a specific task by its ID, returning the corresponding name and description.
   - **Endpoint**: `/items/<int:item_id>`

3. **POST Request to Create a New Task**:
   - Allows users to create a new task by sending data via a JSON object (name and description).
   - **Endpoint**: `/items`
   - Example JSON body:
     ```json
     {
         "name": "Data Preprocessing",
         "description": "Clean the data by removing null values and outliers"
     }
     ```

4. **PUT Request to Update an Existing Task**:
   - Updates the name or description of a task by ID.
   - **Endpoint**: `/items/<int:item_id>`

5. **DELETE Request to Remove a Task**:
   - Removes a task by its ID from the to-do list.
   - **Endpoint**: `/items/<int:item_id>`


## To List json format image.
 ![Alt text](/image.png)


## Technologies Used

- **Flask**: A lightweight Python framework for building web applications.
- **JSON**: Used to structure data sent and received via API requests.
- **HTTP Verbs**: Handling different HTTP methods like GET, POST, PUT, DELETE for CRUD operations.

# Using Postman for API Requests

For testing **POST**, **PUT**, and **DELETE** requests, **Postman** is a powerful tool to interact with the API. Here's how to use it:

### **POST:**

1. Open Postman.
2. Set the HTTP method to **POST**.
3. Enter the URL `http://127.0.0.1:5000/items`.
4. Go to the **Body** tab, select **raw**, and choose **JSON** format.
5. Enter the JSON data for creating a new task (e.g., `"name": "Model Evaluation"`, `"description": "Evaluate the model."`).
6. Click **Send** to create the new task.

### **PUT:**

1. Open Postman.
2. Set the HTTP method to **PUT**.
3. Enter the URL `http://127.0.0.1:5000/items/1` (replace `1` with the task ID you want to update).
4. Go to the **Body** tab, select **raw**, and choose **JSON** format.
5. Enter the updated task data (e.g., `"name": "Data Preprocessing Update"`, `"description": "Refine the data cleaning process."`).
6. Click **Send** to update the task.

### **DELETE:**

1. Open Postman.
2. Set the HTTP method to **DELETE**.
3. Enter the URL `http://127.0.0.1:5000/items/2` (replace `2` with the task ID you want to delete).
4. Click **Send** to delete the task.

---

# Explanation of Flask Routes and `@app.route` Decorator

In Flask, routes are created using the **`@app.route`** decorator, which tells Flask to associate a function with a specific URL endpoint and HTTP method. Here's how it works:

### **`@app.route('/items', methods=['GET'])`:**

This route listens for **GET** requests on the `/items` endpoint. It fetches all items from the task list.

### **`@app.route('/items/<int:item_id>', methods=['GET'])`:**

This route listens for **GET** requests on the `/items/<item_id>` endpoint. It fetches a specific task using its ID (`item_id` is captured from the URL and passed to the function).

### **`@app.route('/items', methods=['POST'])`:**

This route listens for **POST** requests on the `/items` endpoint. It expects JSON data in the request body, which is used to create a new task.

### **`@app.route('/items/<int:item_id>', methods=['PUT'])`:**

This route listens for **PUT** requests on the `/items/<item_id>` endpoint. It updates the task with the given ID using the data in the request body.

### **`@app.route('/items/<int:item_id>', methods=['DELETE'])`:**

This route listens for **DELETE** requests on the `/items/<item_id>` endpoint. It deletes the task with the specified ID.

---

# Future Improvements

- **User Authentication & Authorization**:
  - Implement user login and personal task management with sessions or tokens.

- **Database Integration**:
  - Replace in-memory data storage with a relational database like SQLite or PostgreSQL.

- **Error Handling & Input Validation**:
  - Add detailed error messages and input validation to ensure only valid data is handled.

---

# Conclusion

This project is a great introduction to using Flask for creating simple REST APIs. By testing API requests using Postman, you can efficiently manage tasks and practice handling HTTP methods like **GET**, **POST**, **PUT**, and **DELETE**. The **`@app.route`** decorator simplifies URL endpoint management and binds specific functions to those endpoints, making it easier to handle API requests. As you move forward, you can extend this app with more features, like user authentication and database support, to create a robust task management tool for da

