# GitHub

## Sort activity map from Monday to Sunday

Display the activity map starting from Monday to Sunday, instead of Sunday to Saturday.

<img width="756" alt="Screenshot 2024-08-23 at 14 04 45" src="https://github.com/user-attachments/assets/42055734-dcd8-4520-8581-586fe1aa573f">


```
/* when the activity overview is enabled the grid rects are 10px * 10px (3px spacing) */
.ContributionCalendar-grid[style*="border-spacing: 3px"] {
    --dist: 13px;
}

/* but when it's disabled, they're 11px * 11px (4px spacing) */
.ContributionCalendar-grid[style*="border-spacing: 4px"] {
    --dist: 15px;
}

/* all days up a little */
.ContributionCalendar-grid tbody tr {
    transform: translateY(calc(var(--dist) * -1));
}

/* all sundays all the way down */
.ContributionCalendar-grid tbody tr:first-child {
    transform: translateY(calc(var(--dist) * 6));
}

/* hide first sunday (otherwise it'll be outside the box) */
.ContributionCalendar-grid tbody tr:first-child .ContributionCalendar-label + * {
    display: none;
}

/* show sunday text */
.ContributionCalendar-grid tbody tr:first-child .ContributionCalendar-label span:last-child  {
    clip-path: unset !important;
}
```
