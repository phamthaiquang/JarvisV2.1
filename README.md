# JarvisV2.1
# 🧠 Product Requirements Document (PRD)  
## Project: **Jarvis Chatbot – Task & Expense Management System**  
**Version:** 1.0  
**Owner:** Phạm Thái Quang  
**Last Updated:** 17/10/2025

---

## 1. 📝 Project Overview

Jarvis Chatbot is a **multi-platform virtual assistant** (Android, Web, Desktop) designed to help users manage **personal expenses** and **daily tasks** through natural language conversations in Vietnamese.  
The system uses:

- **Frontend:** Flutter (Clean Architecture + Feature First + Riverpod)  
- **Backend:** Node.js (Express or Fastify) as an intermediate layer  
- **Database & Auth:** Supabase (PostgreSQL + Realtime + Email Verification)  
- **AI:** OpenRouter API (free LLMs) + voice trigger “Hey Jarvis”  

The goal is to deliver an assistant experience similar to Jarvis in Ironman—fast, personalized, context-aware, and capable of decision support.

---

## 2. 🎯 Product Goals

### 2.1 General Goal
Build an intelligent chatbot system that enables **natural language interaction** and effectively supports users in managing expenses and tasks.

### 2.2 Specific Objectives
- Provide a **simple and intuitive UI** built with Flutter.  
- Integrate a **Vietnamese-speaking AI chatbot** that can:
  - Answer general questions.
  - Perform CRUD operations on personal expense and task data.  
- Enable **user authentication** with Supabase (email verification).  
- Support **multi-device data sync** in real time.  
- Activate chatbot by voice trigger (“Hey Jarvis”).  
- Use Node.js as a secure intermediary between AI and database to protect sensitive data.

---

## 3. 👤 Target Users

| User Group | Description | Main Needs |
|------------|-------------|------------|
| Students | Young users with limited financial literacy | Expense tracking, study reminders, deadlines |
| Office workers | Users with many daily tasks | Task management, quick notes, decision support |
| General users | Non-tech users | Voice interaction, simple UI |

---

## 4. 🧩 Feature Scope

### 4.1 Core Features

#### a. **AI Chatbot**
- Natural language conversations in Vietnamese.  
- Context retention for multi-turn interactions.  
- Expense & task suggestions.  
- Voice activation using “Hey Jarvis”.

#### b. **Expense Management**
- Add, edit, delete income and expense entries.  
- Categorize expenses (Food, Education, Utilities, etc.).  
- Weekly/monthly statistics & charts.  
- Smart financial recommendations based on history.

#### c. **Task Management**
- Create, edit, mark complete, or delete tasks.  
- Categorize tasks (Study, Personal, Deadlines).  
- Push notifications for reminders.  
- Real-time synchronization across devices.

#### d. **Authentication & Profile**
- Sign up / log in using email (Supabase Auth).  
- Email verification required before access.  
- Manage personal profile (name, avatar, info).

---

## 5. 🏗️ System Architecture

```mermaid
flowchart LR
    subgraph Flutter App
        UI --> State(Riverpod State) --> API
    end

    API --> NodeJS[Node.js Backend]
    NodeJS -->|CRUD & Auth| Supabase[(Supabase DB)]
    NodeJS -->|Call| OpenRouter[OpenRouter API]
    Flutter App -->|Voice| STT[Speech-to-Text Engine]

Dùng MCP TASK MASTER để Export các task các việc cần làm



