# ChatApp API Documentation

Complete API reference for the ChatApp backend server.

## Base Information

- **Base URL**: `http://localhost:8000`
- **API Version**: v1.0.0
- **Authentication**: JWT Bearer Token
- **Content-Type**: `application/json` (unless specified otherwise)

## Authentication

Most endpoints require JWT authentication. Include the token in the Authorization header:

```http
Authorization: Bearer <your-jwt-token>
```

## Endpoints Overview

| Category | Endpoint | Method | Description |
|----------|----------|--------|-------------|
| Auth | `/register` | POST | Register new user |
| Auth | `/login` | POST | User login |
| Users | `/users/:userId` | GET | Get all users except current |
| Users | `/user/:userId` | GET | Get specific user details |
| Friends | `/friend-request` | POST | Send friend request |
| Friends | `/friend-requests/sent/:userId` | GET | Get sent friend requests |
| Friends | `/friend-request/:userId` | GET | Get received friend requests |
| Friends | `/friend-request/accept` | POST | Accept friend request |
| Friends | `/friends/:userId` | GET | Get user's friends |
| Messages | `/messages` | POST | Send message |
| Messages | `/messages/:senderId/:recepientId` | GET | Get messages between users |
| Messages | `/deleteMessages` | POST | Delete messages |

---

## Authentication Endpoints

### Register User

Register a new user account.

**Endpoint**: `POST /register`

**Request Body**:
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securepassword123",
  "image": "https://example.com/profile.jpg"
}
```

**Response**:
```json
{
  "message": "User registered successfully"
}
```

**Error Responses**:
- `400 Bad Request`: Missing required fields
- `409 Conflict`: Email already exists
- `500 Internal Server Error`: Server error

---

### Login User

Authenticate user and receive JWT token.

**Endpoint**: `POST /login`

**Request Body**:
```json
{
  "email": "john@example.com",
  "password": "securepassword123"
}
```

**Success Response**:
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "userId": "64a123b456c789d012e345f6"
}
```

**Error Responses**:
- `400 Bad Request`: Missing email or password
- `401 Unauthorized`: Invalid credentials
- `500 Internal Server Error`: Server error

---

## User Management Endpoints

### Get All Users

Get list of all users except the current user.

**Endpoint**: `GET /users/:userId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Parameters**:
- `userId` (path): Current user's ID to exclude from results

**Response**:
```json
[
  {
    "_id": "64a123b456c789d012e345f7",
    "name": "Jane Smith",
    "email": "jane@example.com",
    "image": "https://example.com/jane-profile.jpg",
    "friends": ["64a123b456c789d012e345f8"],
    "friendRequests": [],
    "sentFriendRequests": ["64a123b456c789d012e345f9"]
  }
]
```

---

### Get User Details

Get specific user information by ID.

**Endpoint**: `GET /user/:userId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Parameters**:
- `userId` (path): User ID to retrieve

**Response**:
```json
{
  "_id": "64a123b456c789d012e345f7",
  "name": "Jane Smith",
  "email": "jane@example.com",
  "image": "https://example.com/jane-profile.jpg",
  "friends": ["64a123b456c789d012e345f8"],
  "friendRequests": [],
  "sentFriendRequests": []
}
```

---

## Friend Request Endpoints

### Send Friend Request

Send a friend request to another user.

**Endpoint**: `POST /friend-request`

**Headers**:
```http
Authorization: Bearer <jwt-token>
Content-Type: application/json
```

**Request Body**:
```json
{
  "currentUserId": "64a123b456c789d012e345f6",
  "selectedUserId": "64a123b456c789d012e345f7"
}
```

**Response**:
```json
{
  "message": "Friend request sent successfully"
}
```

---

### Get Sent Friend Requests

Get all friend requests sent by the current user.

**Endpoint**: `GET /friend-requests/sent/:userId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Response**:
```json
[
  {
    "_id": "64a123b456c789d012e345f7",
    "name": "Jane Smith",
    "email": "jane@example.com",
    "image": "https://example.com/jane-profile.jpg"
  }
]
```

---

### Get Received Friend Requests

Get all friend requests received by the current user.

**Endpoint**: `GET /friend-request/:userId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Response**:
```json
[
  {
    "_id": "64a123b456c789d012e345f8",
    "name": "Bob Johnson",
    "email": "bob@example.com",
    "image": "https://example.com/bob-profile.jpg"
  }
]
```

---

### Accept Friend Request

Accept an incoming friend request.

**Endpoint**: `POST /friend-request/accept`

**Headers**:
```http
Authorization: Bearer <jwt-token>
Content-Type: application/json
```

**Request Body**:
```json
{
  "senderId": "64a123b456c789d012e345f7",
  "recepientId": "64a123b456c789d012e345f6"
}
```

**Response**:
```json
{
  "message": "Friend request accepted successfully"
}
```

---

### Get User's Friends

Get list of all friends for a specific user.

