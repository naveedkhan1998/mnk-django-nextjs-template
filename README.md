# Next.js and Django REST Framework Template

This template provides a complete setup for building modern web applications using **Next.js** for the frontend and **Django REST Framework** for the backend. The setup is designed to support real-time functionality using **ASGI Django** with WebSockets via **Django Channels** and **Redis**. It also includes caching and database support with **PostgreSQL**, along with a pre-configured **RTK Toolkit** and **Tailwind CSS** for frontend state management and styling. Additionally, it integrates **shadcn components** for enhanced UI.

## Features

- **Backend**:

  - Django REST Framework with ASGI setup
  - WebSocket support using Django Channels and Redis
  - PostgreSQL for database management
  - Caching via Redis
  - OAuth integration with Google for authentication

- **Frontend**:

  - Next.js application with RTK Toolkit template
  - Tailwind CSS for styling
  - Pre-configured shadcn components for UI design

- **Deployment**:
  - Nginx server exposed on port `8000`, managing routing for API and frontend
  - Docker Compose configuration for containerized deployment
    - PostgreSQL
    - Redis
    - Django API
    - Next.js Frontend

## Getting Started

### Prerequisites

1. Install Docker and Docker Compose on your machine.
2. Clone the repository:
   ```bash
   git clone <repo-url>
   cd <repo-directory>
   ```

### Setup Environment Variables

1. Create a `.envs` folder in the root directory.
2. Inside `.envs`, create a file named `env.dev` with the following content:

   ```env
   # PostgreSQL Configuration
   POSTGRES_DB=realtime-chat
   POSTGRES_USER=postgres
   POSTGRES_PASSWORD=postgres
   POSTGRES_HOST=postgres
   POSTGRES_PORT=5432

   # Redis Configuration
   REDIS_CACHE_URL=redis://redis:6379/0
   REDIS_URL=redis://redis:6379/0

   # Celery Configuration
   CELERY_BROKER_URL=redis://redis:6379/0
   CELERY_RESULT_BACKEND=redis://redis:6379/0

   # OAuth Configuration
   GOOGLE_OAUTH_CLIENT_ID=fake
   GOOGLE_OAUTH_CLIENT_SECRET=fake
   GOOGLE_OAUTH_CALLBACK_URL=http://localhost:8000/api/accounts/auth/social/google/
   ```

### Run the Application

1. Build and start the containers:

   ```bash
   docker-compose up --build
   ```

2. Access the application at:
   - Frontend: [http://localhost:8000](http://localhost:8000)
   - Backend: API endpoints routed via Nginx on the same port.

This template provides a clean starting point for building robust, scalable web applications with real-time capabilities. Happy coding! 🎉