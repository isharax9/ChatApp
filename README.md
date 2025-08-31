<div align="center">

# 💬 Cross Platform ChatApp

[![React Native](https://img.shields.io/badge/React%20Native-0.74.5-blue.svg)](https://reactnative.dev/)
[![Expo](https://img.shields.io/badge/Expo-52.0.11-black.svg)](https://expo.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.21.2-lightgrey.svg)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green.svg)](https://www.mongodb.com/atlas)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

*A modern, cross-platform real-time chat application built with React Native and Express.js*

[Features](#-features) • [Quick Start](#-quick-start) • [API Documentation](#-api-documentation) • [Screenshots](#-screenshots) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [🚀 Introduction](#-introduction)
- [✨ Features](#-features)
- [🏗️ Architecture](#️-architecture)
- [📋 Prerequisites](#-prerequisites)
- [🚀 Quick Start](#-quick-start)
- [⚙️ Installation Guide](#️-installation-guide)
- [🗄️ Database Setup](#️-database-setup)
- [📱 Running the Application](#-running-the-application)
- [🔌 API Documentation](#-api-documentation)
- [📱 App Structure](#-app-structure)
- [📸 Screenshots](#-screenshots)
- [🛠️ Troubleshooting](#️-troubleshooting)
- [🗺️ Roadmap](#️-roadmap)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [⭐ Support](#-support)

---

## 🚀 Introduction

**ChatApp** is a modern, cross-platform mobile chat application that brings people together through seamless real-time communication. Built with cutting-edge technologies like React Native and Express.js, this app provides a comprehensive social messaging experience with friend management, multimedia sharing, and intuitive user interactions.

### 🎯 What makes it special?
- **Cross-Platform**: Works seamlessly on both iOS and Android
- **Real-time Communication**: Instant messaging with live updates
- **Modern UI/UX**: Clean, intuitive interface designed for modern mobile users
- **Social Features**: Friend requests, user discovery, and social interactions
- **Multimedia Support**: Text, emojis, and image sharing capabilities
- **Secure Authentication**: JWT-based authentication system

## ✨ Features

### 👤 User Management
- **🔐 Secure Registration**: Create accounts with email, password, and profile picture
- **🔑 JWT Authentication**: Secure login system with token-based authentication
- **👥 User Discovery**: Browse and discover other users on the platform
- **🖼️ Profile Pictures**: Upload and display profile images via URL

### 🤝 Social Features
- **📬 Friend Requests**: Send, receive, accept, and decline friend requests
- **👫 Friend Management**: Manage your friend list and connections
- **🔍 User Search**: Find and connect with other users
- **📊 Friend Status**: Real-time updates on friendship status

### 💬 Real-Time Messaging
- **⚡ Instant Chat**: Real-time message exchange between friends
- **📝 Text Messages**: Send and receive text messages instantly
- **😊 Emoji Support**: Express yourself with a wide range of emojis
- **🖼️ Image Sharing**: Share images in conversations
- **⏰ Message Timestamps**: See when messages were sent and received

### 📱 User Interface
- **🎨 Modern Design**: Clean, intuitive mobile-first interface
- **🔄 Real-time Updates**: Live message updates without refresh
- **📋 Chat History**: Browse previous conversations and messages
- **🏠 Home Dashboard**: Overview of all users and friend requests
- **💬 Chat List**: Quick access to all ongoing conversations

### 🔧 Technical Features
- **📱 Cross-Platform**: Runs on both iOS and Android devices
- **☁️ Cloud Database**: MongoDB Atlas for reliable data storage
- **🔄 State Management**: Efficient React Context for app state
- **📐 Responsive Design**: Optimized for various screen sizes
- **🛡️ Secure API**: Protected endpoints with authentication middleware

## 🏗️ Architecture

### System Overview
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   React Native  │    │   Express.js    │    │  MongoDB Atlas  │
│   Frontend      │◄──►│   Backend API   │◄──►│   Database      │
│   (Expo)        │    │   (Node.js)     │    │   (Cloud)       │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Tech Stack

#### Frontend (Mobile App)
- **Framework**: React Native 0.74.5
- **Platform**: Expo 52.0.11
- **Navigation**: React Navigation 6.x
- **State Management**: React Context API
- **Authentication**: JWT with AsyncStorage
- **Image Handling**: Expo Image Picker
- **HTTP Client**: Axios

#### Backend (API Server)
- **Runtime**: Node.js 18+
- **Framework**: Express.js 4.21.2
- **Database ODM**: Mongoose 8.9.5
- **Authentication**: JWT + Passport.js
- **File Upload**: Multer 2.0.2
- **CORS**: Cross-Origin Resource Sharing enabled

#### Database & Storage
- **Database**: MongoDB Atlas (Cloud)
- **Image Storage**: Local file system (expandable to cloud storage)
- **Session Management**: JWT tokens

#### Development & Deployment
- **Package Manager**: Yarn
- **Process Manager**: Nodemon (development)
- **Version Control**: Git
- **Mobile Testing**: Expo Go app

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your development environment:

### System Requirements
- **Node.js** (version 18 or higher) - [Download](https://nodejs.org/)
- **Yarn** package manager - [Installation Guide](https://yarnpkg.com/getting-started/install)
- **Git** for version control - [Download](https://git-scm.com/)

### Development Tools
- **Expo CLI** - Install globally: `npm install -g @expo/cli`
- **Code Editor** - VS Code recommended
- **Mobile Device** with Expo Go app installed
  - [iOS App Store](https://apps.apple.com/app/expo-go/id982107779)
  - [Google Play Store](https://play.google.com/store/apps/details?id=host.exp.exponent)

### Cloud Services
- **MongoDB Atlas Account** - [Sign up free](https://www.mongodb.com/cloud/atlas)
- **Active Internet Connection** for database and real-time features

### Optional Tools
- **Android Studio** (for Android development)
- **Xcode** (for iOS development on macOS)
- **Postman** or similar API testing tool

## 🚀 Quick Start

Get up and running in less than 5 minutes:

```bash
# 1. Clone the repository
git clone https://github.com/isharax9/ChatApp.git
cd ChatApp

# 2. Install frontend dependencies
yarn install

# 3. Install backend dependencies
cd api
yarn install

# 4. Set up your MongoDB Atlas connection (see Database Setup section)

# 5. Start the backend server
yarn start

# 6. In a new terminal, start the frontend
cd ..
npx expo start
```

## ⚙️ Installation Guide

### Step 1: Clone the Repository

Choose one of the following methods:

**Method 1: Using Git (Recommended)**
```bash
git clone https://github.com/isharax9/ChatApp.git
cd ChatApp
```

**Method 2: Download ZIP**
- Download the code as a ZIP file from the GitHub repository
- Extract the ZIP file to your desired location
- Navigate to the project folder

### Step 2: Frontend Dependencies Installation

Open your first terminal in the project root directory:

```bash
# Navigate to project location
cd your_project_location

# Install Expo modules
npx install-expo-modules@latest

# Install main dependencies
yarn add react-native react-native-screens react-native-safe-area-context react-native-emoji-selector jsonwebtoken jwt-decode

# Install navigation dependencies
yarn add @react-navigation/native
yarn add @react-navigation/native-stack

# Install Expo-specific packages
npx expo install @react-native-async-storage/async-storage
npx expo install react-native-screens react-native-safe-area-context expo-image-picker

# Install additional packages
npm install cors
```

### Step 3: Backend Dependencies Installation

Open your second terminal and navigate to the API directory:

```bash
# Navigate to backend directory
cd your_project_location
cd api

# Install backend dependencies
yarn add express cors body-parser mongoose multer nodemon passport passport-local jsonwebtoken jwt-decode axios
```

### 📦 Complete Dependencies List

#### Frontend Dependencies
```json
{
  "@react-native-async-storage/async-storage": "1.23.1",
  "@react-navigation/native": "^6.1.8",
  "@react-navigation/native-stack": "^6.9.14",
  "axios": "^1.8.2",
  "cors": "^2.8.5",
  "expo": "^52.0.11",
  "expo-image-picker": "~15.0.7",
  "expo-status-bar": "~1.12.1",
  "jsonwebtoken": "^9.0.2",
  "jwt-decode": "^3.1.2",
  "react": "18.2.0",
  "react-native": "0.74.5",
  "react-native-emoji-selector": "^0.2.0",
  "react-native-safe-area-context": "4.10.5",
  "react-native-screens": "3.31.1"
}
```

#### Backend Dependencies
```json
{
  "express": "^4.21.2",
  "cors": "^2.8.5",
  "body-parser": "^1.20.2",
  "mongoose": "^8.9.5",
  "multer": "^2.0.2",
  "nodemon": "^3.0.1",
  "passport": "^0.6.0",
  "passport-local": "^1.0.0",
  "jsonwebtoken": "^9.0.0",
  "axios": "^1.8.2"
}
```

## 🗄️ Database Setup

### Setting Up MongoDB Atlas and Remote Database Access

This comprehensive guide will walk you through setting up MongoDB Atlas, a cloud-based database service, for your ChatApp project.

#### 📚 Table of Contents
- [Create MongoDB Atlas Account](#create-a-mongodb-atlas-account)
- [Login to Your Account](#log-in-to-your-mongodb-atlas-account)
- [Create New Project](#create-a-new-project)
- [Build a Cluster](#build-a-cluster)
- [Configure Network Access](#network-access)
- [Set Up Database Access](#database-access)
- [Review & Deploy](#review--deploy)
- [Connect to Your Cluster](#connect-to-your-cluster)
- [Configure Application](#start-using-your-remote-database)

### Create a MongoDB Atlas Account

1. **Visit MongoDB Atlas**: Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. **Sign Up**: Click the "Get started free" button
3. **Complete Registration**: Follow the registration process with your email and password
4. **Verify Email**: Check your email for verification link and activate your account

### Log in to Your MongoDB Atlas Account

Use the credentials you created to access your MongoDB Atlas dashboard.

### Create a New Project

1. **Dashboard**: After logging in, you'll see the project dashboard
2. **New Project**: Click "Create a New Project" 
3. **Project Name**: Give your project a meaningful name (e.g., "ChatApp-Production")
4. **Add Members**: Optionally add team members if working collaboratively

### Build a Cluster

1. **Create Cluster**: In your project, click "Build a Cluster"
2. **Choose Tier**: 
   - **Free Tier (M0)**: Perfect for development and testing
   - **Paid Tiers**: For production with more storage and features
3. **Cloud Provider**: Choose your preferred provider:
   - **AWS** (recommended for global coverage)
   - **Google Cloud Platform**
   - **Microsoft Azure**
4. **Region**: Select the region closest to your users
5. **Cluster Name**: Give your cluster a descriptive name

#### Cluster Configuration Options:
```yaml
Cluster Tier: M0 Sandbox (Free)
Cloud Provider: AWS
Region: us-east-1 (or nearest to you)
MongoDB Version: 7.0 (latest stable)
```

### Network Access

**Security Configuration:**

1. **IP Whitelist**: Navigate to "Network Access" in the left sidebar
2. **Add IP Address**: Click "Add IP Address"
3. **Options**:
   - **Current IP**: Add your current IP address
   - **Allow Access from Anywhere**: `0.0.0.0/0` (⚠️ **Not recommended for production**)
   - **Custom IP**: Add specific IP addresses or CIDR ranges

**Recommended Setup for Development:**
```
IP Address: 0.0.0.0/0 (Allow access from anywhere)
Comment: Development Access
```

**Production Setup:**
```
IP Address: Your-Server-IP/32
Comment: Production Server Access
```

### Database Access

**Create Database User:**

1. **Navigate**: Go to "Database Access" in the left sidebar
2. **Add User**: Click "Add New Database User"
3. **Authentication Method**: Choose "Password"
4. **Username**: Create a username (e.g., `chatapp-user`)
5. **Password**: Generate a secure password (save this securely!)
6. **Database User Privileges**: 
   - **Built-in Role**: `readWriteAnyDatabase` (recommended)
   - **Custom Role**: For fine-grained permissions

**Example User Configuration:**
```yaml
Username: chatapp-admin
Password: [Generated-Secure-Password]
Database: admin
Roles: readWriteAnyDatabase
```

### Review & Deploy

1. **Review Settings**: Double-check your cluster configuration
   - Cluster name and tier
   - Region and cloud provider
   - Security settings
2. **Create Cluster**: Click "Create Cluster"
3. **Wait for Deployment**: Cluster creation takes 3-7 minutes

### Wait for Cluster Creation

Monitor the progress on your dashboard. You'll see:
- ⏳ Cluster creation in progress
- ✅ Cluster ready and available

### Connect to Your Cluster

Once your cluster is ready:

1. **Connect Button**: Click "Connect" on your cluster
2. **Connection Method**: Choose "Connect your application"
3. **Driver**: Select "Node.js" and your version
4. **Connection String**: Copy the provided connection string

**Example Connection String:**
```javascript
mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/<database>?retryWrites=true&w=majority
```

### Start Using Your Remote Database

**Configure Your Application:**

1. **Update Backend**: Open `/api/index.js`
2. **Replace Connection String**: Update the MongoDB connection
3. **Add Your Credentials**: Replace `<username>`, `<password>`, and `<database>`

**Example Configuration:**
```javascript
mongoose.connect(
  "mongodb+srv://chatapp-admin:yourpassword@cluster0.xxxxx.mongodb.net/chatapp?retryWrites=true&w=majority",
  {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  }
);
```

**Environment Variables (Recommended):**
Create a `.env` file in your `/api` directory:
```env
MONGODB_URI=mongodb+srv://chatapp-admin:yourpassword@cluster0.xxxxx.mongodb.net/chatapp?retryWrites=true&w=majority
JWT_SECRET=your-super-secret-jwt-key
PORT=8000
```

### 🔒 Security Best Practices

- **Never commit credentials** to version control
- **Use environment variables** for sensitive data
- **Enable IP whitelisting** for production
- **Create separate clusters** for development and production
- **Regular password rotation** for database users
- **Monitor database access** through Atlas dashboard

### 📊 MongoDB Atlas Features

Explore additional Atlas features:
- **Real-time Performance Advisor**
- **Automated Backups**
- **Performance Monitoring**
- **Data Lake Integration**
- **Charts for Data Visualization**


## 📱 Running the Application

### Step 1: Start the Backend Server

**Terminal 1 - Backend Setup:**
```bash
# Navigate to project directory
cd your_project_location

# Enter API directory
cd api

# Start the backend server
yarn start
```

**Expected Output:**
```
[nodemon] starting `node index.js`
Server running on port 8000
Connected to Mongo Db
```

If you see the above output, your backend is running successfully! 🎉

![Backend Success](assets/img8.jpg)

### Step 2: Start the Frontend Application

**Terminal 2 - Frontend Setup:**
```bash
# Navigate to project root (if you're in api folder)
cd your_project_location

# Start the Expo development server
npx expo start
```

**Expected Output:**
```
› Metro waiting on exp://192.168.x.x:19000
› Scan the QR code above with Expo Go (Android) or the Camera app (iOS)
```

### Step 3: Run on Your Device

#### Option 1: Using Expo Go (Recommended for beginners)
1. **Install Expo Go** on your mobile device:
   - [iOS App Store](https://apps.apple.com/app/expo-go/id982107779)
   - [Google Play Store](https://play.google.com/store/apps/details?id=host.exp.exponent)

2. **Connect to Same Network**: Ensure your computer and mobile device are on the same WiFi network

3. **Scan QR Code**: Open Expo Go and scan the QR code from your terminal

#### Option 2: Using Emulator/Simulator
**Android Emulator:**
```bash
# Press 'a' in the terminal to open Android emulator
npx expo start --android
```

**iOS Simulator (macOS only):**
```bash
# Press 'i' in the terminal to open iOS simulator
npx expo start --ios
```

### 🔧 Development Commands

| Command | Description |
|---------|-------------|
| `npx expo start` | Start development server |
| `npx expo start --android` | Open in Android emulator |
| `npx expo start --ios` | Open in iOS simulator |
| `npx expo start --web` | Open in web browser |
| `npx expo start --clear` | Clear Metro bundler cache |
| `npx expo install` | Install Expo-compatible packages |

### 🌐 Network Configuration

**Important**: Update the IP addresses in the app to match your development environment:

**Files to update:**
- `/screens/HomeScreen.js`
- `/screens/LoginScreen.js`
- `/screens/RegisterScreen.js`
- `/components/User.js`

**Find and replace:**
```javascript
// Current IP (example)
http://192.168.253.12:8000

// Replace with your local IP
http://YOUR_LOCAL_IP:8000
```

**Find your local IP:**
```bash
# Windows
ipconfig

# macOS/Linux
ifconfig | grep "inet "
```

## 🔌 API Documentation

### Base URL
```
http://localhost:8000
```

### Authentication
Most endpoints require JWT authentication. Include the token in the Authorization header:
```
Authorization: Bearer <your-jwt-token>
```

### API Endpoints

#### 🔐 Authentication Endpoints

##### Register User
```http
POST /register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securepassword",
  "image": "https://example.com/profile.jpg"
}
```

**Response:**
```json
{
  "message": "User registered successfully"
}
```

##### Login User
```http
POST /login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "securepassword"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "userId": "64a123b456c789d012e345f6"
}
```

#### 👥 User Management Endpoints

##### Get All Users (except current user)
```http
GET /users/:userId
Authorization: Bearer <token>
```

**Response:**
```json
[
  {
    "_id": "64a123b456c789d012e345f7",
    "name": "Jane Smith",
    "email": "jane@example.com",
    "image": "https://example.com/jane-profile.jpg",
    "friends": [],
    "friendRequests": []
  }
]
```

##### Get User Details
```http
GET /user/:userId
Authorization: Bearer <token>
```

#### 🤝 Friend Request Endpoints

##### Send Friend Request
```http
POST /friend-request
Content-Type: application/json
Authorization: Bearer <token>

{
  "currentUserId": "64a123b456c789d012e345f6",
  "selectedUserId": "64a123b456c789d012e345f7"
}
```

##### Get Sent Friend Requests
```http
GET /friend-requests/sent/:userId
Authorization: Bearer <token>
```

##### Get Received Friend Requests
```http
GET /friend-request/:userId
Authorization: Bearer <token>
```

##### Accept Friend Request
```http
POST /friend-request/accept
Content-Type: application/json
Authorization: Bearer <token>

{
  "senderId": "64a123b456c789d012e345f7",
  "recepientId": "64a123b456c789d012e345f6"
}
```

##### Get User's Friends
```http
GET /friends/:userId
Authorization: Bearer <token>
```

#### 💬 Messaging Endpoints

##### Send Message
```http
POST /messages
Content-Type: multipart/form-data
Authorization: Bearer <token>

FormData:
- senderId: "64a123b456c789d012e345f6"
- recepientId: "64a123b456c789d012e345f7"
- messageType: "text" | "image"
- messageText: "Hello, how are you?"
- imageFile: [File] (optional, for image messages)
```

##### Get Messages Between Users
```http
GET /messages/:senderId/:recepientId
Authorization: Bearer <token>
```

**Response:**
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
  }
]
```

##### Delete Message
```http
POST /deleteMessages
Content-Type: application/json
Authorization: Bearer <token>

{
  "messages": ["64a123b456c789d012e345f8"]
}
```

### Error Responses

All endpoints return appropriate HTTP status codes:

- `200` - Success
- `400` - Bad Request
- `401` - Unauthorized
- `404` - Not Found
- `500` - Internal Server Error

**Error Response Format:**
```json
{
  "error": "Error message description"
}
```

## 📱 App Structure

### Frontend Architecture

```
ChatApp/
├── App.js                 # Main app component
├── StackNavigator.js      # Navigation configuration
├── UserContext.js         # Global state management
├── components/            # Reusable components
│   ├── User.js           # User list item component
│   ├── UserChat.js       # Chat list item component
│   └── FriendRequest.js  # Friend request component
├── screens/              # App screens
│   ├── LoginScreen.js    # User authentication
│   ├── RegisterScreen.js # User registration
│   ├── HomeScreen.js     # User discovery
│   ├── FriendsScreen.js  # Friend requests
│   ├── ChatsScreen.js    # Chat list
│   └── ChatMessagesScreen.js # Individual chat
└── assets/               # Images and static files
```

### Backend Architecture

```
api/
├── index.js              # Main server file
├── models/               # Database models
│   ├── user.js          # User model schema
│   └── message.js       # Message model schema
├── files/               # Uploaded images storage
└── package.json         # Backend dependencies
```

### Key Components

#### 🔄 State Management
- **UserContext**: Global state for user authentication and data
- **AsyncStorage**: Persistent storage for JWT tokens
- **React Navigation**: Screen navigation and routing

#### 🎨 UI Components
- **Custom Components**: Reusable UI elements for users, chats, and requests
- **Native Elements**: React Native built-in components
- **Expo Vector Icons**: Icon library for UI enhancement

#### 🔐 Security Features
- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: Secure password storage (if implemented)
- **Input Validation**: Client and server-side validation

## 📸 Screenshots

Here are some screenshots that showcase the functionality and user interface of the ChatApp:

### 🔐 Authentication Screens

<div align="center">

**Login & Registration Pages**

<img src="/assets/img1.jpg" alt="Login Screen" width="250" height="456"> &nbsp;&nbsp;&nbsp;&nbsp; <img src="/assets/img2.jpg" alt="Registration Screen" width="250" height="456">

*Clean and intuitive authentication interface for secure user login and registration*

</div>

### 🏠 Home & User Discovery

<div align="center">

**Home Page - User Discovery**

<img src="/assets/img7.jpg" alt="Home Screen" width="250" height="456">

*Browse and discover other users, send friend requests, and manage connections*

</div>

### 💬 Chat Interface

<div align="center">

**Chat List & Individual Chat**

<img src="/assets/img6.jpg" alt="Chat List" width="250" height="456"> &nbsp;&nbsp;&nbsp;&nbsp; <img src="/assets/img5.jpg" alt="Chat Messages" width="250" height="456">

*Overview of all conversations and detailed chat interface with real-time messaging*

</div>

### 🗨️ Real-Time Messaging

<div align="center">

**Conversation View - Both Users**

<img src="/assets/img3.jpg" alt="User 1 Chat View" width="250" height="456"> &nbsp;&nbsp;&nbsp;&nbsp; <img src="/assets/img5.jpg" alt="User 2 Chat View" width="250" height="456">

*Side-by-side view showing real-time message synchronization between users*

</div>

### 🤝 Friend Management

<div align="center">

**Friend Request Interface**

<img src="/assets/img4.jpg" alt="Friend Requests" width="250" height="456">

*Manage incoming and outgoing friend requests with easy accept/decline options*

</div>

### ✨ Key UI Features

- **🎨 Modern Design**: Clean, Material Design-inspired interface
- **📱 Mobile-First**: Optimized for mobile devices with touch-friendly interactions
- **⚡ Real-Time Updates**: Live message updates and status changes
- **🌈 Intuitive Navigation**: Easy-to-use navigation between different app sections
- **😊 Emoji Support**: Express yourself with integrated emoji picker
- **🖼️ Image Sharing**: Send and receive images seamlessly
- **🔄 Status Indicators**: Real-time friend status and message delivery confirmation

## 🛠️ Troubleshooting

### Common Issues and Solutions

#### 🔴 Backend Connection Issues

**Problem**: Cannot connect to backend server
```
Network Error: Unable to connect to server
```

**Solutions:**
1. **Check Backend Status**: Ensure backend is running on port 8000
   ```bash
   cd api
   yarn start
   ```

2. **Verify IP Address**: Update IP addresses in frontend files
   ```javascript
   // Update these files with your local IP:
   // - screens/HomeScreen.js
   // - screens/LoginScreen.js  
   // - screens/RegisterScreen.js
   // - components/User.js
   
   const API_URL = "http://YOUR_LOCAL_IP:8000";
   ```

3. **Network Connectivity**: Ensure device and computer are on same WiFi network

#### 🔴 Database Connection Issues

**Problem**: MongoDB connection errors
```
Error connecting to MongoDb
```

**Solutions:**
1. **Check Connection String**: Verify MongoDB Atlas connection string
2. **IP Whitelist**: Ensure your IP is whitelisted in MongoDB Atlas
3. **Credentials**: Verify username and password in connection string
4. **Network Access**: Check if your firewall allows MongoDB connections

#### 🔴 Expo/React Native Issues

**Problem**: Metro bundler errors or module resolution issues

**Solutions:**
1. **Clear Cache**: 
   ```bash
   npx expo start --clear
   ```

2. **Reinstall Dependencies**:
   ```bash
   rm -rf node_modules
   yarn install
   ```

3. **Reset Expo Cache**:
   ```bash
   expo r -c
   ```

4. **Check Node Version**: Ensure Node.js version is 18+

#### 🔴 Authentication Issues

**Problem**: Login/Registration not working

**Solutions:**
1. **Check API Endpoints**: Verify backend routes are accessible
2. **JWT Token**: Ensure JWT secret is configured in backend
3. **Password Validation**: Check password requirements
4. **Email Format**: Verify email format is valid

#### 🔴 Image Upload Issues

**Problem**: Images not uploading or displaying

**Solutions:**
1. **Check Permissions**: Ensure app has camera/gallery permissions
2. **File Size**: Verify image file size limits
3. **File Path**: Check file storage path in backend (`files/` directory)
4. **Multer Configuration**: Verify multer setup for file uploads

### 📱 Device-Specific Issues

#### iOS Issues
- **Simulator**: Use iOS Simulator for testing on macOS
- **Physical Device**: Ensure iOS device is on same network
- **Permissions**: Grant camera and photo library permissions

#### Android Issues  
- **Emulator**: Set up Android Studio emulator
- **Physical Device**: Enable USB debugging for physical device testing
- **Network**: Check Android firewall settings

### 🔧 Development Tips

1. **Hot Reload**: Use Expo's hot reload for faster development
2. **Error Boundaries**: Implement error boundaries for better error handling
3. **Logging**: Use console.log for debugging API calls
4. **Network Inspector**: Use Flipper or React Native Debugger for network monitoring

### 📞 Getting Help

If you encounter issues not covered here:

1. **Check Console**: Look for error messages in terminal and device console
2. **GitHub Issues**: Search existing issues in the repository
3. **Expo Documentation**: Check [Expo docs](https://docs.expo.dev/) for platform-specific issues
4. **React Native Community**: Visit [React Native community](https://reactnative.dev/help) for help

## 🗺️ Roadmap

### Current Version (v1.0.0)
- ✅ User authentication and registration
- ✅ Friend request system
- ✅ Real-time text messaging
- ✅ Image sharing capabilities
- ✅ Cross-platform mobile support

### Upcoming Features (v1.1.0)
- 🔄 **Message Editing**: Edit sent messages
- 🔄 **Message Reactions**: React to messages with emojis
- 🔄 **Typing Indicators**: Show when users are typing
- 🔄 **Online Status**: Display user online/offline status
- 🔄 **Push Notifications**: Real-time notifications for new messages

### Future Enhancements (v1.2.0+)
- 📝 **Group Chats**: Create and manage group conversations
- 🔊 **Voice Messages**: Send and receive voice recordings
- 🎥 **Video Calls**: Integrate video calling functionality
- 🌙 **Dark Mode**: Dark theme support
- 🔍 **Message Search**: Search through chat history
- 📎 **File Sharing**: Share documents and files
- 🔒 **End-to-End Encryption**: Enhanced security for messages
- 🌐 **Web Version**: Progressive Web App (PWA) support
- 🤖 **Chatbots**: AI-powered chat assistants
- 📊 **Analytics Dashboard**: Admin dashboard for app analytics

### Long-term Vision (v2.0.0+)
- 🎮 **Mini Games**: Interactive games within chat
- 💰 **In-App Purchases**: Premium features and customizations
- 🌍 **Multi-language Support**: Internationalization
- 🔔 **Advanced Notifications**: Smart notification preferences
- 📱 **Desktop App**: Native desktop applications
- ☁️ **Cloud Storage**: Cloud-based file storage integration
- 🎨 **Themes & Customization**: User-customizable themes

### Contributing to the Roadmap
We welcome community input on our roadmap! Please:
- Open an issue to suggest new features
- Vote on existing feature requests
- Submit pull requests for features you'd like to implement

## 🤝 Contributing

We welcome and appreciate contributions from the community! Whether you're fixing bugs, adding new features, improving documentation, or suggesting enhancements, your contributions help make ChatApp better for everyone.

### 🌟 Ways to Contribute

- 🐛 **Report Bugs**: Found a bug? Help us fix it by reporting it
- ✨ **Suggest Features**: Have an idea for a new feature? We'd love to hear it
- 📖 **Improve Documentation**: Help make our docs clearer and more comprehensive
- 🔧 **Submit Code**: Fix bugs or implement new features
- 🎨 **UI/UX Improvements**: Enhance the user interface and experience
- 🧪 **Add Tests**: Help improve code coverage and reliability

### 📝 Contribution Guidelines

#### Before You Start
1. **Check Existing Issues**: Look through existing issues and pull requests
2. **Open an Issue**: For major changes, open an issue first to discuss your idea
3. **Fork the Repository**: Create your own fork of the project

#### Development Process
1. **Create a Branch**: 
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/bug-description
   ```

2. **Make Your Changes**: 
   - Follow the existing code style and conventions
   - Add comments for complex logic
   - Ensure your code is clean and readable

3. **Test Your Changes**:
   - Test the app thoroughly on both iOS and Android
   - Verify that existing functionality still works
   - Add tests for new features when possible

4. **Commit Your Changes**:
   ```bash
   git add .
   git commit -m "feat: add new message reaction feature"
   # Use conventional commit format:
   # feat: new features
   # fix: bug fixes  
   # docs: documentation changes
   # style: code style changes
   # refactor: code refactoring
   # test: adding tests
   ```

5. **Push and Create PR**:
   ```bash
   git push origin feature/your-feature-name
   ```
   Then create a Pull Request on GitHub

#### Code Standards
- **JavaScript/React Native**: Follow ESLint rules and React best practices
- **File Naming**: Use PascalCase for components, camelCase for utilities
- **Comments**: Add meaningful comments for complex logic
- **Error Handling**: Include proper error handling and user feedback

#### Pull Request Guidelines
- **Clear Title**: Use descriptive titles for your PRs
- **Detailed Description**: Explain what your PR does and why
- **Screenshots**: Include screenshots for UI changes
- **Link Issues**: Reference related issues with "Closes #issue-number"
- **Small PRs**: Keep PRs focused and reasonably sized

### 🐛 Reporting Bugs

When reporting bugs, please include:

**Bug Report Template:**
```markdown
**Bug Description**
Clear description of the bug

**Steps to Reproduce**
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected Behavior**
What you expected to happen

**Screenshots**
If applicable, add screenshots

**Environment:**
- Device: [e.g. iPhone 12, Samsung Galaxy S21]
- OS: [e.g. iOS 15.0, Android 11]
- App Version: [e.g. 1.0.0]
- Node Version: [e.g. 18.0.0]
```

### 💡 Suggesting Features

**Feature Request Template:**
```markdown
**Feature Description**
Clear description of the feature

**Use Case**
Why would this feature be useful?

**Proposed Solution**
How do you envision this working?

**Alternatives Considered**
Other solutions you've considered

**Additional Context**
Any other context, mockups, or examples
```

### 🏗️ Development Setup

1. **Fork & Clone**:
   ```bash
   git clone https://github.com/yourusername/ChatApp.git
   cd ChatApp
   ```

2. **Install Dependencies**:
   ```bash
   # Frontend
   yarn install
   
   # Backend  
   cd api
   yarn install
   ```

3. **Set Up Environment**:
   - Configure MongoDB Atlas connection
   - Update IP addresses for local development
   - Set up any required environment variables

4. **Start Development**:
   ```bash
   # Terminal 1: Backend
   cd api
   yarn start
   
   # Terminal 2: Frontend
   npx expo start
   ```

### 🧪 Testing

While we're working on comprehensive test coverage, please manually test:
- **Core Features**: Authentication, messaging, friend requests
- **Cross-Platform**: Test on both iOS and Android
- **Edge Cases**: Network errors, invalid inputs, empty states
- **Performance**: App responsiveness and memory usage

### 👥 Community

- **Discord/Slack**: Join our community discussions (coming soon)
- **GitHub Discussions**: Use GitHub Discussions for questions and ideas
- **Code Reviews**: Participate in code reviews to help maintain quality

### 🎯 Good First Issues

Looking for a place to start? Check out issues labeled:
- `good first issue` - Perfect for newcomers
- `help wanted` - We'd love community help with these
- `documentation` - Improve our docs
- `bug` - Fix known issues

### 🙏 Recognition

Contributors will be:
- Listed in our README.md
- Recognized in release notes for significant contributions
- Invited to join our contributor community

Thank you for considering contributing to ChatApp! Every contribution, no matter how small, helps make the project better. 🎉

## ⭐ Support

### 🌟 Give a Star

If you find this project useful, please consider giving it a star ⭐️ on GitHub! Your support means a lot and helps others discover the project.

**Why star this project?**
- 📈 **Show Support**: Help us gauge community interest
- 🔍 **Increase Visibility**: Help others find this useful project
- 💪 **Motivate Development**: Encourage continued development and improvements
- 🤝 **Build Community**: Join our growing community of developers

### 📢 Share the Project

Help spread the word about ChatApp:
- 🐦 **Share on Twitter**: Tweet about the project with #ChatApp #ReactNative
- 💼 **LinkedIn**: Share with your professional network
- 📱 **Dev Communities**: Share on Reddit, Dev.to, or other developer communities
- 👥 **Tell Friends**: Recommend to fellow developers

### 💝 Support the Project

- ⭐ **Star the Repository**: Free and helps with discoverability
- 🐛 **Report Issues**: Help us improve by reporting bugs
- 🤝 **Contribute Code**: Submit pull requests with improvements
- 📖 **Improve Docs**: Help make documentation better
- 💡 **Share Ideas**: Suggest new features and enhancements

### 📬 Stay Connected

- **GitHub**: Follow this repository for updates
- **Issues**: Watch for discussions and announcements
- **Releases**: Get notified about new versions

Your support and feedback are highly valued! Together, we can make ChatApp an even better communication platform. 🚀

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### MIT License Summary

✅ **You CAN**:
- Use this project for personal and commercial purposes
- Modify and distribute the code
- Include in private projects
- Sublicense and sell

❗ **You MUST**:
- Include the original license and copyright notice
- Not hold the authors liable for any damages

### Copyright Notice

```
MIT License

Copyright (c) 2024 isharax9

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

### 💬 ChatApp - Connecting People, Simplifying Communication

**Made with ❤️ by [isharax9](https://github.com/isharax9)**

[⭐ Star this project](https://github.com/isharax9/ChatApp) • [🐛 Report Bug](https://github.com/isharax9/ChatApp/issues) • [💡 Request Feature](https://github.com/isharax9/ChatApp/issues)

</div>
  

