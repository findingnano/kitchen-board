# Kitchen board meals

Public meal plan for the kitchen Inky display. The Pi fetches this file with no login:

https://raw.githubusercontent.com/findingnano/kitchen-board/main/meals.json

The file on `main` is the Health Bot extract for 2026-09-28 through 2026-10-11. Replace `meals.json` on `main` when a new week is ready. Do not commit tokens or other secrets in this repo.

## Shape

Top-level object:

- `week_of`: ISO date of the first day in `days`
- `through`: ISO date of the last day in `days`
- `source`: short string saying where the plan came from
- `days`: oldest first, only days that were planned, 1 to 21 days

Each day:

- `date`: `YYYY-MM-DD`
- `weekday`: English name (`Monday` through `Sunday`)
- `breakfast`, `lunch`, and `dinner`: each a meal

Each meal:

- `name`: short string that fits a 7.3 inch screen
- `minutes`: integer from 0 to 1440
- `serves`: integer, 2 unless the plan says otherwise
- `ingredients`: list of short strings
- `steps`: list of short strings

Every planned day needs all three meals.
