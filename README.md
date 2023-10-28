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

# Getting Started

## 1. Clone the Repository
   
- Use any method to clone the repo from my GitHub account. if you don't know to clone it, simply download the code as zip file and unzip it.

## 2. Installation Process 
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

# 3. Set Up MongoDB Atlas

## Setting Up MongoDB Atlas and Remote Database Access

This guide will walk you through the steps to set up a MongoDB Atlas account and create a cluster for remote database access. MongoDB Atlas is a cloud-based database service that allows you to easily manage MongoDB databases.

## Table of Contents

- [Create a MongoDB Atlas Account](#create-a-mongodb-atlas-account)
- [Log in to Your MongoDB Atlas Account](#log-in-to-your-mongodb-atlas-account)
- [Create a New Project](#create-a-new-project)
- [Build a Cluster](#build-a-cluster)
- [Network Access](#network-access)
- [Database Access](#database-access)
- [Review & Deploy](#review--deploy)
- [Wait for Cluster Creation](#wait-for-cluster-creation)
- [Connect to Your Cluster](#connect-to-your-cluster)
- [Start Using Your Remote Database](#start-using-your-remote-database)

## Create a MongoDB Atlas Account

1. Go to the MongoDB Atlas website: [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Click the "Get started free" button.
3. Follow the registration process to create an account.

## Log in to Your MongoDB Atlas Account

Use the credentials you just created to log in to your MongoDB Atlas account.

## Create a New Project

After logging in, you will be prompted to create a new project. Projects help you organize your clusters and resources.

## Build a Cluster

1. In your project, click "Build a Cluster" to create a new cluster.
2. Configure your cluster by providing the following details:
   - Cluster Name: Choose a name for your cluster.
   - Cluster Tier: Select the cluster size (e.g., M0, M2, M10). The free M0 tier is suitable for testing and small projects.
   - Cloud Provider & Region: Choose a cloud provider (e.g., AWS, Azure, Google Cloud) and region where your cluster will be hosted.
   - Additional Settings: Customize options like backups, automated scaling, and the version of MongoDB.

## Network Access

1. Under the Security section, configure your network access.
2. Whitelist your IP address or choose to allow access from anywhere (not recommended for production).
3. You can also configure IP Whitelist entries to include multiple IP addresses or CIDR ranges if needed.

## Database Access

1. Under the Security section, create a database user and set a secure password.
2. Assign appropriate permissions to the user based on your application's requirements.

## Review & Deploy

1. Review your cluster configuration, including the cluster name, size, region, and security settings.
2. Click the "Create Cluster" button to deploy your cluster.

## Wait for Cluster Creation

It may take a few minutes to create your cluster. You can monitor the progress on the MongoDB Atlas dashboard.

## Connect to Your Cluster

Once your cluster is created, you'll be able to connect to it. MongoDB Atlas provides a connection string that you can use in your application code. You can also download drivers and connect using a MongoDB client.

## Start Using Your Remote Database

Update your application's database connection settings with the connection string provided by MongoDB Atlas. Your remote MongoDB database is now ready to use!

Remember to configure your application to use the provided connection string and the credentials you created. Additionally, MongoDB Atlas offers many features for monitoring, scaling, and managing your database, so be sure to explore the dashboard for more options as you develop your project.


## 4. Start the Backend Server

- open the new terminal in vs code and go to you project directory
- ``cd your_project_location`` hit enter
- ``cd api`` and hit enter again
- now, youre ready to start your project backend part🚀😼
- ``yarn start`` hit enter and boom
- if you see below img you're done doing everything.real chad 😎

![backend_ok](assets/img8.jpg)



## 5. Run the Application on Your Device(Starting Frontend part)

- if you do it everything correctly you have to execute one command only in here
- open the new terminal and go to you project directory
- ``cd C:\ReactNativeApps\chatapp`` | This is my directory for reference.
- ``npx expo start`` now you're ready to start app on your device

## Screenshots

Here are some screenshots that showcase the functionality of the React Native Chat App:

- Registration and Login Page

<img src="/assets/img1.jpg" alt="Calculator Interface" width="200" height="456"> .... <img src="/assets/img2.jpg" alt="Calculator Interface" width="200" height="456">

- Home Page

<img src="/assets/img7.jpg" alt="Calculator Interface" width="200" height="456">

- Chat Page and all Chats Page

<img src="/assets/img6.jpg" alt="Calculator Interface" width="200" height="456"> .... <img src="/assets/img5.jpg" alt="Calculator Interface" width="200" height="456">

- Same Chat page for 2 users side by side view

<img src="/assets/img3.jpg" alt="Calculator Interface" width="200" height="456"> .... <img src="/assets/img5.jpg" alt="Calculator Interface" width="200" height="456">

- Friend Request page

<img src="/assets/img4.jpg" alt="Calculator Interface" width="200" height="456">

## Contributing

I am welcome contributions to improve and expand this project. Feel free to submit pull requests, report issues, or suggest enhancements.

## Give a Star ⭐

Your support and feedback are highly valued, so if you find this project useful, consider giving it a star ⭐️. I appreciate your interest in my work.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
  

