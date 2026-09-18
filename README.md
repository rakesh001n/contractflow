# ContractFlow Finance

ContractFlow Finance is a contractor project finance and operations management system. It is designed for contractors managing multiple water leakage, plumbing, electrical, maintenance, emergency repair, and AMC projects.

The core principle is:

> Every rupee must be traceable to a project, category, vendor or labourer, payment, and document.

## Product Vision

ContractFlow Finance helps a contractor answer the most important operational questions quickly:

- How many active projects are running?
- What is each project worth?
- How much has been spent on each project?
- Where was the money spent?
- How much have clients paid?
- How much is still receivable?
- How much is owed to vendors and workers?
- How much of the contractor's own money is invested in each project?
- Which projects are profitable or over budget?
- What is the current cash position?

## Current Frontend

This repository currently contains a frontend-first MVP built with Vite and vanilla JavaScript. It uses realistic Indian contractor finance mock data and is structured so a backend can be connected later.

Implemented workflows include:

- Financial dashboard with KPI cards, project health, cash flow, transactions, and investment summary
- Projects listing with project financial metrics
- Expenses and receivables views
- Fast Add Expense modal
- Contractor money invested calculation
- Investment report by project
- Finance navigation dropdown for Expenses, Receivables, Payables, and Cash Flow
- Light and dark themes with saved preference
- Responsive desktop, tablet, and mobile layout
- Global search across projects, vendors, expenses, payments, and workers
- Notifications dropdown and profile menu
- Profile settings, company settings, and help center pages
- Dynamic time-based dashboard greeting
- Accessible contrast improvements and reduced-motion support

## Application Areas

The planned product includes:

- Dashboard
- Projects and project details
- Expenses
- Client payments
- Receivables
- Payables
- Cash flow
- Unified transactions
- Vendors and vendor payments
- Labour, attendance, and labour payments
- Materials and usage
- AMC contracts and recurring expenses
- Documents, bills, receipts, contracts, and invoices
- Project profitability and financial reports
- Company and user settings

## Key Financial Calculations

The product is centered around project-level calculations:

```text
Contractor Money Invested = Project Expenses - Client Payments
Budget Utilization = Actual Project Expenses / Estimated Project Cost × 100
Outstanding Receivable = Contract Value - Client Payments
Estimated Profit = Contract Value - Estimated Project Cost
Actual Profit = Contract Value - Actual Project Expenses
```

These calculations make it possible to see how much of the contractor's own cash is currently tied up in each project.

## Fast Expense Entry

Adding a small expense should take approximately 10–15 seconds:

```text
Project → Category → Amount → Vendor → Payment method → Save
```

Optional details such as descriptions, receipts, and contractor-funded status can be added when needed.

## Design Direction

The interface follows a professional finance-focused SaaS style:

- Neutral light and dark themes
- Green for received money, profit, and positive values
- Red for overdue or negative values
- Amber for warnings and pending items
- Readable typography and accessible contrast
- Responsive tables, forms, cards, and navigation
- Subtle modern transitions without excessive animation

## Run Locally

Requirements:

- Node.js 18 or newer
- npm

Install dependencies and start the development server:

```bash
npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in a browser.

Create a production build:

```bash
npm run build
```

## Project Structure

```text
contractflow/
├── index.html
├── package.json
├── package-lock.json
├── src/
│   ├── main.js
│   └── style.css
└── README.md
```

## Planned Backend

The frontend is intended to connect to a backend without redesigning the UI. The recommended future stack is:

- Next.js API routes or Server Actions
- Supabase Auth
- Supabase PostgreSQL
- Supabase Storage for bills, receipts, contracts, and invoices

The main data relationships should eventually be:

```text
USERS
  │
  ▼
PROJECTS
  ├── EXPENSES ─── VENDORS
  ├── PAYMENTS ─── CLIENTS
  ├── LABOUR ───── WORKERS
  ├── MATERIALS
  └── DOCUMENTS
```

Every record should use stable IDs and reference its related project, vendor, client, worker, payment, or document where applicable.

## Roadmap

### V1: Finance MVP

- Login
- Dashboard
- Projects
- Project details
- Expenses
- Client payments
- Receivables
- Budget tracking
- Profit view
- Vendors
- Reports

### V2: Operations

- Labour and attendance
- Materials
- AMC contracts
- Recurring expenses
- Documents

### V3: Automation

- Notifications and reminders
- WhatsApp payment reminders
- Invoice generation
- PDF reports
- AI expense categorization
- AI financial insights

## Recommended Production Stack

For the full production version:

- Next.js with App Router
- TypeScript
- Tailwind CSS
- shadcn/ui
- Lucide icons
- Recharts
- React Hook Form
- Zod
- TanStack Table
- date-fns

The current MVP intentionally keeps the runtime lightweight while the workflows and product direction are validated.
