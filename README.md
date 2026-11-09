# Grade Titrator

An interactive course-grade calculator. Drag sliders, see your letter grade change, and find out what you need on everything left.

**Live site:** https://ia4252.github.io/Grade_Calculator/

## What it does

- Shows your current grade and how far you are from the next letter
- Solves for the score you need on an exam to reach a grade
- Maps two exams against each other, with a payoff curve for each score
- Compares every ungraded score at once, showing what moves your grade and how possible semesters play out
- Shows what one more point is worth, and the grades you can still reach
- Simulates exam luck
- Handles alternate grading policies, drops, replacement rules, better-of rules, scale-ups, weighted scores, point-based scores, deductions, sliding cutoffs and rounding

## Classes

Fall 2026 at Duke University: Chem 101, Compsci 201, STA 198, Writing 120, Math 218D-2, BIO 201L, EGR 105L and PSY 101. Each class lists its rules and any assumptions.

Mark a score as Graded and every tool updates to plan only what is left.

Anyone can add their own class with **New class** or **Import class**. Those save in that person's browser. Share a class as a CSV or a class code. Neither includes scores.

When a syllabus offers alternate official policies, one class can include a grading-policy selector. Switching it recalculates everything without clearing the entered scores.

## Add a class for everyone

Upload a CSV to the [`classes`](classes) folder. It appears in everyone's Class menu after the site rebuilds.

[`CSV_GUIDE.md`](CSV_GUIDE.md) explains every row and column, and includes a prompt for making a CSV from a syllabus with AI. [`class-template.csv`](class-template.csv) is a filled-in example.

## Privacy

There is no server, account or tracking. Scores and classes you add are saved in your own browser. Fonts load from Google Fonts.

## Run it

Open `index.html` in a browser. It is one file with no build step. Classes from the `classes` folder only load when the site is hosted.

To host your own copy, push this repo to GitHub, then go to **Settings → Pages** and set **Source** to **GitHub Actions**. The workflow in `.github/workflows/pages.yml` builds the class list and deploys the site.

## Disclaimer

This is an unofficial calculator, not affiliated with any university or course. Your instructor and official gradebook have the last word.

Coded with Claude.
