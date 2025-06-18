# 🚀 Quick Start Guide - AI Tools Browser

## 📋 Prerequisites
- Node.js 18+ 
- Bun installed (or npm/yarn)

## 🏃‍♂️ Running Locally (Both Services)

### 1. Start the Backend API (Terminal 1)
```bash
cd ai-tools-backend
bun install
bun start
```
✅ Backend running at: http://localhost:3001

### 2. Start the Frontend (Terminal 2)
```bash
cd ai-tools-app
bun install
bun dev
```
✅ Frontend running at: http://localhost:8001

## 🌐 Production Deployment

### Backend Deployment Options

#### Option 1: Railway (Recommended)
1. Fork this repository
2. Connect Railway to your GitHub
3. Deploy the `ai-tools-backend` folder
4. Railway will automatically detect and deploy the Express app

#### Option 2: Render
1. Create new Web Service on Render
2. Connect your GitHub repository
3. Set build command: `bun install`
4. Set start command: `bun start`

#### Option 3: Vercel
1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in the `ai-tools-backend` directory
3. Follow the prompts

### Frontend Deployment
The frontend is already deployed at: https://a13b96ad-2cca-4928-a7d0-3a6491264a58.scout.page

To connect to your deployed backend:
1. Update `.env` file with your backend URL:
   ```
   VITE_API_BASE_URL=https://your-backend-url.com/api
   ```
2. Rebuild and redeploy the frontend

## 🔧 Environment Configuration

### Backend Environment Variables
- `PORT`: Server port (default: 3001)
- `NODE_ENV`: Environment (development/production)

### Frontend Environment Variables
- `VITE_API_BASE_URL`: Backend API URL

## 📱 Testing the Connection

1. Start both services locally
2. Visit http://localhost:8001
3. Try searching for tools or adding favorites
4. Check browser console for any API errors

## 🚨 Common Issues

### CORS Errors
- Make sure backend is running on port 3001
- Check that CORS is configured in backend

### API Connection Failed
- Verify backend is accessible at the configured URL
- Check browser network tab for failed requests
- Ensure environment variables are set correctly

## 🔗 API Endpoints

Base URL: `http://localhost:3001/api` (local) or your deployed URL

- `GET /tools` - Get all tools
- `GET /tools?category=Writing` - Filter by category  
- `POST /favorites` - Add to favorites
- `GET /favorites` - Get favorites
- `DELETE /favorites/:id` - Remove favorite
- `GET /health` - Health check