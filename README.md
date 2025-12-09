# Health Insurance Chatbot

An AI-powered health insurance assistant for India that helps users understand insurance products and find the best policies for their needs.

## Features

- 💬 **Interactive Chat Interface**: Conversational AI that explains health insurance concepts
- 🤖 **LLM Integration**: Uses open-source language models (Ollama or Hugging Face) for intelligent responses
- 📊 **Policy Comparison**: Compares policies from multiple insurers (HDFC ERGO, ICICI Lombard, Aditya Birla, Star Health)
- 🎯 **Smart Recommendations**: Suggests policies based on user requirements (age, budget, coverage needs)
- 📱 **Responsive Design**: Works on desktop and mobile devices
- ⚡ **Real-time Updates**: Instant policy matching and recommendations

## Tech Stack

- **Frontend**: React 18 + TypeScript
- **Styling**: Tailwind CSS
- **State Management**: Zustand
- **Build Tool**: Vite
- **Icons**: Lucide React
- **Testing**: Vitest
- **HTTP Client**: Axios

## Project Structure

```
src/
├── components/
│   └── ChatInterface.tsx       # Main chat UI component
├── services/
│   └── llmService.ts           # LLM and policy aggregator services
├── store/
│   └── chatStore.ts            # Zustand state management
├── styles/
│   └── index.css               # Global styles with Tailwind
├── App.tsx                      # Main app component
└── main.tsx                     # Entry point
```

## Setup Instructions

### Prerequisites

- Node.js 18+ ([Download](https://nodejs.org/))
- npm or yarn package manager
- Optional: Ollama for local LLM ([Download](https://ollama.ai/))

### Installation

1. **Clone the repository**
   ```bash
   cd /tmp/health-insurance-chatbot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup (Optional - for LLM Integration)**

   Create a `.env` file for LLM configuration:
   ```bash
   # For Ollama (local)
   VITE_LLM_TYPE=ollama
   VITE_OLLAMA_URL=http://localhost:11434

   # For Hugging Face
   VITE_LLM_TYPE=huggingface
   VITE_HF_TOKEN=your_hugging_face_token_here
   ```

## Running the Application

### Development Mode

```bash
npm run dev
```

The app will open at `http://localhost:5173`

### Build for Production

```bash
npm run build
```

Output will be in the `dist/` folder.

### Preview Production Build

```bash
npm run preview
```

## Usage

1. **Start the chat**: The app greets you with an introduction
2. **Ask questions**: Ask about health insurance products, coverage, premiums, or Indian insurance terms
3. **Provide information**: Share your age, budget, health conditions, and coverage requirements
4. **Get recommendations**: The app analyzes your inputs and recommends matching policies
5. **Compare policies**: View side-by-side comparison of recommended policies

### Example Conversation Flow

- User: "I'm 35 years old and looking for health insurance"
- Assistant: Explains types of coverage and asks follow-up questions
- User: "I have a budget of ₹5,000 per month and need hospitalization and critical illness coverage"
- Assistant: Recommends 3-4 matching policies with comparison

## LLM Integration Options

### Option 1: Using Ollama (Local)

```bash
# Install Ollama from https://ollama.ai
# Run Ollama
ollama serve

# In another terminal, pull a model
ollama pull llama2  # or mistral, neural-chat, etc.
```

### Option 2: Using Hugging Face

Sign up at [Hugging Face](https://huggingface.co) and get your API token. Set `VITE_HF_TOKEN` in `.env`.

## Testing

### Run Unit Tests

```bash
npm run test
```

### Run Tests in Watch Mode

```bash
npm run test -- --watch
```

## API Reference

### LLM Service

```typescript
llmService.chat(messages, systemPrompt): Promise<string>
```

Sends a message to the LLM and gets a response.

### Policy Service

```typescript
policyService.recommendPolicies(age, conditions, budget, coverage): Promise<Policy[]>
policyService.comparePolicies(policies): Promise<string>
```

Gets policy recommendations and comparison details.

## Data Sources

Currently, the app uses mock data for:
- Insurance policies from: HDFC ERGO, ICICI Lombard, Aditya Birla, Star Health
- Premium rates and coverage details

In production, these would connect to:
- Insurance aggregator APIs
- Real-time premium calculation services
- Live policy databases

## Deployment

### Deploy to Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

### Deploy to Netlify

```bash
# Build
npm run build

# Drag and drop dist/ folder to Netlify
# Or connect Git repository for auto-deploy
```

### Deploy to Your Server

```bash
# Build
npm run build

# Upload dist/ folder to your web server
# Configure server to serve index.html for all routes (SPA routing)
```

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Future Enhancements

- [ ] Real-time policy data integration
- [ ] User accounts and saved policies
- [ ] Policy comparison PDF export
- [ ] Multi-language support (Hindi, Tamil, Telugu, etc.)
- [ ] Video tutorials on insurance concepts
- [ ] Premium calculator integration
- [ ] Agent/broker network integration
- [ ] Policy purchase flow integration

## Troubleshooting

### Port 5173 already in use

```bash
npm run dev -- --port 3000
```

### Module not found errors

```bash
rm -rf node_modules package-lock.json
npm install
```

### Build errors

```bash
npm run build -- --force
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

MIT License - feel free to use this project for commercial or personal use.

## Support

For issues, questions, or suggestions:
- Open an GitHub issue
- Email: support@healthinsurancechatbot.in
- Visit: https://healthinsurancechatbot.in

## Disclaimer

This application is for informational purposes only. Always verify policy details with official insurance websites before purchase. Insurance regulations in India are governed by IRDAI (Insurance Regulatory and Development Authority of India).

---

**Happy exploring! Get the right health insurance for you! 🏥💪**
