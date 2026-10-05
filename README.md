# n8n-AI-Task-Automation

An AI-powered task tracking and reminder system built using **n8n, Google Gemini, Google Sheets, and Google Calendar**.

The system allows users to manage tasks through a simple chat interface instead of manually entering information into spreadsheets or creating calendar events. The AI Agent understands the user's message, collects the required information, maintains the conversation context, and performs the required actions automatically.

---

## 📌 Project Overview

Managing small tasks, deadlines, tests, meetings, and reminders often requires switching between different applications.

For example, a user may need to:

- Write down a task
- Record its deadline
- Mention who or what the task is related to
- Specify whether it is online or offline
- Update the task status
- Create a calendar reminder

This project brings these activities together into a single **chat-based automation workflow**.

The user communicates with the system using natural language. The AI Agent understands the request and uses connected tools to store and manage the task.

### Example

Instead of manually entering a task into a spreadsheet, the user can simply say:

> "I have a college test on 29 January. It is offline."

The AI Agent understands the information and can maintain the corresponding task details.

The task can then be stored in **Google Sheets**, while **Google Calendar** can be used to manage the deadline and reminder.

---

# 🎯 Objectives

The main objectives of this project are:

- To build a **chat-based task management system**
- To use **Generative AI** for understanding natural-language instructions
- To automate task creation and updates
- To reduce manual data entry
- To maintain conversation context using AI Agent memory
- To connect different applications through an automated workflow
- To demonstrate how **AI Agents and workflow automation** can work together

---

# 🏗️ System Architecture

The system consists of several components working together:

```text
                ┌──────────────────────┐
                │       User           │
                │  Chat Interface      │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │    Chat Trigger      │
                │  n8n Chat Interface  │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │      AI Agent        │
                │                      │
                │ Understands request  │
                │ Manages conversation │
                │ Decides actions      │
                └───────┬──────┬───────┘
                        │      │
              ┌─────────┘      └──────────┐
              ▼                           ▼
    ┌──────────────────┐        ┌──────────────────┐
    │  Google Gemini   │        │   AI Memory      │
    │   Chat Model     │        │ Conversation     │
    └──────────────────┘        │ Context          │
                                └──────────────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │   Automation Tools   │
             └──────────┬───────────┘
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
    ┌──────────────────┐  ┌──────────────────┐
    │  Google Sheets   │  │  Google Calendar │
    │ Task Storage     │  │ Deadlines &      │
    │ & Tracking       │  │ Reminders        │
    └──────────────────┘  └──────────────────┘
