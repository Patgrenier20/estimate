# EstimateAI - Construction Estimate Analyzer

A modern, AI-powered construction estimate analysis platform with SC residential building code expertise.

## Features

### 📄 PDF Estimate Analysis
- Upload construction estimate PDFs
- AI-powered extraction of key information:
  - Project name and address
  - Estimator details
  - Total cost and square footage
  - Line item breakdown
  - Category analysis
  - Scope of work

### 💬 Estimate Chat
- Ask questions about your uploaded estimates
- Get insights on pricing, missing items, and potential issues
- AI-powered responses using Gemini

### 🏗️ SC Building Code Assistant
- Expert knowledge of SC Residential Building Code (IRC 2021)
- Local amendments for:
  - Charleston County
  - Dorchester County
  - Berkeley County
- Municipal codes for:
  - City of Charleston
  - North Charleston
  - Mount Pleasant
  - Summerville
  - Goose Creek

## Tech Stack

### Frontend
- **Next.js 14** - React framework with App Router
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **shadcn/ui** - UI components
- **Framer Motion** - Animations
- **Zustand** - State management

### Backend
- **Express.js** - API server
- **Google Gemini** - AI/LLM integration
- **JWT** - Authentication
- **Multer** - File uploads

## Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn
- Gemini API key (get one at https://makersuite.google.com/app/apikey)

### Installation

1. Clone the repository:
```bash
cd j:\estimate
```

2. Install frontend dependencies:
```bash
npm install
```

3. Install backend dependencies:
```bash
cd server
npm install
```

4. Configure environment variables:

Create `server/.env`:
```env
PORT=3001
JWT_SECRET=your-secret-key-change-in-production
GEMINI_API_KEY=your-gemini-api-key-here
```

### Running the Application

1. Start the backend server:
```bash
cd server
npm run dev
```

2. In a new terminal, start the frontend:
```bash
npm run dev
```

3. Open http://localhost:3000 in your browser

## Project Structure

```
estimate/
├── app/                    # Next.js app directory
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/
│   ├── auth/              # Authentication components
│   ├── dashboard/         # Dashboard components
│   ├── ui/                # shadcn/ui components
│   └── theme-provider.tsx # Theme provider
├── lib/
│   └── utils.ts           # Utility functions
├── store/
│   └── useStore.ts        # Zustand store
├── types/
│   └── index.ts           # TypeScript types
├── server/                # Backend server
│   ├── src/
│   │   ├── index.ts       # Server entry
│   │   └── routes/        # API routes
│   └── package.json
└── package.json
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login
- `GET /api/auth/me` - Get current user

### Estimates
- `POST /api/estimates/upload` - Upload PDF estimate
- `GET /api/estimates` - Get all estimates
- `GET /api/estimates/:id` - Get estimate by ID
- `DELETE /api/estimates/:id` - Delete estimate

### Chat
- `POST /api/chat/estimate/:estimateId` - Chat about estimate
- `GET /api/chat/session/:sessionId` - Get chat session
- `GET /api/chat/sessions` - Get all sessions

### Code Assistant
- `POST /api/code-assistant/chat` - Ask code question
- `GET /api/code-assistant/session/:sessionId` - Get session
- `GET /api/code-assistant/sessions` - Get all sessions

## Configuration

### Gemini API
The application uses Google's Gemini 1.5 Flash model for:
- PDF analysis and data extraction
- Estimate Q&A
- Building code assistance

Get your API key at: https://makersuite.google.com/app/apikey

### Jurisdictions
The code assistant supports the following jurisdictions:
- SC Residential Code (Statewide)
- Charleston County
- Dorchester County
- Berkeley County
- City of Charleston
- North Charleston
- Mount Pleasant
- Summerville
- Goose Creek

## License

MIT
