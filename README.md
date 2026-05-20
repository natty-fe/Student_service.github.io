# Student Academic Advisor System

A browser-based academic advising system that helps students manage completed courses, plan future courses, estimate GPA, check prerequisites, and understand graduation readiness.

## Main Features

### Sign In and Sign Up

Students can create an account or sign in to an existing account. Each student has their own saved course plan, completed courses, planned courses, GPA information, and custom course entries.

In the GitHub Pages version, student data is saved in the browser using local storage. In the Python server version, student data is saved in `data/students.json`.

### Completed Courses

Students can add courses they have already finished, including the grade they received. These courses are used to calculate the current GPA and completed credit progress.

The system also shows a visible completed-course list so students can review what they added. If a course was added by mistake, it can be removed.

### Planned Courses

Students can add courses they plan to take in a future term. Each planned course includes:

- course
- term
- meeting time
- expected grade

Planned courses are used for expected GPA, workload estimation, prerequisite checks, degree progress, and graduation eligibility prediction.

### Custom Course Entry

If a course is not listed in the dropdown, students can choose `+ Add course not listed`. They can enter:

- course code
- course title
- credits
- course area: major, core, or elective

Custom courses are saved with the student account and are included in GPA, credits, progress, and workload calculations.

### Course Recommendations

The recommendation engine suggests courses based on the student's current academic plan. It considers:

- completed courses
- planned courses
- prerequisites
- course difficulty
- degree value
- selected recommendation mode

Recommendation modes include:

- `Best fit`: balances readiness, progress, GPA fit, and difficulty.
- `Easiest`: favors lower-difficulty courses.
- `Fastest path`: favors courses that help degree progress faster.

Recommended courses include an `Add to plan` button.

### Prerequisite Checking

The system checks whether planned courses have their required prerequisites completed or in progress.

Status meanings:

- `Clear`: the course passes the prerequisite check.
- `Review`: the course needs attention because a prerequisite is missing or unfinished.

Example: if `CS340` requires `CS210` and the student has not completed `CS210`, the system marks `CS340` as `Review`.

### GPA and Expected GPA Calculator

The GPA calculator helps students estimate results before official grades are released.

It shows:

- `Current GPA`: calculated from completed graded courses only.
- `Expected GPA`: calculated from completed courses plus planned courses using expected grades.
- `Planned credits`: total credits from planned courses.

Students can change the expected grade for each planned course, and the expected GPA updates from those choices.

### Degree Progress Tracking

The system tracks progress toward the target credit requirement. It counts completed, in-progress, and planned courses toward overall progress.

It also separates progress by requirement type:

- major credits
- core/general education credits
- elective credits
- residency credits

### Graduation Eligibility Prediction

The eligibility section checks whether the student appears ready for graduation based on the current plan.

It checks:

- total credits
- major credits
- core credits
- minimum GPA
- capstone requirement
- schedule conflicts

Prediction meanings:

- `Met`: the requirement is currently satisfied.
- `Review`: the requirement still needs attention.
- `Needs review`: the full graduation plan is not ready yet.

### Workload and Credit Load Estimation

The system estimates whether each planned term is healthy, full, or over the credit limit.

Load meanings:

- `Healthy`: the term is within a comfortable credit range.
- `Full`: the term is close to the maximum credit limit.
- `Over limit`: the term has too many credits based on the selected max term credits.

It also gives a workload prediction based on course difficulty.

### Schedule Conflict Detection

The planner checks whether planned courses overlap in the same term. If two courses appear to have conflicting meeting times, the system creates an alert.

The `Auto-fix conflict` button can change conflicting meeting times to `TBD`, so the student can later choose non-overlapping sections.

### Open Alerts

Open alerts are the active warnings or reminders the student should review.

Alerts may include:

- registration deadline reminders
- schedule conflicts
- missing prerequisites
- GPA checkpoints

If Open Alerts shows `3`, that means the system found three things that need attention.

### Advisor AI

The Advisor AI is a local chat assistant that responds using the student's current academic context. It can answer questions about:

- GPA
- expected GPA
- course recommendations
- prerequisites
- graduation eligibility
- schedule conflicts
- workload difficulty
- registration deadlines
- how to add courses

Example questions:

- `What is my GPA?`
- `Recommend me a course`
- `Can I graduate?`
- `Do I have prerequisites missing?`
- `Is my workload hard?`
- `Do I have schedule conflicts?`

The advisor also handles friendly messages such as `hi` or `how are you`.

### Search

The search bar can find information about:

- courses
- GPA
- prerequisites
- alerts
- graduation
- schedule conflicts
- workload
- advisor help

Pressing Enter or clicking Search shows matching results immediately.

### Theme Toggle

The app includes a light/dark theme toggle. The selected theme is saved in the browser.

### Mobile Support

The interface is responsive and includes mobile-friendly layout behavior, compact header controls, and a floating AI button that stays visible while scrolling.

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

## GitHub Pages Version

The GitHub Pages version runs without a backend. In that mode, accounts and course data are stored in the browser's local storage for demo purposes.

## Project Files

- `index.html`: page structure
- `styles.css`: layout, theme, and responsive design
- `app.js`: advising logic, GPA calculation, course planning, search, and chat behavior
- `server.py`: optional local Python server for account storage
- `README.md`: project explanation and usage guide
