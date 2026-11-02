# Grade Titrator

An interactive course-grade calculator. Drag sliders, see your letter grade change, and find out what you need on everything left.

**Live site:** https://ia4252.github.io/Grade_Calculator/

## What it does

- Shows your current grade and how far you are from the next letter
- Solves for the score you need on an exam to reach a grade
- Maps two exams against each other, with a payoff curve for each score
- Shows what one more point is worth, and the grades you can still reach
- Simulates exam luck
- Handles drops, replacement rules, better-of rules, scale-ups, weighted scores, point-based scores, deductions, sliding cutoffs and rounding

## Presets

Fall 2026 at Duke University: Chem 101, Compsci 201, STA 198 and Writing 120. Each class page lists its rules and any assumptions.

Mark a score as Graded and every tool updates to plan only what is left.

You can create your own class, or import one from a CSV. Start from [`class-template.csv`](class-template.csv), and find the column guide under **Import class**. Share a class as a CSV or a class code. Neither includes scores.

## Privacy

There is no server, account or tracking. Scores and classes are saved in your own browser. Fonts load from Google Fonts.

## Run it

Open `index.html` in a browser. It is one file with no build step.

To host it, push this repo to GitHub, then go to **Settings → Pages**, choose **Deploy from a branch**, and select `main` and `/ (root)`.

## Disclaimer

This is an unofficial calculator, not affiliated with any university or course. Your instructor and official gradebook have the last word.

Coded with Claude. 
