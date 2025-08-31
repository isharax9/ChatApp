# Deployment Guide

This guide covers deploying ChatApp to production environments.

## Overview

ChatApp consists of two main components:
1. **Backend API** - Express.js server that can be deployed to any Node.js hosting service
2. **Mobile App** - React Native app built with Expo that can be published to app stores

## Backend Deployment

### Prerequisites

- MongoDB Atlas cluster (production-ready)
- Node.js hosting service account
- Domain name (optional but recommended)
- SSL certificate (for HTTPS)

### Recommended Hosting Services

#### Option 1: Heroku (Easiest)
- Free tier available
- Easy deployment with Git
- Built-in SSL
- Environment variable management

#### Option 2: Railway
- Modern platform
- Git-based deployment
- Good free tier

#### Option 3: Render
- Free tier with SSL
- Auto-deploy from GitHub
- Environment variable support

#### Option 4: DigitalOcean App Platform
- Reliable and scalable
- Good for production use
- Competitive pricing

#### Option 5: AWS/GCP/Azure
- Most scalable options
- Requires more configuration
- Best for enterprise applications

### Deployment Steps (Heroku Example)

#### 1. Prepare Your Backend

**Create `package.json` scripts for production**:
```json
{
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "build": "npm install"
  }
}
```

**Create `Procfile` in `/api` directory**:
```
web: node index.js
```

**Update `index.js` for production**:
```javascript
const PORT = process.env.PORT || 8000;

app.listen(PORT, '0.0.0.0', () => {
  console.log(`Server running on port ${PORT}`);
});
```

#### 2. Set Up Environment Variables

Create production environment variables:
- `MONGODB_URI`: Your MongoDB Atlas connection string
- `JWT_SECRET`: Strong secret key for JWT tokens
- `NODE_ENV`: Set to `production`
- `PORT`: Let Heroku assign (automatic)

#### 3. Deploy to Heroku

```bash
# Install Heroku CLI
npm install -g heroku

# Login to Heroku
heroku login

# Create new Heroku app
cd api
heroku create your-chatapp-api

# Set environment variables
heroku config:set MONGODB_URI="your-mongodb-connection-string"
heroku config:set JWT_SECRET="your-super-secret-key"
heroku config:set NODE_ENV="production"

# Deploy
git init
git add .
git commit -m "Initial deployment"
git push heroku main
```

#### 4. Verify Deployment

```bash
# Check logs
heroku logs --tail

# Test API endpoint
curl https://your-chatapp-api.herokuapp.com/
```

### Environment Variables Reference

| Variable | Description | Required | Example |
|----------|-------------|----------|---------|
| `MONGODB_URI` | MongoDB connection string | Yes | `mongodb+srv://user:pass@cluster.mongodb.net/db` |
| `JWT_SECRET` | Secret key for JWT tokens | Yes | `your-super-secret-256-bit-key` |
| `NODE_ENV` | Environment mode | Yes | `production` |
| `PORT` | Server port | No | `8000` (auto-assigned on most platforms) |
| `CORS_ORIGIN` | Allowed origins for CORS | No | `https://yourapp.com` |

### Production Checklist

- [ ] MongoDB Atlas cluster configured for production
- [ ] Environment variables set securely
- [ ] CORS configured for your domain
- [ ] HTTPS enabled
- [ ] Error logging configured
- [ ] Database connection pooling optimized
- [ ] API rate limiting implemented (recommended)
- [ ] Input validation and sanitization
- [ ] Proper error handling for all endpoints
- [ ] Health check endpoint added

## Mobile App Deployment

### Expo Build Service (EAS)

#### 1. Install EAS CLI

```bash
npm install -g @expo/eas-cli
```

#### 2. Configure EAS

```bash
cd ChatApp
eas login
eas build:configure
```

#### 3. Update App Configuration

**Update `app.json`**:
```json
{
  "expo": {
    "name": "ChatApp",
    "slug": "chatapp",
    "version": "1.0.0",
    "platforms": ["ios", "android"],
    "orientation": "portrait",
    "icon": "./assets/icon.png",
    "splash": {
      "image": "./assets/splash.png",
      "resizeMode": "contain",
      "backgroundColor": "#ffffff"
    },
    "updates": {
      "url": "https://u.expo.dev/[project-id]"
    },
    "runtimeVersion": "1.0.0",
    "ios": {
      "bundleIdentifier": "com.yourcompany.chatapp",
      "buildNumber": "1.0.0"
    },
    "android": {
      "package": "com.yourcompany.chatapp",
      "versionCode": 1
    },
    "extra": {
      "apiUrl": "https://your-chatapp-api.herokuapp.com"
    }
  }
}
```

#### 4. Update API URLs

**Create environment configuration**:
```javascript
// config/env.js
const ENV = {
  dev: {
    apiUrl: 'http://192.168.1.100:8000', // Your local IP
  },
  prod: {
    apiUrl: 'https://your-chatapp-api.herokuapp.com',
  },
};

export default ENV[__DEV__ ? 'dev' : 'prod'];
```

**Update API calls in your components**:
```javascript
import ENV from '../config/env';

// Replace hardcoded URLs with
const API_URL = ENV.apiUrl;
```

#### 5. Build for App Stores

**Build for iOS**:
```bash
eas build --platform ios
```

**Build for Android**:
```bash
eas build --platform android
```

**Build for both platforms**:
```bash
eas build --platform all
```

### App Store Submission

#### iOS App Store

1. **Requirements**:
   - Apple Developer Account ($99/year)
   - App Store Connect access
   - Completed app metadata

