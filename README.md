# Node.js Application Deployment on AWS EC2

## Introduction

This project demonstrates deploying a Node.js application on an AWS EC2 instance running Amazon Linux 2023. It covers Git installation, cloning the application repository, installing Node.js and npm, managing application dependencies, and running the application using PM2.

## Objectives

- Configure an AWS EC2 instance for Node.js deployment.
- Install Git, Node.js, and npm.
- Clone the application repository from GitHub.
- Install application dependencies.
- Run the Node.js application on port 3000.
- Manage the application process using PM2.

## Architecture

**Application Flow:**

<img width="2069" height="760" alt="image" src="https://github.com/user-attachments/assets/e295f9ef-518d-4c64-9d29-553a4d563d88" />


User / Browser → Internet → AWS EC2 Instance → Amazon Linux 2023 → Node.js Application → Port 3000

The application runs on an EC2 instance. Git is used to retrieve the source code, npm manages dependencies, Node.js executes the application, and PM2 manages the running process.



## Technologies Used

| Technology | Purpose |
|---|---|
| AWS EC2 | Cloud server hosting |
| Amazon Linux 2023 | Operating system |
| Git | Source code version control |
| GitHub | Source code repository |
| Node.js | JavaScript runtime |
| npm | Dependency management |
| PM2 | Node.js process management |

## Deployment Steps

### 1. Launch and Connect to EC2

Launched an EC2 instance using Amazon Linux 2023 and connected through SSH.

### 2. Update the System

```bash
sudo yum update
```

### 3. Install Git

```bash
sudo yum install git -y
```

Verified the installation:

```bash
git --version
```

### 4. Install Node.js

```bash
sudo yum install nodejs -y
```

Verified the Node.js version:

```bash
node --version
```

### 5. Install npm

```bash
sudo yum install npm -y
```

Verified the npm version:

```bash
npm --version
```

### 6. Clone the GitHub Repository

Cloned the Node.js application repository and navigated to the project directory.

```bash
git clone <GitHub-Repository-URL>
cd node
```

Replace the repository URL with the actual URL you used when cloning.

### 7. Check Application Files

```bash
ls
```

The application directory contained files such as:

- `app.js` — Application entry point
- `package.json` — Project metadata and dependencies
- `package-lock.json` — Dependency lockfile
- `node_modules/` — Installed dependencies

### 8. Install Application Dependencies

```bash
npm install
```

This installs the dependencies defined in `package.json`.

### 9. Run the Node.js Application

```bash
node app.js
```

The terminal displayed:

```text
App listening at http://localhost:3000
```

### 10. Install PM2

Installed PM2 globally to manage the Node.js application process.

```bash
sudo npm install -g pm2
```

### 11. Start the Application with PM2

```bash
pm2 start app.js
```

PM2 manages the application process and allows it to run in the background.

### 12. Verify the Application Process

```bash
pm2 status
```

## Screenshots

- EC2 instance details:

<img width="1898" height="545" alt="Screenshot 2026-10-23 190346" src="https://github.com/user-attachments/assets/20287c35-889a-41e8-9455-a2d4c2c5ff42" />

- Node.js and npm:
<img width="1398" height="452" alt="Screenshot 2026-10-23 190633" src="https://github.com/user-attachments/assets/ba4da22a-b190-45b4-8f25-882b55dcce8b" />

- Application running on port 3000:
<img width="938" height="280" alt="Screenshot 2026-10-23 190625" src="https://github.com/user-attachments/assets/bd3f6252-dd8c-4b56-bb2a-75acf84e1218" />

- PM2 process status:
- <img width="829" height="270" alt="image" src="https://github.com/user-attachments/assets/a0942ec0-2601-4c56-bd88-612d39434072" />


## Key Learnings

- AWS EC2 setup and Linux administration
- Installing Git, Node.js, and npm
- Cloning application code from GitHub
- Managing Node.js dependencies
- Running an application on port 3000
- Using PM2 for process management
- Documenting cloud deployment projects

## Summary

Deployed a Node.js application on AWS EC2 using Amazon Linux 2023. Installed Git, Node.js, npm, and PM2, cloned the application repository, installed dependencies, and started the application using PM2.

