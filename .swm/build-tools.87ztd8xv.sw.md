---
title: Build Tools
---
## 1\. Overview

Sentry uses a variety of build tools to manage its development process, ensure code quality, and prepare the application for deployment. These tools automate various tasks such as dependency management, code compilation, testing, and asset bundling.

## 2\. Key Build Tools

### 2.1 Package Managers

#### npm (Node Package Manager)

- **Purpose**: Manages JavaScript dependencies for the frontend.

- **Key Files**: `package.json`, `package-lock.json`

- **Usage**: `npm install`, `npm run <script>`

#### pip

- **Purpose**: Manages Python dependencies for the backend.

- **Key Files**: `requirements.txt`

- **Usage**: `pip install -r requirements.txt`

### 2.2 Task Runners

#### Webpack

- **Purpose**: Bundles JavaScript modules and other assets for the frontend.

- **Key Files**: `webpack.config.js`

- **Usage**: Typically invoked through npm scripts

### 2.3 Transpilers

#### Babel

- **Purpose**: Transpiles modern JavaScript to ensure browser compatibility.

- **Key Files**: `.babelrc`

- **Usage**: Integrated with Webpack build process

### 2.4 Linters and Formatters

#### ESLint

- **Purpose**: Lints JavaScript code to catch errors and enforce style.

- **Key Files**: `.eslintrc.js`

- **Usage**: `eslint .`

#### Black

- **Purpose**: Formats Python code to ensure consistent style.

- **Usage**: `black .`

### 2.5 Testing Frameworks

#### Jest

- **Purpose**: JavaScript testing framework for frontend unit tests.

- **Key Files**: `jest.config.js`

- **Usage**: `jest`

#### pytest

- **Purpose**: Python testing framework for backend tests.

- **Usage**: `pytest`

### 2.6 Database Migration Tools

#### Alembic

- **Purpose**: Handles database schema migrations.

- **Key Files**: `alembic.ini`, migration scripts in `migrations/`

- **Usage**: `alembic upgrade head`

### 2.7 Docker

- **Purpose**: Containerizes the application for consistent development and deployment environments.

- **Key Files**: `Dockerfile`, `docker-compose.yml`

- **Usage**: `docker-compose up`

## 3\. Build Process

1. **Dependency Installation**:

   - Backend: `pip install -r requirements.txt`

   - Frontend: `npm install`

2. **Database Setup**:

   - Run migrations: `alembic upgrade head`

3. **Compile Assets**:

   - Run Webpack: `npm run build`

4. **Run Tests**:

   - Backend: `pytest`

   - Frontend: `npm test`

5. **Linting and Formatting**:

   - JavaScript: `eslint .`

   - Python: `black .`

6. **Build Docker Image**:

   - `docker build -t sentry .`

## 4\. Continuous Integration (CI)

Sentry uses GitHub Actions for CI/CD. The process typically includes:

1. Running all tests

2. Linting and code style checks

3. Building Docker images

4. Deploying to staging environments

## 5\. Development Workflow

1. Clone the repository

2. Install dependencies

3. Set up local environment variables

4. Run database migrations

5. Start development servers (backend and frontend)

6. Make changes and run tests locally

7. Submit pull request

## 6\. Best Practices

1. Keep dependencies up to date

2. Run linters before committing code

3. Write tests for new features and bug fixes

4. Use feature flags for gradual rollouts

5. Follow the branching strategy (e.g., GitFlow)

## 7\. Troubleshooting

- Clear npm cache if facing frontend build issues: `npm cache clean --force`

- Ensure Docker daemon is running for container-based operations

- Check for conflicting Python versions or virtual environments

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2VudHJ5LWNsYXVkZSUzQSUzQXNodWp1dXU=" repo-name="sentry-claude"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
