# 🚀 WATI-CLONE | WhatsApp Business Communication Dashboard

<p align="center">
  <b>A WhatsApp Business Communication Management Platform</b>
  <br/>
  Manage contacts, organize customer communication, create message templates and monitor messaging activities through a centralized dashboard.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-Frontend-blue?logo=react" />
  <img src="https://img.shields.io/badge/Node.js-Backend-green?logo=node.js" />
  <img src="https://img.shields.io/badge/Express.js-API-black?logo=express" />
  <img src="https://img.shields.io/badge/WhatsApp-Cloud%20API-25D366?logo=whatsapp" />
  <img src="https://img.shields.io/badge/Deployment-Vercel-black?logo=vercel" />
</p>

---

## 📌 About The Project

WATI-CLONE is a web-based WhatsApp Business communication dashboard inspired by WATI.

The project aims to simplify customer communication by providing businesses with a centralized platform to manage contacts, organize conversations, create reusable message templates and monitor messaging activities.

Instead of handling customer communication through multiple individual chats, businesses can use a unified interface to manage their communication workflow.

The application is designed with a modular architecture that separates frontend components, backend APIs, business logic and external messaging integrations.

It supports a Demo Mode for development and testing, with an architecture designed to support integration with the official Meta WhatsApp Cloud API.

## 🎯 Problem Statement

Businesses that communicate with customers through WhatsApp often face challenges such as:

- Managing large numbers of customer contacts.
- Organizing customer conversations.
- Reusing frequently sent messages.
- Monitoring communication activities.
- Tracking customer engagement.
- Maintaining an organized messaging workflow.

## 💡 Proposed Solution

WATI-CLONE provides a centralized dashboard that aims to solve these problems through:

- Contact management.
- Customer communication management.
- Reusable message templates.
- Broadcast campaign management.
- Message status tracking.
- Communication analytics.
- Centralized business settings.

## ✨ Features

### Implemented Features

- User Registration
- User Login and Authentication
- Email Verification
- Dashboard Interface
- Contact Management
- Add New Contacts
- Edit Contact Details
- Delete Contacts
- Search Contacts
- Persistent Contact Storage

### Planned / Integration Features

- WhatsApp Cloud API Integration
- Real-Time Incoming Messages
- Customer Conversation Inbox
- Message Sending
- Message Templates
- Broadcast Campaigns
- Delivery and Read Receipts
- Analytics and Reporting
- Business Account Settings

> Note: Features listed under planned/integration features should be moved to implemented only after successful end-to-end testing.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React.js | Frontend development |
| Vite | Frontend build tool |
| JavaScript | Application logic |
| Node.js | Backend runtime |
| Express.js | REST API development |
| PostgreSQL / Neon | Database architecture (confirm actual configured database) |
| Prisma ORM | Database access layer (if configured) |
| Meta WhatsApp Cloud API | WhatsApp messaging integration |
| Vercel | Deployment |

## 🏗️ System Architecture

The application follows a client-server architecture.

```text
                 USER
                   |
                   v
           REACT FRONTEND
                   |
                   v
            EXPRESS API
                   |
          BUSINESS LOGIC
                   |
          WHATSAPP SERVICE
              /       \
             /         \
         DEMO MODE    LIVE MODE
             |           |
             v           v
        MOCK SERVICE  META CLOUD API
             |           |
             +-----+-----+
                   |
                   v
               DATABASE
```

### Architecture Components

**1. Frontend Layer**

Built with React.js and Vite.

Responsibilities:
- User interface.
- Authentication screens.
- Dashboard.
- Contact management.
- Communication interface.
- API integration.

**2. Backend Layer**

Built using Node.js and Express.js.

Responsibilities:
- API request handling.
- Authentication.
- Contact management.
- Business logic.
- Message processing.
- Webhook handling.

**3. Database Layer**

Responsible for storing application data, such as:

- User information.
- Customer contacts.
- Message records.
- Templates.
- Campaign information.

**4. WhatsApp Integration Layer**

Designed to communicate with Meta's official WhatsApp Cloud API.

The messaging service is designed to support two providers:

- Demo Provider: Simulates WhatsApp messaging for development.
- Meta Provider: Handles actual WhatsApp API communication when credentials are configured.

## 📂 Project Structure

The following is a logical reference structure. Adjust it to match the actual folders in your repository.

