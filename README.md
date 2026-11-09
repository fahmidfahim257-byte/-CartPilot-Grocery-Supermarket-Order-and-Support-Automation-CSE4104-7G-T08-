CartPilot
Grocery & Supermarket Order and Support Automation

CartPilot is an AI-powered grocery and supermarket customer support and order-assistance platform designed for the Bangladeshi market. It aims to help customers ask questions in Bangla or English, discover grocery products through natural language, check store-specific prices and stock, receive suitable alternatives for unavailable items, create orders after confirmation, and track order status. A staff dashboard supports product, inventory, order, delivery-rule, and customer-support management.
Project status: Academic course prototype in development. The first release is designed around one clearly labelled demo grocery store. It does not claim to be connected to a commercial supermarket.

Project Information
Item	Details
Project Title	CartPilot: Grocery & Supermarket Order and Support Automation
Course	CSE4104 — Software Development III
Institution	Department of Computer Science and Engineering, Northern University of Business and Technology, Khulna
Official Team Name	CSE4104-7A-T01
Section	7A
Planned Duration	10 weeks (approximately 2.5 months)
Target Users	Grocery customers, supermarket owners/managers, and customer-support or inventory staff in Bangladesh
Repository	[Add the GitHub repository URL]


Problem Statement
Grocery and supermarket customers regularly need information about product availability, selling prices, brands, pack sizes, delivery areas and fees, order status, and substitutes for unavailable items. Store staff may have to answer repetitive questions and manually check product or order records. When prices or stock information are outdated, customers can receive inconsistent information and orders may contain avoidable mistakes.

Existing online grocery services provide useful product catalogues and shopping workflows. CartPilot's course prototype focuses on combining bilingual conversational support with verified, database-backed product, inventory, delivery, and order operations in one application.
Objectives
- Build a responsive web application for grocery customers and supermarket staff.
- Provide customer assistance in Bangla and English, with basic Banglish query testing.
- Search grocery products by name, brand, category, budget, pack size, and unit.
- Retrieve store-specific selling prices and stock availability from the application database.
- Suggest suitable in-stock alternatives when an item is unavailable, subject to customer approval.
- Create and validate shopping carts and orders through controlled backend operations.
- Provide order tracking and human-support handoff for unresolved or sensitive requests.
- Provide staff with a dashboard for managing products, inventory, delivery settings, orders, and support requests.
- Evaluate AI grounding, tool execution, security, and end-to-end order completion using documented test cases.
Proposed Features
Core Features
1. Authentication and role-based access — Secure sign-in and permission checks for store administrators and support staff.
2. AI customer-support chat — A web chat interface for Bangla and English questions, with conversation history and relevant context.
3. Smart grocery product search — Search by product name, brand, category, budget, pack size, and unit. Natural-language requests are converted into structured search criteria.
4. Product catalogue and inventory management — Staff can add, edit, deactivate, categorize, and update product and stock records.
5. Database-verified price and stock checking — The backend retrieves store selling prices and available quantities from PostgreSQL. The AI must not invent these values.
6. Alternative product suggestions — Recommend similar available products based on category, brand, pack size, or price range. Customer approval is required before replacing an item.
7. Shopping cart and order creation — Add/remove items, change quantities, calculate totals on the server, validate stock, and create an order only after customer confirmation.
8. Order tracking — Customers can check their own order status through an authenticated or otherwise verified lookup.
9. Human-support handoff and history — Create a support request with relevant conversation and order context when staff assistance is required.
10. Admin dashboard — A unified workspace to manage products, stock, orders, conversations, and support requests.
Selected Advanced Features
- RAG knowledge base: Retrieve grounded answers from store-managed FAQs, delivery rules, return/refund policies, and product guidance.
- Delivery-zone and fee management: Allow administrators to configure supported delivery areas, fees, and basic delivery rules; the backend calculates the applicable fee.
- Low-stock alerts: Notify staff when an item falls below an administrator-defined stock threshold.
- Basic admin analytics: Show order counts, order statuses, popular products, common customer-query categories, and support-handoff counts.
- Smart grocery list: Let customers request multiple grocery items in one message or list and prepare a proposed cart for review.
- Bangladesh market-price reference: Display dated DAM/TCB market-price references separately from store selling prices. This is a reference feature, not a live retailer-price feed.
AI Integration
CartPilot uses an AI model to understand natural-language customer requests and coordinate approved application functions. Retrieval-Augmented Generation (RAG) is planned for store FAQs and policies, while controlled function/tool calling is planned for product search, stock checks, delivery information, order drafts, and order tracking.

