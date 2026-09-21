# AI Diagram Hub

An AI-powered diagram creation platform. Describe your diagram in natural language, and AI generates it for you.

Built on Cloudflare Pages with React frontend and Pages Functions backend.

## Key Highlights

### Three Drawing Engines

Three distinctive drawing engines to meet different needs:

- **Mermaid** - Flowcharts, sequence diagrams, class diagrams - code-driven, precise control
- **Excalidraw** - Hand-drawn style diagrams, clean and beautiful, great for brainstorming
- **Draw.io** - Professional diagram editor, feature-rich, ideal for complex diagrams

### Intuitive Project Management

- Easily manage all your diagram projects
- Complete version history, restore to any previous version
- **All data stored locally** - no privacy concerns

### Superior Drawing Experience

- **Instant Response** - Almost all diagrams render in seconds, no more waiting
- **Beautiful Styling** - Specially optimized Mermaid rendering for significantly improved aesthetics
- **Smart Editing** - Continue editing based on existing diagrams, AI understands context
- **Spatial Awareness** - Better layout capabilities, fewer arrows crossing through elements

### Multimodal Input

Beyond text descriptions, also supports:

- **Document Visualization** - Upload documents to auto-generate visual diagrams
- **Image Recreation** - Upload images, AI recognizes and recreates diagrams
- **Link Parsing** - Enter URLs to auto-parse content and generate diagrams

## Quick Start

### Option 1: Quick Generate from Homepage

1. Open the homepage
2. Select a drawing engine (Mermaid / Excalidraw / Draw.io)
3. Enter your diagram description, e.g., "Draw a user login flowchart"
4. Click Generate - AI creates the project and diagram automatically

### Option 2: Project Management

1. Go to the Projects page
2. Click "New Project"
3. Choose an engine and name your project
4. Use the chat panel in the editor to describe your needs

## Usage Tips

### AI Chat Generation

In the chat panel on the right side of the editor, you can:

- Describe new diagrams: "Draw an e-commerce checkout flow"
- Modify existing diagrams: "Change the payment node to red"
- Add elements: "Add an inventory check step"

### Manual Editing

- **Excalidraw** - Drag and draw directly on the canvas
- **Draw.io** - Use professional diagram editing tools
- **Mermaid** - Edit the code directly

### Version Management

- Click the "History" button in the toolbar
- View all historical versions
- Click any version to preview
- Click "Restore" to revert to that version

## Local Development

### 1. Clone and Install Dependencies

```bash
git clone https://github.com/hkxiaoyao/ai-draw-nexus
cd ai-draw-nexus
pnpm install
```

### 2. Configure Environment Variables

Create a `.dev.vars` file in the root directory:

```env
AI_API_KEY=your-api-key
AI_BASE_URL=https://api.openai.com/v1
AI_PROVIDER=openai
AI_MODEL_ID=gpt-4o-mini
```

> Supports OpenAI, Anthropic, and other OpenAI-compatible services

### 3. Start Development Server

```bash
# Start frontend + backend together
pnpm run dev
# Visit http://localhost:8787

# Or run separately:
pnpm run dev:frontend   # Vite only (http://localhost:5173)
pnpm run dev:backend    # Wrangler Pages only (http://localhost:8787)
```

**Note**: Access `http://localhost:8787` during development (wrangler proxies vite).

## Cloudflare Pages Deployment

### 1. Build

```bash
pnpm run build        # TypeScript check + Vite build
```

### 2. Configure Production Secrets

```bash
wrangler pages secret put AI_API_KEY
wrangler pages secret put AI_BASE_URL
wrangler pages secret put AI_PROVIDER
wrangler pages secret put AI_MODEL_ID
```

Or configure environment variables in Cloudflare Pages dashboard.

### 3. Deploy

```bash
pnpm run pages:deploy
```

### Supported AI Services

| Provider | AI_PROVIDER | AI_BASE_URL | Recommended Models |
|----------|-------------|-------------|-------------------|
| OpenAI | openai | https://api.openai.com/v1 | gpt-5 |
| Anthropic | anthropic | https://api.anthropic.com/v1 | claude-sonnet-4-5 |
| Other compatible | openai | Custom URL | - |

## Tech Stack

- Frontend: React 19 + Vite + TypeScript + Tailwind CSS
- State: Zustand
- Storage: Dexie.js (IndexedDB)
- Backend: Cloudflare Pages Functions

## License

MIT
