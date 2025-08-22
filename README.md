# AI-Powered Ticket Management System

A smart ticket management system that uses AI to automatically categorize, prioritize, and assign support tickets to the most appropriate moderators.

---

## 🚀 Features

### AI-Powered Ticket Processing
- Automatic ticket categorization  
- Smart priority assignment  
- Skill-based moderator matching  
- AI-generated helpful notes for moderators  

### Smart Moderator Assignment
- Automatic matching of tickets to moderators based on skills  
- Fallback to admin assignment if no matching moderator found  
- Skill-based routing system  

### User Management
- Role-based access control (User, Moderator, Admin)  
- Skill management for moderators  
- User authentication with JWT  

### Background Processing
- Event-driven architecture using Inngest  
- Automated email notifications  
- Asynchronous ticket processing  

---

## 🛠 Tech Stack
- **Backend**: Node.js with Express  
- **Database**: MongoDB  
- **Authentication**: JWT  
- **Background Jobs**: Inngest  
- **AI Integration**: Google Gemini API  
- **Email**: Nodemailer with Mailtrap  
- **Development**: Nodemon for hot reloading  

---

## 📋 Prerequisites
- Node.js (v14 or higher)  
- MongoDB  
- Google Gemini API key  
- Mailtrap account (for email testing)  

---

## ⚙️ Installation

1. **Clone the repository**
   ```bash
    git clone <repository-url>
   cd ai-ticket-assistant
2. **Install dependencies**
   npm install
3. **Environment Setup**
   Create a .env file in the root directory with the following variables
   # MongoDB
MONGO_URI=your_mongodb_uri

# JWT
JWT_SECRET=your_jwt_secret

# Email (Mailtrap)
MAILTRAP_SMTP_HOST=your_mailtrap_host
MAILTRAP_SMTP_PORT=your_mailtrap_port
MAILTRAP_SMTP_USER=your_mailtrap_user
MAILTRAP_SMTP_PASS=your_mailtrap_password

# AI (Gemini)
GEMINI_API_KEY=your_gemini_api_key

# Application
APP_URL=http://localhost:3000
Running the Application

Start the main server:
npm run dev
Start the Inngest dev server:
npm run inngest-dev

API Endpoints
Authentication

POST /api/auth/signup – Register a new user

POST /api/auth/login – Login and get JWT token

Tickets

POST /api/tickets – Create a new ticket

GET /api/tickets – Get all tickets for logged-in user

GET /api/tickets/:id – Get ticket details

Admin

GET /api/auth/users – Get all users (Admin only)

POST /api/auth/update-user – Update user role & skills (Admin only)

🔄 Ticket Processing Flow

Ticket Creation

User submits a ticket with title and description

System creates initial ticket record

AI Processing

Inngest triggers on-ticket-created event

AI analyzes ticket content

Generates: required skills, priority, helpful notes, ticket type

Moderator Assignment

System searches for moderators with matching skills

Uses regex-based skill matching

Falls back to admin if no match found

Updates ticket with assignment

Notification

Sends email to assigned moderator

Includes ticket details and AI-generated notes

   
   git clone <repository-url>
   cd ai-ticket-assistant
