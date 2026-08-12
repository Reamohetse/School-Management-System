# Que Technical Institute — School Management System

A single-page web application for managing student records, fee tracking, tool-box and uniform payments, and academic results for **Que Technical Institute**, a vocational training school with January and August intake cycles.

**Modern Minds. Modern Creatives.**
Ha Pita, Nts'irele · +(266) 63146060

---

## Features

- **Dashboard** — enrolment totals, fees/tool-box/uniform collection summaries, enrolment-by-course breakdown.
- **Students** — add, edit, and delete learner records (name, intake, course).
- **School Fees** — track amount paid and outstanding balance per student, per course.
  - Long-term courses (Carpentry & Joinery, Plumbing, Electrical Installation): **M1,200/month · M14,400 total**
  - Short-term courses (Interior Design, Leather Works & Upholstery): **M1,500/month · M9,000 total**
- **Tool-Box** — track payments toward the M4,500 tool-box fee.
- **School Uniform** — track payments toward the M1,000 uniform fee.
- **Academics / Results** — enter Term 1 & Term 2 Theory and Practical marks (score, out-of, weight), with automatic percentage and division:
  - 85–100: Passed with Distinction
  - 75–84: First Division
  - 60–74: Second Division
  - 50–59: Third Division
  - 40–49: Not Competent
  - 0–39: Repeat
  - View Marks also shows an overall average across both terms.
- **Reports** — download a PDF for one category at a time (Fees, Tool-Box, Uniform, or Results), filterable by intake and course.
- **Individual Result Slip** — download a per-student PDF result slip with institute letterhead, term breakdown, overall average, and signature lines.
- Course-specific filtering across every tab (Intake + Course dropdowns).

## Getting Started

This is a static site with no build step.

1. Clone the repo:
   ```bash
   git clone https://github.com/Reamohetse/School-Management-System.git
   cd School-Management-System
   ```
2. Open `index.html` directly in your browser, **or** serve it locally:
   ```bash
   python3 -m http.server 8000
   ```
   then visit `http://localhost:8000`.

No installation, server, or database is required — everything runs client-side.

## Data & Persistence

Student, fee, tool-box, uniform, and results data is stored in the browser's **`localStorage`**, scoped to the browser/device you're using. This means:

- Data persists across page reloads and browser restarts, on the **same device and browser**.
- Data does **not** sync between different computers, browsers, or users automatically.
- Clearing browser data/cache will erase the records.

The app ships pre-loaded with the actual January and August intake student lists (parsed from the institute's original spreadsheets). You can add, edit, or delete any student going forward.

If you need multi-device or multi-user syncing (e.g. Admin and Teachers on separate computers seeing the same live data), this would require a small backend/database — let us know if that's the next step.

## Project Structure

```
School-Management-System/
├── index.html          # Main application (HTML + CSS + JS, single page)
├── assets/
│   ├── logo.png         # Que Technical Institute logo
│   └── background.jpg   # Background photo
└── README.md
```

## Tech Stack

- Plain HTML, CSS, and JavaScript — no framework, no build tools
- [jsPDF](https://github.com/parallax/jsPDF) + [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable) (loaded via CDN) for PDF report generation
- Browser `localStorage` for data persistence

## License

Internal use for Que Technical Institute. Add a license of your choice if this repository is made public beyond institute use.
