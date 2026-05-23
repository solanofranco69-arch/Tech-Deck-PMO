# Tech Deck PMO

**Tech Deck PMO** is a Flask-based project operations dashboard for field and commercial teams. It centralizes budget visibility, inventory tracking, receivables management, payment scheduling, and proposal close-out into a single high-clarity control surface.

Live preview: [techdeckpmo.com](https://www.techdeckpmo.com)

---

## Features

- **Project lifecycle** — track each project from Proposal → Proposal Closing → Installation → Final Billing
- **Financial dashboard** — monitor budget, revenue, accounts receivable, and logged costs per project
- **Inventory management** — add, adjust (set / add / remove), and locate inventory items by category
- **Expenditure log** — record field spending per worker with date, category, and optional receipt photo
- **Receipt OCR** — automatically parse vendor, date, and amount from uploaded receipt images (requires Tesseract)
- **Payment intelligence** — milestone schedules, installment dates and amounts, payment methods, discount tracking
- **Client data capture** — name, company, contact info, and payment structure captured inline during Proposal Closing
- **Password reset** — secure token-based reset via email or console link
- **Role-based access** — Admin, Finance, and Field worker roles

---

## Tech stack

| Layer      | Technology                                   |
|------------|----------------------------------------------|
| Backend    | Python 3.11+, Flask, Flask-SQLAlchemy        |
| Database   | SQLite (auto-created on first run)           |
| Frontend   | Bootstrap 5 · custom dark glassmorphism UI  |
| OCR        | Tesseract · pytesseract · Pillow (optional) |
| Auth       | Werkzeug password hashing · session tokens  |

---

## Requirements

- Python 3.11+
- pip
- Tesseract *(optional — only needed for receipt OCR)*

---

## Install

```bash
# 1. Clone the repo
git clone https://github.com/solanofranco69-arch/Tech-Deck-PMO.git
cd Tech-Deck-PMO

# 2. Create and activate a virtual environment
python -m venv .venv

# macOS / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate

# 3. Install dependencies
pip install flask flask_sqlalchemy pillow pytesseract
```

> **OCR support:** install [Tesseract](https://github.com/tesseract-ocr/tesseract) and ensure it is on your `PATH` before running.

---

## Run locally

```bash
python "Tech Deck PM"
```

Open [http://127.0.0.1:5000](http://127.0.0.1:5000) in your browser.

---

## Demo accounts

Three accounts and a sample project (**Riverview Decking**) are seeded automatically on first run.

| Role    | Email                    | Password      |
|---------|--------------------------|---------------|
| Admin   | `admin@example.com`      | `admin123`    |
| Finance | `finance@example.com`    | `finance123`  |
| Field   | `worker@example.com`     | `worker123`   |

The demo project includes inventory items, an expenditure entry, and a milestone-based payment schedule so every section of the dashboard is populated on first launch.

---

## Environment variables

All variables are optional. Set them before running to enable email-based password reset.

| Variable               | Default             | Description                              |
|------------------------|---------------------|------------------------------------------|
| `SECRET_KEY`           | *(insecure default)*| Flask session secret — change in production |
| `MAIL_SERVER`          | `smtp.gmail.com`    | SMTP host                                |
| `MAIL_PORT`            | `587`               | SMTP port                                |
| `MAIL_USE_TLS`         | `true`              | Enable STARTTLS (`true` / `false`)       |
| `MAIL_USERNAME`        | —                   | SMTP login username                      |
| `MAIL_PASSWORD`        | —                   | SMTP login password                      |
| `MAIL_DEFAULT_SENDER`  | —                   | From address for reset emails            |

Without mail configuration the reset link is printed to the console instead.

---

## Project structure

```
Tech-Deck-PMO/
├── Tech Deck PM          # Flask application (single-file entry point)
├── docs/
│   ├── index.html        # GitHub Pages public landing page
│   └── CNAME             # Custom domain binding
├── uploads/              # Receipt image uploads (auto-created at runtime)
├── data.db               # SQLite database   (auto-created at runtime)
└── README.md
```

---

## License

MIT
