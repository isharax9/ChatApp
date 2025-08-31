# Quick Setup Guide

Get ChatApp running in 5 minutes! 🚀

## Prerequisites ✅
- [Node.js 18+](https://nodejs.org/) installed
- [Yarn](https://yarnpkg.com/) package manager
- [Expo CLI](https://docs.expo.dev/get-started/installation/) installed
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) account
- Mobile device with [Expo Go](https://expo.dev/client) app

## Step 1: Clone & Install 📥
```bash
# Clone repository
git clone https://github.com/isharax9/ChatApp.git
cd ChatApp

# Install frontend dependencies
yarn install

# Install backend dependencies
cd api
yarn install
cd ..
```

## Step 2: Database Setup 🗄️
1. Create [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) account
2. Create a new cluster (free M0 tier works)
3. Get your connection string
4. Update `api/index.js` with your MongoDB URI:
```javascript
mongoose.connect("YOUR_MONGODB_CONNECTION_STRING", {
  useNewUrlParser: true,
  useUnifiedTopology: true,
});
```

## Step 3: Update Network Configuration 🌐
Update the IP address in these files with your local IP:
- `screens/HomeScreen.js`
- `screens/LoginScreen.js`
- `screens/RegisterScreen.js`
- `components/User.js`

Find your local IP:
```bash
# Windows
ipconfig

# Mac/Linux  
ifconfig | grep "inet "
```

Replace `http://192.168.253.12:8000` with `http://YOUR_LOCAL_IP:8000`

## Step 4: Start the Application 🚀

**Terminal 1 - Backend:**
```bash
cd api
yarn start
```
*You should see: "Connected to Mongo Db" and "Server running on port 8000"*

**Terminal 2 - Frontend:**
```bash
npx expo start
```

## Step 5: Run on Your Device 📱
1. Install **Expo Go** on your mobile device
2. Scan the QR code from terminal with Expo Go
3. Wait for the app to load

## Test the App 🧪
1. Register a new account
2. Upload a profile picture (URL)
3. Create another account to test messaging
4. Send friend requests and chat!

## Common Issues & Solutions 🔧

**"Network Error" when registering:**
- Check if backend is running on port 8000
- Verify IP addresses are updated correctly
- Ensure device and computer are on same WiFi

**"Cannot connect to database":**
- Verify MongoDB connection string
- Check your IP is whitelisted in MongoDB Atlas
- Ensure internet connection is stable

**Expo app crashes or won't load:**
- Clear Expo cache: `npx expo start --clear`
- Restart Expo Go app
- Check terminal for error messages

## Next Steps 📖
- Read the full [README.md](README.md) for detailed documentation
- Check [CONTRIBUTING.md](CONTRIBUTING.md) to contribute
- Explore [API Documentation](docs/API.md) for backend details
- See [Deployment Guide](docs/DEPLOYMENT.md) for production setup

## Need Help? 🆘
- Check [Troubleshooting](README.md#️-troubleshooting) section
- Open an [issue](https://github.com/isharax9/ChatApp/issues) on GitHub
- Join the discussion in GitHub Discussions

---

**Happy Coding! 🎉**

*If this quick setup worked for you, please ⭐ star the repository!*