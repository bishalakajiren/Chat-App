# Chat App

## Overview

Chat App is a real-time messaging application that allows users to communicate with each other in a seamless and instant manner.

## Features

- Real-time messaging
- User authentication
- User profiles
- Chat

## Demo

You can try out the application at [http://34.131.61.34:3000/](http://34.131.61.34:3000/).

### API Documenatation

## Register User

- **Endpoint**: `/api/register`
- **Method**: `POST`
- **Description**: `Register a new user.`
- **Request Body**:
  ```json
  {
    "fullName": "John Doe",
    "email": "john@example.com",
    "password": "yourpassword"
  } 

# Success Response

- **Code**: `200 OK`
- **Content**: `User registered successfully`

# Error Response

- **Code**: `400 Bad Request`
- **Content**: `Please fill all required fields or User already exists`

## User Login

- **Endpoint**: `/api/login`
- **Method**: `POST`
- **Description**: `Log in an existing user.`
- **Request Body**:
  ```json
  {
    "email": "john@example.com",
    "password": "yourpassword"
  } 

# Success Response

- **Code**: `200 OK`
- **Content**: 
  ```json  
      {
        "user": {
        "id": "user_id",
        "email": "john@example.com",
        "fullName": "John Doe"
        },
        "token": "generated_jwt_token"
       }

# Error Response

- **Code**: `400 Bad Request`
- **Content**: `Please fill all required fields or User already exists`

## Create Conversation

- **Endpoint**: `/api/conversation`
- **Method**: `POST`
- **Description**: `Create a new conversation.`
- **Request Body**:

    ```json
    {
    "senderId": "sender_id",
    "receiverId": "receiver_id"
    }

# Success Response

- **Code**: `200 OK`
- **Content**: `Conversation created successfully`
 

# Error Response

- **Code**: `400 Bad Request`
- **Content**: `Please fill all required fields or User already exists`

# Success Response:
 - **Code**: `200 OK`
 - **Content**: `Conversation created successfully`

# Send Message

- **Endpoint**: `/api/message`
- **Method**: `POST`
- **Description**: `Create a new conversation.`
- **Request Body**:

   ```json
   { "conversationId": "conversation_id",
  "senderId": "sender_id",
  "receiverId": "receiver_id",
  "message": "Hello, how are you?"}
 
# Success Response:

- **Code**: `200 OK`
- **Content**: `Message sent successfully`

# Error Response:

# Error Response:

- **Code**: `400 Bad Request`
- **Content**: `Please fill all required fields`

# Get Conversations for a User

- **Endpoint**: `/api/conversations/:userId`
- **Method**: `GET`
- **Description**: `Retrieve conversations for a specific user.`
- **Parameters**:
  - `userId`: `User ID`
- **Success Response**:
  - **Code**: `200 OK`
  - **Content**: `List of conversations with associated users`

# Get Messages for a Conversation

- **Endpoint**: `/api/message/:conversationId`
- **Method**: `GET`
- **Description**: `Retrieve messages for a specific conversation.`
- **Parameters**:
  - `conversationId`: `Conversation ID`
- **Success Response**:
  - **Code**: `200 OK`
  - **Content**: `List of messages with associated users`

# Get Users (Excluding Current User)

- **Endpoint**: `/api/users/:userId`
- **Method**: `GET`
- **Description**: `Retrieve a list of users excluding the current user.`
- **Parameters**:
  - `userId`: `Current User ID`
- **Success Response**:
  - **Code**: `200 OK`
  - **Content**: `List of users`

---

## WebSockets

# Socket.io

- **Endpoint**: `/socket.io`
- **Description**: `Real-time messaging using WebSockets.`

---

## Usage Examples

### Registering a User

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "fullName": "John Doe",
  "email": "john@example.com",
  "password": "yourpassword"
}' http://34.131.61.34:8000/api/register

### Prerequisites

- Node.js and npm installed on your machine
- Internet connection
