# Devo Daily - Proverbs and Psalms Only

> "Your word is a lamp to my feet and a light to my path." - Psalm 119:105

Devo Daily is a lightweight, single-file devotional checklist focused on two Bible books: Proverbs and Psalms. It helps you keep a daily rhythm with a simple monthly tracker that works entirely in the browser.

## Features

- Monthly reading checklist for Proverbs and Psalms.
- Automatic day generation based on selected month and year.
- Proverbs plan: one chapter per day (Proverbs 1-31).
- Psalms plan: Psalms 1-150 distributed across the selected month.
- Completion tracking with progress stats:
- `Days done`
- `Days left`
- `Completed %`
- Local persistence using browser `localStorage`.
- Reset button to clear progress for the current month.
- Responsive layout with light/dark mode support.

## Tech Stack

- Native HTML
- CSS
- Vanilla JavaScript
- No external dependencies

## Project Structure

```text
.
|- bible_reading_plan_checklist.html
`- README.md
```

## Run Locally

1. Clone the repository:

```bash
git clone https://github.com/EE2506/Devo-Daily-Proverbs-and-Psalms-only-.git
cd Devo-Daily-Proverbs-and-Psalms-only-
```

2. Open `bible_reading_plan_checklist.html` in your browser.

No build step is required.

## Usage

1. Select month and year.
2. Mark each day as completed using the check button.
3. Track progress through the stats and progress bar.
4. Use `Reset month` if you want to start that month again.

## Notes

- Progress is stored per month and year in your browser only.
- Clearing browser storage will remove saved progress.

## Contributing

Suggestions and improvements are welcome through issues and pull requests.