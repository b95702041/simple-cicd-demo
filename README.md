# Simple CI/CD Demo

A simple Node.js web application demonstrating CI/CD concepts with Jenkins and Docker.

## 🎯 What This Project Demonstrates

- **Continuous Integration:** Automated testing on every code change
- **Continuous Deployment:** Automated deployment pipeline
- **Jenkins Pipeline:** Complete CI/CD workflow using Jenkinsfile
- **Docker:** Jenkins running in a containerized environment
- **Automated Testing:** Jest unit tests with CI integration

## 📁 Project Structure

```
simple-cicd-demo/
├── app.js              # Express.js web application
├── app.test.js         # Jest unit tests
├── package.json        # Node.js dependencies and scripts
├── Jenkinsfile         # Jenkins pipeline configuration
├── .gitignore          # Git ignore rules
└── README.md           # This documentation
```

## 🚀 Local Development

### Prerequisites
- Node.js 18+ (we use 24.4.1 in CI)
- npm package manager

### Quick Start
```bash
# Install dependencies
npm install

# Run tests
npm test

# Start the application
npm start
```

### Available Scripts
- `npm start` - Start the Express server on port 3000
- `npm test` - Run Jest test suite

## 🌐 API Endpoints

- **GET /** - Returns hello world message with timestamp
  ```json
  {
    "message": "Hello CI/CD World!",
    "version": "1.0.0",
    "timestamp": "2025-01-17T15:30:45.123Z"
  }
  ```

- **GET /health** - Health check endpoint
  ```json
  {
    "status": "healthy",
    "uptime": 47.8329652
  }
  ```

## 🔧 CI/CD Pipeline

Our Jenkins pipeline includes these automated stages:

1. **📥 Checkout** - Get latest code from GitHub
2. **⚙️ Setup** - Verify Node.js 24.4.1 environment
3. **📦 Install Dependencies** - Run `npm install`
4. **🧪 Run Tests** - Execute Jest unit tests
5. **🏗️ Build** - Prepare application for deployment
6. **🚀 Deploy to Staging** - Simulate deployment process

### Pipeline Configuration

The pipeline is defined in `Jenkinsfile` and includes:
- Automatic Node.js 24.4.1 installation
- Dependency caching
- Test result reporting
- Build artifacts
- Deployment simulation

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **Node.js 24.4.1** | Runtime environment |
| **Express.js** | Web framework |
| **Jest** | Testing framework |
| **Supertest** | HTTP testing utilities |
| **Jenkins** | CI/CD automation platform |
| **Docker** | Container platform for Jenkins |
| **Git/GitHub** | Version control and source hosting |

## 📋 Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/b95702041/simple-cicd-demo.git
cd simple-cicd-demo
```

### 2. Local Development
```bash
npm install
npm test
npm start
```

### 3. Jenkins Setup
1. **Install Docker Desktop**
2. **Run Jenkins in Docker:**
   ```bash
   docker run -d -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts
   ```
3. **Access Jenkins:** http://localhost:8080
4. **Install NodeJS Plugin**
5. **Configure Node.js 24.4.1 tool**
6. **Create Pipeline job pointing to this repository**

## ✅ Pipeline Results

**Latest Build Status:** ✅ SUCCESS

```
✅ Node.js: v24.4.1
✅ npm: v11.4.2
✅ Dependencies: 346 packages installed
✅ Tests: 2/2 passing
✅ Build: Completed successfully
✅ Deployment: Simulated successfully
```

## 🧪 Test Coverage

```
Test Suites: 1 passed, 1 total
Tests:       2 passed, 2 total
Snapshots:   0 total
Time:        1.672 s
```

### Test Cases
- ✅ GET / returns correct hello message
- ✅ GET /health returns healthy status

## 📝 Learning Outcomes

This project demonstrates:
- Setting up a complete CI/CD pipeline from scratch
- Automated testing integration
- Docker containerization for development tools
- Git workflow with automated builds
- Jenkins pipeline configuration
- Node.js application development and testing

## 🔄 Workflow

1. **Developer pushes code** → GitHub repository
2. **Jenkins detects changes** → Triggers pipeline
3. **Pipeline runs automatically** → Tests, builds, deploys
4. **Results reported** → Success/failure notifications
5. **Application deployed** → Ready for use

## 🎓 Next Steps

To extend this project, consider:
- Adding more comprehensive tests
- Implementing real deployment to cloud platforms
- Adding code quality checks (linting, security scans)
- Setting up multiple environments (dev, staging, production)
- Adding notification integrations (Slack, email)
- Implementing blue-green deployments

---

**Created as a hands-on learning exercise for CI/CD concepts with Jenkins and Docker.**

*For questions or improvements, please open an issue or submit a pull request.*