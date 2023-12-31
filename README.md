# A Simple REST API for TODO

A REST API with the following Methods GET,POST and DELETE.

## Installation  

1. Create Virtualenv and Activate it:

   
         python -m venv venv
         venv\Scripts\activate
   
2. Install Django and Django REST framework:

         
          pip install django djangorestframework

3. Navigate to your Django project directory (walterproject):

          cd /change/to/your/path/walterproject
    
4. Run the Django development server:
   
   ```
   python manage.py runserver

## API Documentation

### Authentication - Obtain an Authentication Token

### Request

- **Method:** POST
- **URL:** `http://localhost:8000/api-token-auth/`
- **Headers:** No specific headers are required.
- **Body:**

  ```
  {
      "username": "your_username",
      "password": "your_password"
  }


### Response
   
    Status Code: 200 OK
    Response Body:
    {
      "token": "9893763653790gdnu79"
    }



## GET Method - Retrieve Tasks

    
        Request
        Method: GET
        URL: http://localhost:8000/api/tasks/
        Headers:
        Key: Authorization
        Value: Token your_auth_token_here
        Response
        Status Code: 200 OK
        Response Body: A JSON array containing the list of tasks.
        
## POST Method - Create a Task

    
        Request
        Method: POST
        URL: http://localhost:8000/api/tasks/
        Headers:
        Key: Authorization
        Value: Token your_auth_token_here
        Body:
        {
            "title": "New Task Title",
            "description": "Description of the new task",
            "completed": false
        }
        
## DELETE Method - Delete a Task

    
        Request
        Method: DELETE
        URL: http://localhost:8000/api/tasks/<task_id>/
        Headers:
        Key: Authorization
        Value: Token your_auth_token_here
        Response
        Status Code: 204 No Content 
