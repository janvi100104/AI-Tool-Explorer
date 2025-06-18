# AI Tool Explorer

A comprehensive full-stack web application for browsing, filtering, and favoriting AI tools. Built with Express.js backend and React frontend with modern UI components.


> 🌟 **Last Updated**: June 18, 2025

## 📋 Project Overview

AI Tool Explorer consists of two main components:
- A **backend server** built with Express.js that provides RESTful API endpoints
- A **frontend client** built with React and modern UI libraries

The application allows users to browse a curated list of AI tools, filter them by category, search across multiple fields, and save their favorites for later reference.

## ✨ Features

### Core Functionality
- Browse 20 AI tools in a responsive card layout
- Filter tools by category with dropdown
- Search by tool name, category, tags, or description
- Add/remove tools from favorites with heart icons
- Dedicated favorites page to view and manage favorite tools
- Responsive design for mobile and desktop
- Comprehensive error handling and loading states

### Backend API (Express.js)
- `GET /api/tools` - Return all AI tools
- `GET /api/tools?category=Writing` - Filter tools by category (case-insensitive)
- `POST /api/favorites` - Save tool to favorites (prevents duplicates)
- `GET /api/favorites` - List all saved favorites
- `DELETE /api/favorites/:id` - Remove tool from favorites
- `GET /api/categories` - Get all unique categories
- `GET /api/health` - Health check endpoint

### Enhanced User Experience
- Dark/light mode toggle
- Interactive charts showing tools by category
- Advanced search across multiple fields
- Confetti animation when adding favorites
- Real-time favorites counter
- Loading states with skeleton loaders
- Comprehensive error handling

## 🛠 Tech Stack

### Backend
- **Node.js** with **Express.js**
- **TypeScript** for type safety
- **CORS** for cross-origin requests
- **In-memory storage** for favorites (resets on server restart)

### Frontend
- **React** with **TypeScript**
- **React Router** for navigation
- **TanStack Query** for data fetching and caching
- **Tailwind CSS** for styling
- **ShadCN UI** components library
- **Lucide React** for icons
- **Recharts** for data visualization
- **Canvas Confetti** for animations
- **Axios** for HTTP requests

## 📦 Installation & Setup

### Prerequisites
- Node.js 18+ and Bun (or npm/yarn)
- Git

### Clone the Repository
```bash
# Clone the repository
git clone https://github.com/yourusername/ai-tool-explorer.git
cd AI\ Tool\ Explorer
```

### Backend Setup
```bash
# Navigate to backend directory
cd ai-tools-backend

# Install dependencies
bun install
# OR if using npm
npm install

# Start the server (runs on port 3001)
bun run index.ts
# OR if using npm
npx tsx index.ts
```

### Frontend Setup
```bash
# Navigate to frontend directory
cd client

# Install dependencies
bun install
# OR if using npm
npm install

# Start development server
bun dev
# OR if using npm
npm run dev
```

### Accessing the Application
- Frontend: [http://localhost:5173](http://localhost:5173) or [http://localhost:5174](http://localhost:5174)
- Backend API: [http://localhost:3001/api](http://localhost:3001/api)
- API Documentation: [http://localhost:3001](http://localhost:3001)

## 🗂 Project Structure

```
AI Tool Explorer/
├── ai-tools-backend/       # Backend API server
│   ├── index.ts            # Express server with API routes
│   ├── data.ts             # Sample AI tools data (20 tools)
│   ├── package.json        # Backend dependencies
│   └── README.md           # Backend documentation
│
├── client/                 # React frontend application
│   ├── src/
│   │   ├── App.tsx         # Main application with all components
│   │   ├── api.ts          # API service functions
│   │   ├── types.ts        # TypeScript interfaces
│   │   ├── main.tsx        # Application entry point
│   │   ├── index.css       # Global styles
│   │   ├── demo-data.ts    # Fallback data for offline mode
│   │   └── components/ui/  # ShadCN UI components
│   ├── public/             # Static assets
│   ├── package.json        # Frontend dependencies
│   ├── vite.config.ts      # Build configuration
│   └── README.md           # Frontend documentation
│
└── README.md               # Project documentation (this file)
```

## 📡 API Documentation

### Get All Tools
```
GET /api/tools
```
Returns all AI tools in the database.

### Filter Tools by Category
```
GET /api/tools?category=Writing
```
Returns tools filtered by the specified category (case-insensitive).

### Get All Categories
```
GET /api/categories
```
Returns a list of all unique categories.

### Add to Favorites
```
POST /api/favorites
Content-Type: application/json

{
  "toolId": 1
}
```
Adds a tool to favorites. Prevents duplicates.

### Get Favorites
```
GET /api/favorites
```
Returns all favorited tools with complete details.

### Remove from Favorites
```
DELETE /api/favorites/:id
```
Removes a tool from favorites by ID.

### Health Check
```
GET /api/health
```
Returns server status and statistics.

## 💾 Sample Data

The application includes 20 AI tools across 8 categories:
- **Writing** (5 tools): ChatGPT, Claude, Grammarly, Jasper, Copy.ai
- **Image Generation** (3 tools): DALL-E 3, Midjourney, Stable Diffusion
- **Coding** (3 tools): GitHub Copilot, Cursor, Replit AI
- **Video** (3 tools): Loom AI, RunwayML, Synthesia
- **Audio** (2 tools): Eleven Labs, Otter.ai
- **Productivity** (2 tools): Notion AI, Zapier AI
- **Research** (1 tool): Perplexity
- **Design** (1 tool): Canva AI

## 🚀 Development Notes

### Key Implementation Details
1. **State Management**: React Context for global state (dark mode, favorites)
2. **Data Fetching**: TanStack Query for caching and synchronization
3. **Component Architecture**: Single-file components for rapid development
4. **API Design**: RESTful endpoints with proper HTTP status codes
5. **Error Handling**: Graceful error handling throughout the app

### Edge Cases Handled
- Duplicate favorite prevention with user feedback
- Empty search results with clear messaging
- Network errors with retry suggestions
- Category filtering with case-insensitive matching
- Mobile responsiveness across different device sizes

## 📈 Future Enhancements

Potential improvements for production use:
- **Database Integration**: Replace in-memory storage with PostgreSQL/MongoDB
- **User Authentication**: Login system with personal favorites
- **Tool Submissions**: Allow users to submit new AI tools
- **Reviews & Ratings**: User reviews and star ratings
- **Advanced Filtering**: Price range, popularity, date added
- **Hierarchical Categories**: Nested category system
- **Search Analytics**: Track popular searches and tools

## 📚 Resources

- [Express.js Documentation](https://expressjs.com/)
- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TanStack Query Documentation](https://tanstack.com/query/latest)
- [ShadCN UI Documentation](https://ui.shadcn.com/)

## 📄 License

This project is for educational purposes only. All AI tools mentioned are property of their respective owners.