**Endpoint**: `GET /friends/:userId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Response**:
```json
[
  {
    "_id": "64a123b456c789d012e345f7",
    "name": "Jane Smith",
    "email": "jane@example.com",
    "image": "https://example.com/jane-profile.jpg"
  }
]
```

---

## Messaging Endpoints

### Send Message

Send a text or image message to another user.

**Endpoint**: `POST /messages`

**Headers**:
```http
Authorization: Bearer <jwt-token>
Content-Type: multipart/form-data
```

**Form Data**:
- `senderId`: Sender's user ID
- `recepientId`: Recipient's user ID  
- `messageType`: "text" or "image"
- `messageText`: Message content (for text messages)
- `imageFile`: Image file (for image messages)

**Example Request (Text Message)**:
```javascript
const formData = new FormData();
formData.append('senderId', '64a123b456c789d012e345f6');
formData.append('recepientId', '64a123b456c789d012e345f7');
formData.append('messageType', 'text');
formData.append('messageText', 'Hello, how are you?');
```

**Example Request (Image Message)**:
```javascript
const formData = new FormData();
formData.append('senderId', '64a123b456c789d012e345f6');
formData.append('recepientId', '64a123b456c789d012e345f7');
formData.append('messageType', 'image');
formData.append('imageFile', imageFile);
```

**Response**:
```json
{
  "message": "Message sent successfully"
}
```

---

### Get Messages Between Users

Retrieve all messages between two users.

**Endpoint**: `GET /messages/:senderId/:recepientId`

**Headers**: 
```http
Authorization: Bearer <jwt-token>
```

**Parameters**:
- `senderId` (path): First user's ID
- `recepientId` (path): Second user's ID

**Response**:
```json
[
  {
    "_id": "64a123b456c789d012e345f8",
    "senderId": "64a123b456c789d012e345f6",
    "recepientId": "64a123b456c789d012e345f7",
    "messageType": "text",
    "message": "Hello, how are you?",
    "timestamp": "2024-01-15T10:30:00.000Z",
    "imageUrl": null
  },
  {
    "_id": "64a123b456c789d012e345f9",
    "senderId": "64a123b456c789d012e345f7",
    "recepientId": "64a123b456c789d012e345f6",
    "messageType": "image",
    "message": "",
    "timestamp": "2024-01-15T10:35:00.000Z",
    "imageUrl": "files/1642248900000-123456789-image.jpg"
  }
]
```

---

### Delete Messages

Delete one or more messages.

**Endpoint**: `POST /deleteMessages`

**Headers**:
```http
Authorization: Bearer <jwt-token>
Content-Type: application/json
```

**Request Body**:
```json
{
  "messages": [
    "64a123b456c789d012e345f8",
    "64a123b456c789d012e345f9"
  ]
}
```

**Response**:
```json
{
  "message": "Messages deleted successfully"
}
```

---

## Data Models

### User Model

```javascript
{
  _id: ObjectId,
  name: String (required),
  email: String (required, unique),
  password: String (required),
  image: String (required),
  friendRequests: [ObjectId], // References to User
  friends: [ObjectId], // References to User
  sentFriendRequests: [ObjectId] // References to User
}
```

### Message Model

```javascript
{
  _id: ObjectId,
  senderId: ObjectId (required), // Reference to User
  recepientId: ObjectId (required), // Reference to User
  messageType: String (required), // "text" or "image"
  message: String, // Message content
  timestamp: Date (required),
  imageUrl: String // Path to image file
}
```

---

## Error Handling

### HTTP Status Codes

- `200 OK`: Request successful
- `400 Bad Request`: Invalid request data
- `401 Unauthorized`: Authentication required or invalid
- `403 Forbidden`: Access denied
- `404 Not Found`: Resource not found
- `409 Conflict`: Resource already exists
- `500 Internal Server Error`: Server error

### Error Response Format

```json
{
  "error": "Error message description",
  "details": "Additional error details (optional)"
}
```

### Common Error Messages

- `"User registration failed"`: Registration error
- `"Invalid email or password"`: Authentication error
- `"User not found"`: User doesn't exist
- `"Friend request already sent"`: Duplicate friend request
- `"Internal Server Error"`: Generic server error

---

## Rate Limiting

Currently, there are no rate limits implemented. This may be added in future versions for production deployment.

---

## CORS

CORS is enabled for all origins. In production, this should be restricted to specific domains.

---

## File Upload

- **Max file size**: No explicit limit (default Node.js/Express limits)
- **Supported formats**: All image formats
- **Storage location**: `files/` directory in backend
- **File naming**: `{timestamp}-{random}-{originalname}`

---

## Security Considerations

- Use HTTPS in production
- Implement rate limiting
- Validate and sanitize all inputs
- Store passwords with proper hashing
- Implement proper CORS policies
- Use environment variables for sensitive data
- Implement request size limits

---

## Testing the API

### Using cURL

**Register User**:
```bash
curl -X POST http://localhost:8000/register \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test User",
    "email": "test@example.com", 
    "password": "password123",
    "image": "https://example.com/avatar.jpg"
  }'
```

**Login**:
```bash
curl -X POST http://localhost:8000/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "test@example.com",
    "password": "password123"
  }'
```

### Using Postman

1. Import the endpoints into Postman
2. Set up environment variables for base URL and token
3. Use the JWT token in Authorization header for protected routes

---

## Version History

- **v1.0.0**: Initial API implementation
  - User authentication
  - Friend request system  
  - Basic messaging functionality
  - Image upload support