AI safety and data-integrity rules:
- The language model will not directly read from or write to the database.
- The backend validates every tool request, user permission, store context, and input parameter.
- Product prices, stock quantities, delivery fees, order totals, and order statuses come from validated backend/database operations.
- Final order placement requires explicit customer confirmation.
- Unclear, unsupported, or sensitive requests can be escalated to human support.
Technology Stack
Layer	Proposed Technology	Purpose
Frontend	Next.js (React.js) + Tailwind CSS	Customer chat, product browsing, cart, and staff dashboard
Backend	Node.js + Express.js (REST API)	Authentication, validation, business rules, product/order APIs, and AI orchestration
Database	PostgreSQL	Users, products, variants, inventory, prices, customers, conversations, carts, orders, and support tickets
Vector retrieval	pgvector extension for PostgreSQL	Store and retrieve FAQ/policy embeddings, if supported by the selected host
Local LLM	Qwen3.5:2b via Ollama (CPU-first)	Laptop-friendly local prototyping for intent understanding and controlled tool-calling experiments
Optional LLM fallback	Hosted model endpoint, if required	Fallback if local-model Bangla quality or tool-calling results are insufficient
Embedding model	intfloat/multilingual-e5-small	Multilingual semantic retrieval for Bangla/English FAQ and policy content
AI methods	RAG + controlled function/tool calling	Ground policy answers and request approved backend operations
Testing and design	Postman, Jest, Playwright, Figma	API, unit, and end-to-end testing; interface prototyping
Version control	Git + GitHub	Team collaboration, branches, pull requests, issues, and documentation
Deployment	Vercel (frontend), Render or equivalent (backend), managed PostgreSQL	Host the web application and database


Hardware and Model Feasibility
The primary development laptop has 16 GB system RAM and Intel Iris integrated graphics. Therefore, the initial local model is Qwen3.5:2b through Ollama, using CPU-first inference, a short context window, and limited concurrency. Qwen3.5:4b may be tested only if memory usage and response time permit. A hosted inference endpoint is an optional fallback for stronger model capability; it is not a required dependency for the initial local prototype.
Proposed System Workflow
1. A customer submits a message through the web chat.
2. The backend sends the message and limited conversation context to the AI orchestration layer.
3. The AI retrieves relevant store-policy information or requests an approved backend function.
4. The backend validates the request, permissions, store context, parameters, and current database state.
5. The backend returns verified information or performs a permitted action. Order placement requires customer confirmation.
6. The AI presents the result in natural language. Uncertain or sensitive requests are routed to human support.
Data Sources and Data Handling
- Open Food Facts: May be used to import public packaged-product metadata, subject to API-use rules, data-quality checks, attribution, and applicable database/image licence terms.
- DAM and TCB public reports: May be used as dated Bangladesh market-price references. These reports will not be presented as guaranteed live APIs or as the demo store's selling prices.
- Demo store data: Store-specific selling prices, stock quantities, customers, and orders will be maintained in the application's database and clearly labelled as simulated unless independently verified.
Scope for the Course Prototype
The first release will demonstrate one simulated grocery/supermarket store and the complete customer-chat-to-order workflow. The core features and selected advanced features listed above are the planned course scope, with implementation prioritized around a working end-to-end flow.

