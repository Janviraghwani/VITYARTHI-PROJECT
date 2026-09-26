# Expense Tracker

A simple, menu-driven expense tracker written in Python. It runs in the terminal or any Python editor, needs no installation of extra packages, and saves your data to a CSV file.

## Features

- Add expenses with an amount, category, optional note, and date
- View all expenses in a neat table with a running total
- See a summary of spending by category, with percentages
- Delete an expense you entered by mistake
- Data is saved automatically and is still there next time you open the program

## Requirements

- Python 3.6 or newer
- No external libraries (only Python's built-in `csv`, `os`, and `datetime` modules)

Check your Python version with:

```bash
python --version
```

## Project Structure

```
expense_tracker/
├── expense_tracker_menu.py   # the main program
├── expenses.csv              # created automatically when you add your first expense
└── README.md
```

## How to Run

**Option 1: From an editor** (IDLE, VS Code, PyCharm, Thonny)

Open `expense_tracker_menu.py` and press Run (F5 in IDLE).

**Option 2: From the terminal**

```bash
cd path/to/expense_tracker
python expense_tracker_menu.py
```

On Mac/Linux you may need to use `python3` instead of `python`.

## Usage

When the program starts, you will see this menu:

```
===== EXPENSE TRACKER =====
1. Add expense
2. View all expenses
3. Summary by category
4. Delete an expense
5. Exit
Choose 1-5:
```

Type a number and press Enter.

### 1. Add expense

The program asks for:

| Prompt | Example | Notes |
|--------|---------|-------|
| Amount | `250` | Must be a number greater than 0 |
| Category | `food` | Free text, saved in lowercase. Defaults to `other` if left empty |
| Note | `Lunch` | Optional |
| Date | `2026-09-24` | Format `YYYY-MM-DD`. Press Enter to use today's date |

### 2. View all expenses

Shows every expense in a table with its number, date, amount, category, and note, plus the total.

```
No.  Date            Amount  Category    Note
-------------------------------------------------------
1    2026-09-24      250.00  food        Lunch
2    2026-09-20     1200.00  travel      Bus
-------------------------------------------------------
Total               1450.00
```

### 3. Summary by category

Shows how much you spent in each category, largest first, with the percentage of your total.

```
Spending by category
----------------------------------------
travel         1200.00   82.8%
food            250.00   17.2%
----------------------------------------
Total          1450.00
```

### 4. Delete an expense

Shows your expenses, then asks for the **No.** of the one to delete.

### 5. Exit

Closes the program. Everything is already saved.

## Where Is My Data Stored?

Expenses are saved in `expenses.csv` in the same folder as the program. Each line has four values:

```
date,amount,category,note
2026-09-24,250.0,food,Lunch
```

You can open this file in Excel or Google Sheets. To start fresh, delete `expenses.csv`.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `python is not recognized` or `command not found` | Try `python3`, or reinstall Python and tick "Add Python to PATH" |
| `No such file or directory` | Make sure your terminal is in the folder that contains the program (`cd` into it) |
| "Please enter a number" when adding | Type the amount using digits only, like `250` or `99.50` |
| "Wrong date format" | Use `YYYY-MM-DD`, for example `2026-09-24` |
| Program crashes after editing `expenses.csv` by hand | Make sure each row has exactly four values and the amount is a number |

## Ideas for Improvement

- Monthly budget with a warning when you go over
- Filter expenses by category or month
- Export a report
- Simple graphical interface with Tkinter
