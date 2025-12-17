# Render Deployment Setup Guide

## Issues to Fix

### 1. Build Command Error

**Problem**: Build command is empty/invalid (`''''`), causing build to fail.

**Solution**: 
- Go to your Render service settings
- Set **Build Command** to: (leave empty) or `npm install`
- Set **Start Command** to: `npm start` (or `node app.js`)

For this simple Node.js app, you can leave the build command empty since Render automatically runs `npm install`.

### 2. GitHub Repository Access

**Problem**: Render shows "It looks like we don't have access to your repo"

**Solution**:
1. Go to [Render Dashboard](https://dashboard.render.com)
2. Click on **Account Settings** (top right)
3. Go to **Connected Accounts** section
4. Click **Connect** next to GitHub
5. Authorize Render to access your GitHub account
6. **Important**: Make sure to grant access to the `mark-analiza-college` organization/account
7. After connecting, go back to your service settings
8. Update the repository connection to use the newly connected GitHub account

### 3. Service Configuration

Your Render service should have:
- **Build Command**: (empty) or `npm install`
- **Start Command**: `npm start`
- **Environment**: Node
- **Node Version**: 22.16.0 (or latest)
- **Port**: 3000 (or use `process.env.PORT` which your app already does)

## After Fixing

Once both issues are resolved:
1. Render will be able to clone your repository
2. The build will succeed (npm install will run automatically)
3. Your app will start using the `start` script from `package.json`
4. The service will be accessible at the Render-provided URL

