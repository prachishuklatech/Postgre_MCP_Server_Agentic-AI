🚀 AI-Powered Dynamic Dashboard Generator (Secure Architecture)

This project demonstrates a secure, AI-driven dashboard generation system where dashboards are not hardcoded and not directly rendered by AI.

Instead, an AI Agent generates structured JSON chart schemas, which are then safely rendered by a React frontend using ECharts.
The system is designed with real-world constraints like security, scalability, and controlled data access in mind.

🧠 Architecture Overview (Second Approach)

Flow:

PostgreSQL Database
        ↓
     MCP Server
        ↓
     AI Agent
        ↓
   ECharts JSON
        ↓
   React Frontend

Why this architecture?

Frontend cannot query the database

Full datasets cannot be exposed

AI must not generate executable code

Dashboards must be fully dynamic

System must be secure against injection attacks

🔑 Key Idea

AI does NOT create charts.
AI creates JSON.
The frontend creates charts.

This separation ensures safety, flexibility, and maintainability.

🧩 Components Explained
1️⃣ PostgreSQL (Data Layer)

Stores structured civic / issue / analytics data

Raw data is never exposed to the frontend

Only aggregated or filtered data is accessed

2️⃣ MCP Server (Secure Data Mediator)

Acts as a controlled gateway between database and AI

Prevents:

Direct SQL access

Data leakage

Unauthorized queries

Only allows predefined, sanitized data views

3️⃣ AI Agent (Dashboard Intelligence)

Receives structured, limited data

Generates:

Chart type

Axes

Labels

Metrics

Output format is strict JSON only

No HTML, JS, SQL, or executable code

Example AI Output:

{
  "chartType": "bar",
  "title": "Issue Severity Distribution",
  "xAxis": ["Low", "Medium", "High", "Critical"],
  "series": [
    { "name": "Issues", "data": [45, 78, 32, 12] }
  ]
}

4️⃣ React Frontend (Visualization Layer)

Reads AI-generated JSON

Uses ECharts to render charts dynamically

No static cards

No hardcoded dashboards

New charts appear automatically based on AI output

🔒 Security Design

✔ No SQL access from frontend
✔ No raw database exposure
✔ JSON-only AI responses
✔ Injection-safe architecture
✔ Controlled data flow through MCP Server

This makes the system production-aligned and enterprise-ready.

📌 Features

AI-generated dynamic dashboards

JSON-based chart configuration

Secure backend-AI-frontend flow

Scalable and extensible design

Works with real databases

Frontend remains completely generic

🛠️ Tech Stack
Layer	Technology
Database	PostgreSQL
Secure Access	MCP Server
Intelligence	AI Agent
Visualization	ECharts
Frontend	React
Version Control	Git


🚀 How It Works (High Level)

Data is stored in PostgreSQL

MCP Server exposes only safe, aggregated views

AI Agent converts insights into JSON chart schemas

React frontend renders dashboards using ECharts

No manual UI changes needed

🧪 Why This Approach Matters

Matches real-world system constraints

Scales to large datasets

Keeps AI controlled and predictable

Enables AI-driven UI without security risks

Ideal for enterprise and public-sector systems

📈 Future Enhancements

Role-based dashboard views

Real-time updates

Multi-agent analytics

Dashboard explanation using LLMs

Caching for performance



🙌 Author
Prachi Shukla
shuklaprachimds@gmail.com
Built as part of a learning-driven exploration into AI agents, MCP servers, and secure system design.
