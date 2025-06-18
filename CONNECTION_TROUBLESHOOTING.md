# 🔧 Connection Troubleshooting Guide

## 🚨 Frontend-Backend Connection Issues

### The Problem
The deployed frontend at https://02ab9779-105e-4b05-b7ff-e1313adf0487.scout.page cannot connect to a local backend API running on `http://localhost:3001` due to:

1. **Network Isolation**: Deployed frontend runs on external servers
2. **CORS Restrictions**: Browser security prevents localhost connections from deployed sites  
3. **Firewall/NAT**: Local servers are not accessible from the internet

### ✅ Solution Options

#### Option 1: Run Both Locally (Recommended for Development)
```bash
# Terminal 1 - Start Backend
cd ai-tools-backend
bun install
bun start
# ✅ Backend at http://localhost:3001

# Terminal 2 - Start Frontend  
cd ai-tools-app
bun install
bun dev
# ✅ Frontend at http://localhost:8001
```

#### Option 2: Deploy Backend to Cloud Service

**Railway (Easiest)**
1. Sign up at https://railway.app
2. Connect your GitHub repository
3. Deploy the `ai-tools-backend` folder
4. Get your deployment URL (e.g., `https://ai-tools-backend-production.up.railway.app`)

**Render**
1. Sign up at https://render.com
2. Create new Web Service
3. Connect GitHub repo
4. Build command: `bun install`
5. Start command: `bun start`

**Vercel**
```bash
cd ai-tools-backend
npm i -g vercel
vercel
# Follow prompts
```

#### Option 3: Use ngrok for Local Tunnel (Quick Testing)
```bash
# Install ngrok
npm install -g ngrok

# Start backend first
cd ai-tools-backend
bun start

# In another terminal, create tunnel
ngrok http 3001
# Copy the https URL (e.g., https://abc123.ngrok.io)

# Update frontend .env
echo "VITE_API_BASE_URL=https://abc123.ngrok.io/api" > ai-tools-app/.env

# Rebuild and redeploy frontend
cd ai-tools-app
bun run build
```

### 🔄 Testing the Connection

1. **Local Development**: Both services running locally
   - Frontend: http://localhost:8001
   - Backend: http://localhost:3001/api/health

2. **Production Setup**: Backend deployed + Frontend updated
   - Frontend: https://02ab9779-105e-4b05-b7ff-e1313adf0487.scout.page
   - Backend: Your deployed URL

3. **Verify API Connection**:
   ```bash
   # Test backend health
   curl https://your-backend-url.com/api/health
   
   # Should return:
   # {"status":"OK","message":"AI Tools API is running","timestamp":"..."}
   ```

### 📱 Current Frontend Behavior

When the backend is not accessible, the deployed frontend now shows:
- ✅ Clear error message explaining the connection issue
- ✅ Step-by-step setup instructions  
- ✅ API URL configuration display
- ✅ Retry connection button
- ✅ Feature showcase even without backend

### 🛠 Environment Configuration

**Frontend (.env)**
```bash
# Local development
VITE_API_BASE_URL=http://localhost:3001/api

# Production with deployed backend
VITE_API_BASE_URL=https://your-backend-url.com/api
```

**Backend (auto-configured)**
```bash
PORT=3001  # or assigned by hosting service
NODE_ENV=production  # set by hosting service
```

### 🎯 Recommended Workflow

1. **Development**: Run both services locally
2. **Testing**: Use ngrok for external testing
3. **Production**: Deploy backend, update frontend env, redeploy
4. **Demo**: Use deployed frontend with clear setup instructions

This ensures the application works in all scenarios while providing clear guidance for users.