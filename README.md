# Photu-ai - Advanced AI Image Generation & LLM Platform

Photu-ai is a cutting-edge AI platform that combines state-of-the-art image generation with powerful language model capabilities. Built on advanced AI technologies, it enables users to create stunning AI-generated artwork, train custom models, and leverage LLM-powered features for enhanced creative control. Whether you're an AI researcher, creative professional, or developer building next-generation AI applications, Photu-ai provides an intuitive interface and robust capabilities for AI-powered image generation and model training.

## Core AI Technologies

- **Image Generation**: Advanced AI models for high-quality image synthesis
- **Language Models**: LLM integration for enhanced prompt engineering and image understanding
- **Custom Model Training**: Fine-tune AI models on your own datasets
- **Dynamic Model Selection**: Intelligent backend that automatically switches between different AI models based on cost and performance optimization
- **AI-Powered Features**:
  - Intelligent image enhancement
  - Style transfer and manipulation
  - Automated image tagging and description
  - Smart content filtering
  - AI-driven image organization

## Tech Stack

- **AI/ML**: 
  - Custom-trained models
  - OpenAI integration
  - Stable Diffusion
  - Dynamic model routing system
  - Cost-optimized model selection
- **Frontend**: Next.js 14 (App Router), TypeScript, Tailwind CSS, Shadcn/UI
- **Backend**: Node.js with TypeScript, AI model serving with intelligent model selection
- **Authentication**: Clerk
- **Containerization**: Docker
- **Package Management**: Bun
- **Monorepo Management**: Turborepo

## Project Structure

### Apps and Packages

- `web`: Next.js frontend application with AI integration
- `backend`: Node.js backend service with AI model serving
- `@repo/ui`: Shared React component library
- `@repo/typescript-config`: Shared TypeScript configurations
- `@repo/eslint-config`: Shared ESLint configurations

## Getting Started

### Prerequisites

- Docker
- Bun (for local development)
- Clerk Account (for authentication)
- OpenAI API Key (for LLM features)
- Stable Diffusion API access

### Environment Setup

1. Create `.env` files:

```bash
# apps/web/.env.local
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_publishable_key
CLERK_SECRET_KEY=your_secret_key
NEXT_PUBLIC_BACKEND_URL=http://localhost:8080
OPENAI_API_KEY=your_openai_key
STABLE_DIFFUSION_API_KEY=your_sd_key
```

### Local Development

```bash
# Install dependencies
bun install

# Run development servers
bun run dev

# Build all packages
bun run build
```

## AI Features

- Advanced image generation with multiple AI models
- LLM-powered prompt engineering and enhancement
- Custom model training and fine-tuning
- AI-driven image analysis and tagging
- Style transfer and manipulation
- Intelligent image organization
- Automated content filtering
- Batch processing capabilities
- AI-powered image enhancement
- Smart cropping and composition
- Dynamic model selection for cost optimization
- Automatic fallback to most cost-effective models

## Development Commands

```bash
# Run frontend only
bun run start:web

# Run backend only
bun run start:backend

# Run both frontend and backend
bun run dev

# Train custom model
bun run train:model
```

## Docker Setup

### Environment Variables Required

```bash
# Frontend Environment Variables
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
NEXT_PUBLIC_BACKEND_URL=your_backend_url
NEXT_PUBLIC_STRIPE_KEY=your_stripe_key
CLERK_SECRET_KEY=your_clerk_secret_key
OPENAI_API_KEY=your_openai_key
STABLE_DIFFUSION_API_KEY=your_sd_key

# Backend Environment Variables
DATABASE_URL=your_database_url
AI_MODEL_PATH=path_to_models
```

### Docker Commands

```bash
# Navigate to docker directory
cd docker

# Build images
docker build -f Dockerfile.frontend -t photu-ai-frontend ..
docker build -f Dockerfile.backend -t photu-ai-backend ..

# Run frontend container
docker run -p 3000:3000 \
  -e NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key \
  -e NEXT_PUBLIC_BACKEND_URL=your_backend_url \
  -e NEXT_PUBLIC_STRIPE_KEY=your_stripe_key \
  -e CLERK_SECRET_KEY=your_clerk_secret_key \
  -e OPENAI_API_KEY=your_openai_key \
  -e STABLE_DIFFUSION_API_KEY=your_sd_key \
  photu-ai-frontend

# Run backend container
docker run -p 8080:8080 \
  -e DATABASE_URL=your_database_url \
  -e AI_MODEL_PATH=path_to_models \
  photu-ai-backend
```

## Project Structure

```
.
├── apps
│   ├── web/                 # Next.js frontend with AI integration
│   └── backend/            # Node.js backend with AI model serving
├── packages
│   ├── ui/                 # Shared UI components
│   ├── typescript-config/  # Shared TS config
│   └── eslint-config/     # Shared ESLint config
├── docker/                # Docker configuration
│   ├── Dockerfile.frontend
│   └── Dockerfile.backend
└── package.json
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments

- Original project: [100xPhoto](https://github.com/code100x/photo-ai)
- Built with [Next.js](https://nextjs.org/)
- UI components from [shadcn/ui](https://ui.shadcn.com/)
- Authentication by [Clerk](https://clerk.com/)
- AI models powered by OpenAI and Stable Diffusion

## Backend AI Model Management

The backend implements an intelligent model selection system that:
- Automatically routes requests to the most cost-effective model
- Maintains quality while optimizing costs
- Provides seamless fallback mechanisms
- Monitors model performance and costs in real-time
- Adapts to changing API pricing and availability

### Model Selection Strategy

```bash
# Example model selection logic
if (request.priority === 'high') {
  usePremiumModel();
} else if (request.complexity === 'low') {
  useCostEffectiveModel();
} else {
  useBalancedModel();
}
```
