# Student Academic Advisor System

A browser-based academic advising system for students.

## Features

- Student sign up and sign in
- Local saved student accounts in the browser
- Student-managed completed course entry
- Student-managed planned course entry
- Course recommendation engine
- Prerequisite checking
- GPA and projected GPA calculations
- Degree progress tracking
- Graduation eligibility prediction
- Course difficulty and workload estimation
- Schedule conflict detection
- Registration and deadline alerts
- Advisor-style chat using the student's own course plan

## Run With Python

```bash
python server.py
```

Then open:

```text
http://127.0.0.1:8000
```

The Python server stores student accounts and course data in `data/students.json`.

## Run Static Version

Open `index.html` in a browser. No installation is required.

## Notes

The GitHub Pages version still runs without a backend. In that mode, accounts and course data are stored in the browser's local storage for demo purposes.