2. **Submission Process**:
   - Upload build via EAS or Xcode
   - Complete app information in App Store Connect
   - Submit for review
   - Wait for approval (1-7 days typically)

3. **App Store Guidelines**:
   - Follow Apple's Human Interface Guidelines
   - Ensure proper permissions handling
   - Test on multiple iOS devices
   - Include privacy policy if collecting data

#### Google Play Store

1. **Requirements**:
   - Google Play Developer Account ($25 one-time)
   - Signed APK/AAB file
   - Store listing assets

2. **Submission Process**:
   - Upload build to Google Play Console
   - Complete store listing
   - Set up pricing and distribution
   - Submit for review
   - Publish when approved

3. **Play Store Requirements**:
   - Target latest Android API level
   - Include proper permissions
   - Provide privacy policy
   - Test on various Android devices

### Production Mobile App Checklist

- [ ] API URLs updated to production endpoints
- [ ] App icons and splash screens configured
- [ ] App name and package identifiers set
- [ ] Version numbers configured
- [ ] Permissions properly configured
- [ ] Privacy policy created and linked
- [ ] App store assets prepared (screenshots, descriptions)
- [ ] Testing completed on multiple devices
- [ ] Push notification setup (if implemented)
- [ ] Analytics integration (if desired)
- [ ] Crash reporting configured
- [ ] App signed with production certificates

## Domain and SSL Setup

### Custom Domain (Optional)

1. **Purchase Domain**: From providers like Namecheap, GoDaddy, etc.
2. **Configure DNS**: Point domain to your hosting service
3. **SSL Certificate**: Most hosting services provide free SSL

### Example Nginx Configuration

If deploying to a VPS:

```nginx
server {
    listen 80;
    listen [::]:80;
    server_name yourdomain.com www.yourdomain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name yourdomain.com www.yourdomain.com;

    ssl_certificate /path/to/ssl/certificate.crt;
    ssl_certificate_key /path/to/ssl/private.key;

    location / {
        proxy_pass http://localhost:8000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;
    }
}
```

## Monitoring and Maintenance

### Recommended Monitoring Tools

1. **Application Monitoring**:
   - Heroku Metrics (if using Heroku)
   - New Relic
   - DataDog
   - Application Insights

2. **Error Tracking**:
   - Sentry
   - Bugsnag
   - Rollbar

3. **Database Monitoring**:
   - MongoDB Atlas built-in monitoring
   - Database performance metrics

### Maintenance Tasks

#### Regular Tasks
- [ ] Monitor server performance and response times
- [ ] Check database storage usage
- [ ] Review error logs
- [ ] Update dependencies for security patches
- [ ] Monitor API usage patterns
- [ ] Backup database regularly
- [ ] Check SSL certificate expiration

#### Monthly Tasks
- [ ] Review and rotate API keys if needed
- [ ] Analyze usage patterns and optimize
- [ ] Update documentation
- [ ] Plan feature updates
- [ ] Review security best practices

## Scaling Considerations

### Backend Scaling

1. **Horizontal Scaling**:
   - Load balancer with multiple server instances
   - Session management with Redis
   - Database read replicas

2. **Vertical Scaling**:
   - Increase server resources (CPU, RAM)
   - Optimize database queries
   - Implement caching strategies

3. **Microservices Architecture**:
   - Split authentication, messaging, and user management
   - Use message queues for asynchronous processing
   - Implement API gateway

### Database Scaling

1. **MongoDB Atlas Scaling**:
   - Auto-scaling cluster tier
   - Read replicas for read-heavy workloads
   - Sharding for very large datasets

2. **Optimization**:
   - Database indexing
   - Query optimization
   - Connection pooling

## Security Best Practices

### Production Security

- [ ] Use HTTPS everywhere
- [ ] Implement rate limiting
- [ ] Input validation and sanitization
- [ ] SQL injection prevention (NoSQL injection for MongoDB)
- [ ] Secure headers (CORS, CSP, etc.)
- [ ] Regular security audits
- [ ] Keep dependencies updated
- [ ] Use environment variables for secrets
- [ ] Implement proper authentication flow
- [ ] Log security events

### Mobile App Security

- [ ] Secure API communication (HTTPS only)
- [ ] Token storage security
- [ ] Input validation on client side
- [ ] Secure image upload handling
- [ ] Proper error handling (don't expose sensitive info)
- [ ] Certificate pinning (advanced)

## Troubleshooting Common Issues

### Backend Issues

**MongoDB Connection Issues**:
- Check connection string format
- Verify IP whitelist in MongoDB Atlas
- Ensure network connectivity

**CORS Errors**:
- Update CORS configuration for production domain
- Check preflight requests handling

**Environment Variables**:
- Verify all required variables are set
- Check variable naming and values

### Mobile App Issues

**API Connection Issues**:
- Update API URLs to production endpoints
- Check network connectivity
- Verify HTTPS configuration

**Build Issues**:
- Update Expo SDK if needed
- Check for deprecated dependencies
- Verify app.json configuration

## Support and Resources

### Documentation
- [Expo Documentation](https://docs.expo.dev/)
- [MongoDB Atlas Documentation](https://docs.atlas.mongodb.com/)
- [Heroku Documentation](https://devcenter.heroku.com/)

### Community
- [Expo Discord](https://chat.expo.dev/)
- [React Native Community](https://reactnative.dev/community)
- [MongoDB Community](https://community.mongodb.com/)

### Professional Support
- Consider professional deployment services
- MongoDB Atlas support tiers
- Expo Application Services (EAS) support

---

Remember to test thoroughly in a staging environment before deploying to production!