# Cross Platform ChatApp

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The React Native Chat App is a mobile application that allows users to connect, chat, and interact with each other. It offers a user-friendly interface with features such as registration, profile picture uploads, friend requests, and real-time chat capabilities.

## Features

### User Registration
- Users can create an account by providing their information, including username, email, and password.
- The registration process also allows users to upload a profile picture using a photo URL.

### Authentication
- Users can log in to their accounts using their registered email and password.

### Home Page
- The home page displays a list of all registered members.
- Users can send friend requests to other members and accept or decline incoming requests.

### Real-Time Chat
- Once two users become friends, they can engage in real-time chat conversations.
- The home chat page displays all ongoing conversations with the last message received and a brief preview with time it received or sent.

### Chatting Page
- Within individual chat conversations, users can exchange text messages with real-time updates.
- The chat supports text, images, and emojis.

### Message Editing and Deletion
- Users have the ability to delete messages.
- Message editing functionality is under development.

## Prerequisites

Before you begin, make sure you have the following prerequisites installed on your development environment:

- Node.js
- Expo CLI
- Yarn
- MongoDB Atlas account
- Expo Go installed on your mobile device

## Getting Started

1. Clone the Repository
   
- Use any method to clone the repo from my GitHub account. if you don't know to clone it, simply download the code as zip file and unzip it.

2. Installation Process 
- Open 2 terminals in your code editor.First One is for frontend and other is for backend
- **adding dependencies to Frontend** :-
- ``cd projectlocation``
- ``npx install-expo-modules@latest``
- ```npx expo start```
- ``npm install cors``
- ``yarn add react-native react-native-screens react-native-safe-area-context react-native-emoji-selector jsonwebtoken jwt-decode``
- ```yarn add @react-navigation/native```
- ``yarn add @react-navigation/native-stack``
- ``npx expo install @react-native-async-storage/async-storage``
- ```npx expo install react-native-screens react-native-safe-area-context expo-image-picker```
- **adding dependencies to Backend** :-
- ```cd projectlocation => cd api```
- ```yarn add express cors body-parser mongoose multer nodemon passport passport-local jsonwebtoken jwt-decode axios```
3. Set Up MongoDB Atlas


4. Start the Development Server


5. Run the Application on Your Device


## Screenshots

Here are some screenshots that showcase the functionality of the React Native Chat App:

- Registration Page
- Home Page
- Chat Page
- Message Editing (Work in Progress)

## Contributing

We welcome contributions to improve and expand this project. Feel free to submit pull requests, report issues, or suggest enhancements.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
  

