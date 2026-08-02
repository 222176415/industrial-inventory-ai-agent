# Industrial Inventory AI Agent

An enterprise-grade, natural language text-to-SQL analytics system designed for manufacturing and warehouse operations. Built using **n8n**, **PostgreSQL**, and **Advanced LLMs**, this agent allows non-technical floor managers and inventory controllers to query complex parts inventories, supplier lead times, and equipment part usage in real-time.

---

## Architecture

```text
[ Operations / User Chat UI ]
             │
             ▼
     [ n8n Workflow API ] ─── (Injects Schema Context & Guardrails)
             │
             ▼
      [ LLM SQL Agent ]
             │
     (Generates Safe SELECT)
             │
             ▼
  [ PostgreSQL / Supabase ] ─── (Restricted Read-Only Database Role)
             │
             ▼
[ Formatted Markdown Insights ]

```

## Key Technical Features
- **Schema-Constrained Text-to-SQL Generation:** Restricts LLM query synthesis to explicitly defined database schemas.
- **Least-Privilege Security:** Connects to PostgreSQL using isolated, read-only credentials to prevent unauthorized data manipulation.
- **Natural Language Aggregations:** Supports complex queries including multi-filter logic, SUM, AVG, and conditional sorting.
- **Execution Audit Trail:** Logs generated queries and execution times for observability and security auditing.

## Tech Stack
- **Orchestration & Workflow:** n8n Workflow Automation
- **Database Engine:** PostgreSQL (Hosted on Supabase)
- **Database Access:**  PostgreSQL Read-Only Client (Least-Privilege Role)
- **AI & LLM Provider:** -
- **API & Trigge:** REST / Webhooks / Internal Chat Trigger
