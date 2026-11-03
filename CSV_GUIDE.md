# Class CSV guide

A class CSV describes how a course is graded. It never holds anyone's scores.

There are two ways to use one:

- **For everyone:** add it to the [`classes`](classes) folder.
- **Just for you:** click **Import class** on the site and choose the file. It saves in your browser only.

## Quick start

1. Copy [`class-template.csv`](class-template.csv) and open it in a spreadsheet.
2. Change the rows to match your syllabus.
3. Save it as a CSV.

Each row has a `kind`, and only some columns apply to each kind. Leave the others blank. The first row must keep the column names.

```
kind,name,value,weight,scores,drop,out_of,score_weights,scale_up,exam,score_names,step
```

A small class looks like this:

```csv
kind,name,value,weight,scores,drop,exam,score_names
setting,class,Biology 101,,,,,
setting,semester,Fall 2026,,,,,
setting,professor,Prof. Example,,,,,
setting,university,Example University,,,,,
setting,source,Fall 2026 syllabus,,,,,
category,Midterms,,50,2,,yes,
category,Final,,30,1,,yes,
category,Homework,,20,10,1,,
grade,A,90,,,,,
grade,B,80,,,,,
grade,C,70,,,,,
grade,D,60,,,,,
grade,F,0,,,,,
```

Only a `class` setting and at least one `category` row are required. Without `grade` rows, the class uses A+ 97 down to D− 60.

## Row kinds

### `category`: a graded part of the class

| Column | Meaning | Example |
|---|---|---|
| `name` | Category name | `Homework` |
| `weight` | Percent of the course grade | `20` |
| `scores` | How many separate scores share that weight | `10` |
| `drop` | How many of the lowest scores to drop | `1` |
| `out_of` | Points, if scores aren't percents | `280` |
| `score_weights` | Uneven weights, separated by semicolons | `1;1;2;2` |
| `scale_up` | `yes` if the class scale-up applies | `yes` |
| `exam` | `yes` if the planner should start on it | `yes` |
| `score_names` | Custom names, separated by semicolons | `Quiz A;Quiz B` |

With several scores, names are numbered automatically, so `Midterms` becomes `Midterm 1`, `Midterm 2` and so on.

If a syllabus doesn't give the number of assignments, use one score and enter your average.

### `grade`: a letter and its minimum

`name` is the letter and `value` is the minimum, such as `grade,A,93`. Letters can be up to 6 characters. The lowest grade should have a minimum of `0`.

### `date`: a key date shown at the top

`name` and `value`, such as `date,Final,Dec 12`.

### `note`: extra text in the class's rules list

Use this for assumptions and anything a reader should check, such as `note,Weights,The syllabus says these may change.`

### `deduction`: points taken off the final grade

| `value` | Meaning |
|---|---|
| `5 per after 3` | 5 points off for each one past 3 |
| `4=5; 6=15; 8=F` | At 4 lose 5 points, at 6 lose 15, at 8 fail |

Use the `step` column if half steps are possible, such as `0.5`.

### `setting`: details and rules

Put the setting in `name` and its value in `value`.

| Setting | Meaning |
|---|---|
| `class` | Short class name |
| `title` | Full title or section |
| `semester` | Such as `Fall 2026` |
| `professor` | Instructor |
| `university` | School |
| `source` | Where the rules came from and when it was added |
| `description` | A short line under the title |
| `replace_with`, `replace_in` | A score that replaces the lowest score in a category if higher, such as `Final` and `Tests` |
| `better_of_category`, `better_of_with` | Each score keeps the better of itself and its match in another category with the same number of scores |
| `scale_up_multiply`, `scale_up_add`, `scale_up_cap` | The scale-up amount. Set both multiply and add to get a switch between the two. |
| `plan_first`, `plan_second` | The two scores the planner starts on |
| `rounding` | `none`, `half` or `whole` |
| `cutoffs_slide` | `yes` to add a slider for lower cutoffs |
| `deduction_limit` | The most deductions can take off, with a switch to turn the limit on or off |

## Make one with AI

Paste this into an AI assistant along with your syllabus, then check the result against the syllabus:

```text
Turn this syllabus into a Grade Titrator class CSV. Follow the attached CSV_GUIDE.md
exactly. Use the columns from class-template.csv. Include the class, title, semester,
professor, university and source settings. Only use rules the syllabus states. If the
syllabus leaves something out, such as how a category splits, use the simplest reading
and add a note row saying so. Give me only the CSV.
```

## Add a class for everyone

Upload the CSV to the [`classes`](classes) folder. Use a filename with only letters, numbers, dashes, dots and underscores, such as `biology-101-fall-2026.csv`.

The site rebuilds on its own, and the class appears in everyone's Class menu within a few minutes. To remove a class, delete its file.

Test a new CSV with **Import class** first. If a file in the folder has an error, the site skips it and the other classes still load.

Grading policies change, so put the semester in the filename and the `source` setting.