Out of scope for the 10-week build:
- Live payment gateway or processing real customer payments.
- Live courier-company API integration or guaranteed real-time delivery tracking.
- Facebook Messenger, WhatsApp, or other social-channel integration requiring separate approvals.
- Voice-based ordering and native mobile applications.
- Production-scale multi-branch real-time synchronization.
- Automated refunds or other financial actions without staff review.
Team Information
Official Team Name: CSE4104-7A-T01
Section: 7A
Team Leader: [Full Name] — [Student ID]
No.	Member Name	Student ID	Initial Responsibility
1	[Team Leader Full Name]	[Student ID]	Team Leader / Backend Developer
2	[Member 2 Name]	[Student ID]	Frontend Developer
3	[Member 3 Name]	[Student ID]	AI Integration Lead
4	[Member 4 Name]	[Student ID]	Database / Testing Lead


All members are expected to contribute to integration, code review, testing, and documentation in addition to their primary responsibilities.
Initial Development Plan
Week	Planned Work	Expected Deliverable
1	Team formation, problem selection, initial research	Week 01 submission
2	Proposal, objectives, scope, team roles, GitHub repository, README	Project proposal and team information
3	SRS, use cases, architecture, ER diagram, API contracts, wireframes	System design package
4	PostgreSQL/backend setup, authentication, product catalogue, inventory APIs	Working authentication and catalogue/inventory
5	Customer chat, product search, cart, staff dashboard, API integration	Frontend connected to backend
6	LLM adapter, Bangla/English prompts, RAG, controlled tool calling	AI support with policy retrieval and product/stock tools
7	Cart, server-side totals, stock validation, confirmation, order creation	End-to-end order placement
8	Tracking, alternatives, human handoff, delivery zones/fees, grocery list	Complete customer support/order workflow
9	Low-stock alerts, analytics, functional/AI/security/integration testing	Tested integrated application
10	Deployment, documentation, README, user guide, demo, presentation	Deployed demo and final project package


Similar Systems for Initial Benchmarking
System	Publicly visible areas to study	CartPilot's planned focus
Chaldal	Online grocery catalogue, categories, product browsing, delivery/order workflow	Bangla/English conversational support, policy-grounded answers, and controlled stock/order tools
Shwapno Online	Online supermarket catalogue and grocery categories	Database-verified stock and customer-approved alternatives
Instacart	Grocery ordering, item replacement choices, order updates, customer help	A smaller educational prototype for substitution choices and human-support handoff


These systems are references for publicly observable workflows only. This project does not claim access to their internal systems, private APIs, or operational data.
Engineering Practices
- Use Git branches and pull requests for team collaboration and code review.
- Validate API inputs and AI tool arguments on the server.
- Keep API keys and secrets in environment variables; never commit them to the repository.
- Enforce authentication, role-based authorization, and store-scoped data access.
- Re-check stock during order confirmation and use database transactions to prevent inconsistent orders.
- Add unit, API integration, and end-to-end tests for core workflows.
- Maintain structured logs without storing passwords or unnecessary sensitive customer data.
- Document setup steps, API behavior, known limitations, and test results.
Suggested Repository Structure
cartpilot/
├── frontend/          # Next.js customer and staff interfaces
├── backend/           # Express REST API and business logic
├── database/          # Schema, migrations, seed/demo data
├── ai/                # LLM adapter, prompts, RAG and tool definitions
├── docs/              # Proposal, SRS, diagrams and user guide
├── tests/             # Unit, integration and end-to-end tests
├── .env.example       # Required environment-variable names (no secrets)
├── .gitignore
└── README.md
Getting Started
The repository structure and implementation are being developed. Setup commands, environment variables, database migrations, and run scripts will be documented here as the codebase is initialized.

Do not commit real .env files, API keys, passwords, private customer information, or production data.
Expected Outcome
The expected outcome is a working web-based grocery support prototype that can answer customer questions in Bangla or English, search a demo grocery catalogue, verify store-specific prices and stock through backend operations, suggest approved alternatives, create customer-confirmed orders, track order status, and escalate unresolved issues to staff. The project will include a staff dashboard, documented tests, source code, setup instructions, and a deployed demonstration where hosting and model availability permit.
License
No open-source project licence has been selected yet. Until a licence is added by the team, all rights are reserved by the project authors. Third-party product data, images, models, and libraries remain subject to their respective licences and terms.
Course: CSE4104 — Software Development III
Institution: Northern University of Business and Technology, Khulna
Team: CSE4104-7A-T01
