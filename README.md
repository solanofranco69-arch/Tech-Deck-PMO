# Tech Deck PM

A small Flask demo for managing projects, inventory, expenditures, receipt uploads, and password resets.

## Requirements

- Python 3.11+
- pip

## Install

1. Open a terminal in the same folder as `Tech Deck PM`.
2. Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install flask flask_sqlalchemy pillow pytesseract
```

> If you want OCR to work, install Tesseract on your machine and make sure it is on your PATH.

## Run locally

```bash
python "Tech Deck PM"
```

Then open:

- http://127.0.0.1:5000/

## Demo account

A demo user is created automatically on first run:

- Email: `admin@example.com`
- Password: `admin123`

## Environment variables (optional)

You can optionally set these for email-based password reset:

- `MAIL_SERVER`
- `MAIL_PORT`
- `MAIL_USE_TLS`
- `MAIL_USERNAME`
- `MAIL_PASSWORD`
- `MAIL_DEFAULT_SENDER`
- `SECRET_KEY`
