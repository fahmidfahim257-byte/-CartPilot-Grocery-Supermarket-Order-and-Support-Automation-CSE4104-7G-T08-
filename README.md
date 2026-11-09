# 🛒 CartPilot
### Grocery & Supermarket Order and Support Automation

An AI-powered grocery and supermarket customer support and order-assistance platform designed for the Bangladeshi market.

---

## 📌 Project Overview

CartPilot is an AI-powered web application designed to simplify grocery shopping and automate customer support for grocery stores and supermarkets.

The system allows customers to interact with an AI chatbot in Bangla or English, search for grocery products using natural language, check product prices and stock availability, receive alternative product suggestions, place orders after confirmation, and track their order status.

It also provides a dedicated staff dashboard to manage products, inventory, orders, delivery rules, and customer support.

*Project Status:* Academic Course Prototype – In Development.

*Initial Scope:* One simulated grocery or supermarket store.

---

## 🎯 Problem Statement

Grocery and supermarket customers frequently need information about product availability, prices, brands, delivery charges, and order status. Store staff often handle these repetitive questions manually, which can lead to delays and inconsistent information.

CartPilot aims to address these challenges by combining AI-powered conversational support with database-verified product information and automated order management.

---

## 🎯 Project Objectives

- Provide AI-powered customer support in Bangla and English.
- Make grocery product searching easier through natural language.
- Provide accurate product prices and stock information.
- Automate shopping cart and order management.
- Suggest suitable alternatives for unavailable products.
- Help supermarket staff manage inventory and customer orders.
- Provide useful sales and business analytics.

---

## ✨ Proposed Features

### 1. Customer Features
- AI-powered Bangla and English chatbot.
- Smart grocery product search.
- Product price and stock checking.
- Alternative product suggestions.
- Shopping cart and order creation.
- Order status tracking.
- Human customer-support assistance.

### 2. Admin & Staff Features
- Product catalogue management.
- Inventory and stock management.
- Order management.
- Delivery zone and fee management.
- Low-stock alerts.
- Sales and product analytics.
- Customer-support request management.

### 3. Advanced AI Features
- Retrieval-Augmented Generation (RAG).
- Natural Language Understanding.
- Controlled AI Function / Tool Calling.
- Smart grocery list generation.
- Store FAQ and policy-based responses.

---

## 🛠️ Technology Stack

| Category | Technology |
|---|---|
| Frontend | Next.js (React.js), Tailwind CSS |
| Backend | Node.js, Express.js |
| Database | PostgreSQL |
| Vector Search | pgvector |
| Local AI Model | Qwen3.5:2b, Ollama |
| Embedding Model | multilingual-e5-small |
| AI Methods | RAG, Function Calling |
| API Testing | Postman |
| Software Testing | Jest, Playwright |
| UI Design | Figma |
| Version Control | Git, GitHub |
| Deployment | Vercel, Render |

---

## 🤖 AI Integration

CartPilot uses an AI model to understand customer requests and coordinate approved application functions.

The system plans to use:

- *RAG:* Retrieve relevant information from store FAQs, delivery rules, and policies.
- *Function Calling:* Search products, check stock, retrieve delivery information, and prepare order drafts.
- *Database Verification:* Retrieve actual product prices, stock quantities, and order information from the database.

For data integrity, the AI model will not directly access or modify the database. Backend validation will control all database operations.

Final order placement requires explicit customer confirmation.

---

## 📅 Project Development Plan

The project is planned to be completed within 10 weeks.

| Week | Planned Activities |
|---|---|
| 1–2 | Research, proposal, team formation, and repository setup |
| 3 | System design, SRS, ER diagram, and UI wireframes |
| 4–5 | Backend, database, frontend, and product management |
| 6 | AI integration, RAG, and function calling |
| 7–8 | Order automation, tracking, and customer support |
| 9 | Analytics, testing, and system integration |
| 10 | Deployment, documentation, and final presentation |

---

## 📌 Project Scope

The initial version will demonstrate one simulated grocery or supermarket store.

The following features are outside the scope of the initial 10-week development:

- Live payment gateway integration.
- Live courier service API integration.
- Facebook Messenger and WhatsApp integration.
- Voice-based ordering and native mobile applications.
- Production-scale multi-branch synchronization.

---

## 👥 Team Information

*Official Team Name:* CSE4104-7A-T01

*Course:* CSE4104 – Software Development III

*Section:* 7A

*Department:* Computer Science and Engineering (CSE)

*Institution:* Northern University of Business and Technology, Khulna

### Team Members

| No. | Name | Student ID | Responsibility |
|---|---|---|---|
| 1 | [Team Leader Name] | [Student ID] | Team Leader / Backend Developer |
| 2 | [Member 2 Name] | [Student ID] | Frontend Developer |
| 3 | [Member 3 Name] | [Student ID] | AI Integration Lead |
| 4 | [Member 4 Name] | [Student ID] | Database / Testing Lead |

All team members will contribute to integration, code review, testing, and documentation.

---

## 📂 Project Structure

text
CartPilot/
│
├── frontend/
├── backend/
├── database/
├── ai/
├── docs/
├── tests/
│
├── .env.example
├── .gitignore
└── README.md

---

## 🚀 Expected Outcome

The expected outcome is a working AI-powered grocery support and order automation web application that can understand customer queries in Bangla and English, search grocery products, verify prices and stock, suggest alternatives, create confirmed orders, and track order status.

The system will also provide a staff dashboard for managing products, inventory, orders, and customer support.

---

## 🔒 Security & Data Handling

- API keys and passwords will be stored in environment variables.
- User authentication and role-based access will be implemented.
- Backend validation will control AI tool requests.
- Customer confirmation will be required before order placement.
- Sensitive customer information will be protected.

---

## 📄 License

This project is developed for academic and educational purposes.

No open-source license has been selected yet. All rights are reserved by the project authors until a license is added.

---

*Course:* CSE4104 – Software Development III

*Team:* CSE4104-7A-T01

*Institution:* Northern University of Business and Technology, Khulna
Tulis
Tulis menyang Md Summy
