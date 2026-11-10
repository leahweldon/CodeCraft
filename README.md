
# CodeCraft

**An AI-powered software engineering platform for code analysis, generation, completion and translation.**

**2024 Software Engineering Projects Showcase - First Place & Industry Award**

*Trinity College Dublin · IBM-sponsored Group 18 project · CSU33013 Software Engineering Project II*

[Original Team Repository](https://github.com/TCD-SWENG-Group-18-2024/CodeCraft) · [Showcase Poster](docs/assets/showcase-poster.png) · [Frontend Leadership](docs/FRONTEND-LEADERSHIP.md)

## Overview

CodeCraft is an AI-powered web application developed by an eleven-person student team at Trinity College Dublin in collaboration with IBM.

The project aimed to make AI-assisted software development more accessible through a unified interface supporting code analysis, generation, completion and translation. Users could submit code or natural-language prompts, select an appropriate model and receive task-specific responses.

Developed during the 2023–2024 academic year, CodeCraft combined frontend development, backend services, large language model integration, software testing, containerisation and collaborative project management.

The project was awarded **first place and the Industry Award** at Trinity College Dublin's 2024 Software Engineering Projects Showcase.

This repository is my personal fork of the original collaborative project, preserving the team's development history while documenting my contributions as a frontend and styling team lead.

## Features

| Feature | Description |
|---|---|
| Code Analysis | Submit code for AI-assisted analysis and feedback |
| Code Generation | Generate code from natural-language instructions |
| Code Completion | Produce suggestions for incomplete code |
| Code Translation | Translate code between supported programming languages |
| Multiple Input Methods | Submit code using text entry or file uploads |
| Model Selection | Choose between available AI model integrations |
| User Interface | Responsive React interface with reusable components and Material UI |
| User Accounts | Authentication and account-management functionality |
| Conversation Management | Submission history and conversation-related controls |
| API Integration | Communication between the React frontend, Flask backend and external model services |

Features were developed to varying degrees of completeness during the original project. Some depend on external services, configuration and credentials that may no longer be available.

## Technologies and Architecture

### Technology Stack

| Category | Technologies |
|---|---|
| Frontend | React, JavaScript, HTML, CSS |
| UI Components | Material UI, Emotion, Font Awesome |
| Backend | Python, Flask |
| API Development | REST APIs, HTTP, JSON |
| AI Integration | OpenAI, Hugging Face, LangChain |
| Data Management | SQLAlchemy, SQLite, Milvus integration |
| Authentication | Flask-Login, Flask-Bcrypt |
| Testing | Jest, React Testing Library, Python unit tests |
| Containerisation | Docker, Docker Compose, Nginx |
| Automation | GitHub Actions |
| Version Control | Git, GitHub |

### Application Architecture

CodeCraft follows a client-server architecture, separating the user interface from backend processing and AI-related operations.

**Frontend - React**

The frontend manages user interaction, navigation, code submission, file selection, model configuration and the presentation of responses.

**Backend - Flask**

The backend exposes HTTP endpoints for processing requests, handling authentication, managing files and communicating with external model services.

**AI Integration**

The model integration layer uses Python libraries and external services to support code-related tasks, including analysis, generation, completion and translation.

**Deployment**

The original project includes Docker configurations for the frontend and backend, Nginx configuration for serving the production frontend, and historical GitHub Actions workflows.

## Repository Structure

| Directory or File | Contents |
|---|---|
| [`frontend/`](frontend/) | React application, components, pages, styles and frontend tests |
| [`frontend/src/components/`](frontend/src/components/) | Reusable interface components |
| [`frontend/src/pages/`](frontend/src/pages/) | Application pages and user workflows |
| [`frontend/src/styles/`](frontend/src/styles/) | Component and page styling |
| [`backend/`](backend/) | Flask application, models, API integrations and tests |
| [`backend/requirements.txt`](backend/requirements.txt) | Python dependencies |
| [`frontend/package.json`](frontend/package.json) | Frontend dependencies and npm scripts |
| [`docker-compose.yml`](docker-compose.yml) | Container orchestration configuration |
| [`Makefile`](Makefile) | Historical automated setup commands |
| [`.github/workflows/`](.github/workflows/) | Original CI/CD workflows |
| [`docs/FRONTEND-LEADERSHIP.md`](docs/FRONTEND-LEADERSHIP.md) | My frontend development and leadership contributions |

## My Contributions

I contributed to CodeCraft as a **frontend team lead**, later taking responsibility for the styling workstream.

My responsibilities combined technical development, interface design, collaboration with other development teams and the organisation of frontend deliverables.

### Frontend Development

- Developed and refined React components and application interfaces.
- Contributed to the code-submission interface and its interaction flows.
- Worked on text entry, file uploads and submission handling.
- Contributed to model and use-case selection controls.
- Developed and improved interface styling using CSS and Material UI.
- Worked on frontend/backend communication and the presentation of API responses.
- Assisted with frontend testing and integration.

### Team Leadership

- Coordinated frontend contributors and allocated development responsibilities.
- Participated in sprint planning, progress reviews and task prioritisation.
- Communicated with backend and AI integration teams.
- Helped resolve blockers and organise work across the project.
- Supported project documentation, testing and showcase preparation.

These responsibilities describe areas I contributed to within the wider team rather than claiming sole authorship of individual features.

For a more detailed breakdown, see [Frontend Leadership and Contributions](docs/FRONTEND-LEADERSHIP.md).

---

## Installation and Setup

CodeCraft was originally developed and deployed in 2024.

The repository preserves the original team's **Docker Compose, GNU Make and manual development workflows**. These instructions document the historical project setup; current dependencies, external API integrations and deployment configurations have not been fully revalidated.

Some components require credentials from third-party services. Credentials are not included in the repository.

### Prerequisites

Depending on the selected installation method, you will need:

- Git
- An internet connection
- A terminal or command-line environment
- A modern web browser
- Docker Desktop and Docker Compose, for containerised execution
- GNU Make, for Makefile-based setup
- Python 3 and pip, for manual backend development
- Node.js and npm, for manual frontend development
- Valid API credentials and backend configuration

The original project used Python and Node.js tooling available in 2024. Compatibility with current versions may require additional configuration or dependency updates.

### Clone the Repository

Clone this portfolio fork:

```bash
git clone https://github.com/leahweldon/CodeCraft.git
cd CodeCraft
```

The original collaborative source repository remains available at:

https://github.com/TCD-SWENG-Group-18-2024/CodeCraft

### Environment Configuration

The application requires environment-specific configuration for backend services and frontend API communication.

#### Backend

Create a `.env` file in the `backend/` directory:

```text
backend/.env
```

The contents depend on the external services being used, including model provider credentials and application configuration.

The original configuration loads environment variables using `python-dotenv`. Required settings can be identified from the backend source files, including `config.py`, `codecraft.py` and `response.py`.

Do not commit real credentials, API tokens or authentication secrets.

#### Frontend

For local React development, create:

```text
frontend/.env
```

Add:

```dotenv
REACT_APP_BACKEND_URL=http://localhost:8080
```

This configures the frontend to communicate with a backend running locally on port `8080`.

The original project also referenced an IBM Cloud Code Engine backend deployment. That historical address is not assumed to remain operational.

**Note:** The frontend Dockerfile contains its own build-time backend URL configuration. Changing `frontend/.env` alone may not change the API destination in a containerised production build.

---

## Method 1 - Docker Compose

Docker Compose was the original recommended method of running the application in containers.

### 1. Install Docker

Install Docker Desktop and ensure the Docker engine is running.

Check that Docker and Docker Compose are available:

```bash
docker --version
docker compose version
```

### 2. Clone and Configure the Project

Clone the repository if you have not already done so:

```bash
git clone https://github.com/leahweldon/CodeCraft.git
cd CodeCraft
```

Create the required backend `.env` file and configure the appropriate service credentials.

For local frontend development, the original setup used:

```dotenv
REACT_APP_BACKEND_URL=http://localhost:8080
```

### 3. Start the Containers

From the repository root, the original project instructed developers to run:

```bash
docker compose up
```

This starts the services defined in `docker-compose.yml`, subject to the required images, build configuration and credentials being available.

**Historical configuration note:** The retained Compose file specifies the repository root as the build context for both services, while the Dockerfiles are located in `backend/` and `frontend/`. A fresh build may therefore require correcting the build contexts or explicitly specifying the Dockerfile paths.

The frontend Dockerfile also contains an original deployment-specific backend URL that may need updating for local execution.

### 4. Access the Application

The original local configuration exposes:

| Service | Address |
|---|---|
| React frontend | http://localhost:3000 |
| Flask backend | http://localhost:8080 |

Open the frontend address in a browser after both services have started successfully.

### 5. Stop the Containers

Stop the running process with `Ctrl + C`, then run:

```bash
docker compose down
```

This stops and removes the containers created by Docker Compose.

---

## Method 2 - GNU Make

The project includes a Makefile intended to automate dependency installation and application startup.

### 1. Install GNU Make

Ensure GNU Make is installed and available:

```bash
make --version
```

GNU Make documentation is available at https://www.gnu.org/software/make/.

You will also need Python, pip, Node.js and npm.

### 2. Clone and Configure the Project

```bash
git clone https://github.com/leahweldon/CodeCraft.git
cd CodeCraft
```

Create the backend environment configuration and set the frontend API URL as described above.

### 3. Install Dependencies and Launch

The original project used:

```bash
make all
```

The `all` target invokes dependency installation and application startup.

The Makefile also defines the following targets:

| Command | Purpose |
|---|---|
| `make install-dependencies` | Install backend and frontend dependencies |
| `make install-backend` | Install Python packages from `backend/requirements.txt` |
| `make install-frontend` | Install npm packages in `frontend/` |
| `make run-backend` | Launch the Flask backend |
| `make run-frontend` | Launch the React frontend |
| `make all` | Install dependencies and start the application |

**Platform compatibility:** The original `run-backend` target uses the Windows-specific `start /b` command. As a result, `make all` is not expected to work unchanged on macOS or Linux.

For a more portable development setup, use the manual instructions below.

---

## Method 3 - Manual Development Setup

The frontend and backend can be started separately, allowing developers to work directly on individual application components.

### 1. Backend Setup - Python and Flask

Navigate to the backend directory:

```bash
cd backend
```

#### Create a Python Virtual Environment

On macOS or Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

On Windows:

```powershell
python -m venv venv
venv\Scripts\activate
```

The virtual environment isolates the application's Python dependencies.

#### Install Dependencies

The original backend dependencies are listed in `requirements.txt`.

Install them with:

```bash
python -m pip install -r requirements.txt
```

This installs Flask and the other packages required by the original backend, including authentication, database and model-integration libraries.

Some packages are pinned to historical versions and may require a compatible Python environment.

#### Configure the Backend

Create and populate `backend/.env` with the required application settings and credentials.

The project's environment requirements depend on the backend functionality and external services being used.

#### Start the Flask Application

Run:

```bash
python codecraft.py
```

The original application configuration starts the backend at:

```text
http://localhost:8080
```

Keep this terminal open while running the frontend.

### 2. Frontend Setup - React

Open a second terminal window.

Navigate to the frontend directory from the repository root:

```bash
cd frontend
```

#### Install Dependencies

Install the npm packages declared in `package.json`:

```bash
npm install
```

#### Configure the Backend URL

Create `frontend/.env` if it does not already exist:

```dotenv
REACT_APP_BACKEND_URL=http://localhost:8080
```

#### Start the React Application

Run:

```bash
npm start
```

The original development setup serves the frontend at:

```text
http://localhost:3000
```

Open this address in your browser.

#### Stop the Application

Use `Ctrl + C` in the frontend and backend terminals to stop both development servers.

Deactivate the Python virtual environment when finished:

```bash
deactivate
```

### Frontend Build

The React application also defines a production build script:

```bash
cd frontend
npm run build
```

This uses `react-scripts build` to generate a production build in the frontend's `build/` directory.

The production frontend configuration must point to a suitable backend API.

---

## Testing

The project includes frontend tests, backend unit tests and automated workflow definitions.

### Frontend Tests

From the `frontend/` directory:

```bash
npm test
```

The test suite uses React's testing infrastructure, including Jest and React Testing Library.

### Backend Tests

The backend includes `junittest.py`, containing the original unit-testing implementation.

From the backend directory:

```bash
python -m unittest junittest
```

Some tests may require service credentials, compatible dependencies or a running backend.

### Historical CI/CD

The repository also preserves GitHub Actions workflows for frontend testing, backend testing, Docker image construction and deployment.

These workflows were developed for the original development environment and may reference historical branches, credentials and Docker Hub resources.

They should be treated as part of the project's original engineering implementation rather than as currently verified deployment pipelines.

---

## Project Recognition

CodeCraft was awarded **first place and the Industry Award** at Trinity College Dublin's **2024 Software Engineering Projects Showcase**.

The award was sponsored by Munich Re Automation Solutions and recognised the team's technical achievement, collaborative development and adaptability.

[View the Project Showcase Poster](docs/assets/showcase-poster.png)

[View the Award Announcement](https://www.linkedin.com/posts/munich-re-automation-solutions_congratulations-to-the-trinity-college-activity-7183824602916114433-FbLj)

## Team and Attribution

CodeCraft was developed collaboratively by **Group 18** at Trinity College Dublin.

The student team comprised:

- Fionn Murphy
- Leah Weldon
- Ben Feeney
- Gerard Moylan
- Roy Zheng
- Mariam María Quesada Ojeda
- Lucia Brown
- Wang Yinghao
- Abdullah Khan
- Patrick Archbold
- Yuchen Zhuang

The team worked with industry mentors from IBM, including Mihai Criveti, Ronan Dalton and Panpan Lin.

The [original Group 18 repository](https://github.com/TCD-SWENG-Group-18-2024/CodeCraft) preserves the collaborative project and development history.

This personal fork documents my involvement in CodeCraft while retaining the original team's authorship and contribution history.

## Academic Context

**Institution:** Trinity College Dublin  
**Module:** CSU33013 - Software Engineering Project II  
**Academic Year:** 2023-2024  
**Project:** CodeCraft - Revolutionising Software Engineering with AI  
**Industry Partner:** IBM  
**Team:** Group 18  
**Project Duration:** January-April 2024
