# Enterprise Natural Language BI & Inventory Analytics Agent

An AI-powered SQL query assistant built with n8n, Supabase (PostgreSQL), and Anthropic Claude/OpenAI. Converts complex business questions into precise SQL queries with strict security guardrails.

## Architecture
[User UI / Slack] -> [n8n Webhook API] -> [Schema-Aware LLM Agent] -> [Read-Only DB Role (Postgres)] -> [Formatted Markdown Output]

## Business Problem
Non-technical operations teams frequently rely on data analysts to fetch simple SQL reports, creating bottlenecks in daily decision-making.

## Key Technical Features
- **Schema-Constrained Text-to-SQL Generation:** Restricts LLM query synthesis to explicitly defined database schemas.
- **Least-Privilege Security:** Connects to PostgreSQL using isolated, read-only credentials to prevent unauthorized data manipulation.
- **Natural Language Aggregations:** Supports complex queries including multi-filter logic, SUM, AVG, and conditional sorting.
- **Execution Audit Trail:** Logs generated queries and execution times for observability and security auditing.

## Tech Stack
- **Orchestration:** n8n Workflow Automation
- **Database:** PostgreSQL (Supabase)
- **AI / LLM:** Anthropic Claude 3.5 Sonnet / OpenAI GPT-4o
- **Integration API:** REST / Webhooks