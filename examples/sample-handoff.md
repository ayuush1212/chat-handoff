# Handoff: Personal Budget Tracker

**Progress: roughly 60% done**

## 1. Project goal
Build a simple web page that tracks monthly spending by category and shows a summary chart.

## 2. Done so far
- HTML layout with an expense form (amount, category, date)
- JavaScript that saves entries in memory and lists them
- Category totals calculated correctly

## 3. Not done yet
- Chart is not drawn yet
- Entries disappear on refresh (no storage)
- No mobile styling

## 4. Key decisions
- Plain HTML, CSS and JavaScript, no framework, to keep it easy to host for free
- Categories fixed to: Food, Transport, Bills, Fun, Other

## 5. Important content
```js
function totalsByCategory(entries) {
  return entries.reduce((acc, e) => {
    acc[e.category] = (acc[e.category] || 0) + e.amount;
    return acc;
  }, {});
}
```

## 6. Where we stopped
About to add a bar chart using Chart.js and read from `totalsByCategory`.

## 7. Next steps
1. Add Chart.js and render a bar chart from the totals
2. Save entries to localStorage and load them on page open
3. Add basic mobile styling
4. Deploy to a free host

## 8. Paste-ready prompt
I'm building a budget tracker in plain HTML/CSS/JS. The expense form and category totals work (function below). Next I need a Chart.js bar chart from the totals, then localStorage saving, then mobile styling. Here is my function: [paste code from section 5]. Start with the chart.