```text
wati/
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── layout/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── assets/
│   │   └── app.js
│   │
│   ├── package.json
│   └── vite.config.js
│
├── backend/
│   ├── api/
│   │   └── index.js
│   ├── routes/
│   ├── controllers/
│   ├── services/
│   │   └── whatsapp/
│   ├── middleware/
│   ├── models/
│   ├── config/
│   └── package.json
│
├── .gitignore
└── README.md
```

## ⚙️ Installation & Setup

### Prerequisites

- Node.js
- npm
- Git
- Code editor (VS Code recommended)

### 1. Clone the repository

```bash
git clone https://github.com/tanmaypande/wati.git
```

```bash
cd wati
```

### 2. Install frontend dependencies

Navigate to the frontend directory:

```bash
cd frontend
npm install
```

Start the frontend:

```bash
npm run dev
```

### 3. Install backend dependencies

Open another terminal and navigate to the backend directory:

```bash
cd backend
npm install
```

Start the backend using the script configured in package.json.

## 🔐 Environment Configuration

Create a `.env` file in the backend directory.

```env
PORT=5000

WHATSAPP_MODE=demo

WHATSAPP_ACCESS_TOKEN=
WHATSAPP_PHONE_NUMBER_ID=
WHATSAPP_BUSINESS_ACCOUNT_ID=
WHATSAPP_API_VERSION=

WHATSAPP_VERIFY_TOKEN=
META_APP_SECRET=

DATABASE_URL=
```

**Important:**

- Use `WHATSAPP_MODE=demo` without Meta API credentials.
- Use `WHATSAPP_MODE=live` only after implementing and configuring the real provider.
- Never expose API tokens or secrets in frontend code.
- Never upload `.env` files to GitHub.

## 🔄 Demo Mode vs Live Mode

| Functionality | Demo Mode | Live Mode |
|---|---|---|
| Contact Management | Yes | Yes |
| Dashboard | Yes | Yes |
| Message Simulation | Yes | Not applicable |
| Real WhatsApp Messages | No | Yes |
| Real Delivery Receipts | No | Yes |
| Incoming WhatsApp Messages | Simulated | Webhooks |
| Meta API Credentials | Not required | Required |

Demo Mode allows developers to explore the application's messaging workflow without connecting an actual WhatsApp Business account.

Live Mode is intended to use the official Meta WhatsApp Cloud API.

## 🔗 API Endpoints

The following endpoints describe the intended API design. Verify actual route names and implementation before marking them as available.

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/health` | Backend health check |
| GET | `/webhook` | WhatsApp webhook verification |
| POST | `/webhook` | Receive WhatsApp webhook events |
| POST | `/api/messages/send` | Send a message |
| GET | `/api/contacts` | Retrieve contacts |
| POST | `/api/contacts` | Create a contact |
| PUT | `/api/contacts/:id` | Update a contact |
| DELETE | `/api/contacts/:id` | Delete a contact |

## 🌐 Deployment

Frontend: Vercel

Backend: Vercel

Configure the appropriate environment variables in the deployment dashboard before running the application.

Previously used deployment endpoints:

- Backend: https://wati-b.vercel.app
- Webhook: https://wati-b.vercel.app/webhook
- working link : https://wati-taupe.vercel.app/

## 🔒 Security Considerations

- Protect authentication routes.
- Validate incoming API requests.
- Store sensitive credentials in environment variables.
- Keep WhatsApp access tokens on the backend.
- Validate webhook signatures in Live Mode.
- Never commit private credentials to GitHub.

## 🚧 Future Improvements

- Real-time messaging with Meta Cloud API.
- WebSocket-based live conversations.
- Advanced campaign scheduling.
- Contact segmentation.
- Chatbot automation.
- Team member and agent management.
- Advanced analytics.
- Message template approval workflows.
- Role-based access control.

## 🎓 Project Purpose

This project was developed as part of practical software development and internship learning, focusing on full-stack web development, REST API architecture, authentication, database management and third-party API integration.

## 👨‍💻 Author

**Tanmay Pandey**

B.Tech CSE | Artificial Intelligence & Machine Learning

- GitHub: https://github.com/tanmaypande
- Portfolio: https://tanmaypandey.vercel.app/

---

<p align="center">
  <b>Built with curiosity, consistency and a passion for technology.</b>
</p>
