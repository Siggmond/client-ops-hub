# ClientOps Hub

[![License](https://img.shields.io/github/license/Siggmond/client-ops-hub)](./LICENSE)
[![Top Language](https://img.shields.io/github/languages/top/Siggmond/client-ops-hub)](https://github.com/Siggmond/client-ops-hub)
[![Last Commit](https://img.shields.io/github/last-commit/Siggmond/client-ops-hub)](https://github.com/Siggmond/client-ops-hub/commits)
[![Repo Size](https://img.shields.io/github/repo-size/Siggmond/client-ops-hub)](https://github.com/Siggmond/client-ops-hub)
[![Open Issues](https://img.shields.io/github/issues/Siggmond/client-ops-hub)](https://github.com/Siggmond/client-ops-hub/issues)
[![Stars](https://img.shields.io/github/stars/Siggmond/client-ops-hub)](https://github.com/Siggmond/client-ops-hub/stargazers)

ClientOps Hub is a small internal workspace for managing clients, leads, and invoices with an auditable change history. It’s designed for teams that want a clear operational view without adopting a full enterprise CRM.

---

## Features

- **Authentication**
  - JWT-based login
  - Role-based access (`admin`, `staff`)
- **Clients**
  - Create, update, search
  - Archive / restore (soft delete)
- **Leads**
  - Pipeline status tracking (`new`, `contacted`, `qualified`, `lost`)
  - Archive / restore (soft delete)
- **Invoices**
  - Linked to clients
  - Lifecycle status (`draft`, `sent`, `paid`)
  - Archive / restore (soft delete)
- **Audit log**
  - Records write actions: `create`, `update`, `archive`, `restore`, `status_change`
  - Admin-only endpoint and UI
- **Pagination**
  - Server-side paging with response headers for totals and page metadata

---

## Tech Stack

**Backend**
- FastAPI
- SQLAlchemy
- Pydantic
- SQLite (local persistence)

**Frontend**
- Vue 3
- TypeScript
- Pinia
- Vue Router
- Axios

---

## Architecture

The repository is split into two independent applications:

- `backend/` — REST API, persistence, authentication/authorization, auditing
- `frontend/` — SPA UI, session management, routing, API client

---

## Screenshots

> All screenshots are taken from a live local run.

### 01-login.png
![Login](docs/screenshots/01-login.png)

### 02-dashboard.png
![Dashboard](docs/screenshots/02-dashboard.png)

### 03-clients-list-search-pagination.png
![Clients](docs/screenshots/03-clients-list-search-pagination.png)

### 04-client-create-form.png
![Client Form](docs/screenshots/04-client-create-form.png)

### 05-client-archived-state.png
![Archived Client](docs/screenshots/05-client-archived-state.png)

### 06-leads-pipeline.png
![Leads Pipeline](docs/screenshots/06-leads-pipeline.png)

### 07-lead-status-change.png
![Lead Status](docs/screenshots/07-lead-status-change.png)

### 08-invoices-table.png
![Invoices](docs/screenshots/08-invoices-table.png)

### 09-invoice-create-form.png
![Invoice Form](docs/screenshots/09-invoice-create-form.png)

### 10-audit-log.png
![Audit Log](docs/screenshots/10-audit-log.png)

### 11-rbac-staff-view.png
![RBAC](docs/screenshots/11-rbac-staff-view.png)

---

## Local Development

### Backend

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r backend\requirements.txt
cd backend
uvicorn app.main:app --reload --port 8000
```

### Frontend

```powershell
cd frontend
npm install
npm run dev
```

---

## Initial Accounts

- **Admin** — `admin / admin123`
- **Staff** — `staff / staff123`
