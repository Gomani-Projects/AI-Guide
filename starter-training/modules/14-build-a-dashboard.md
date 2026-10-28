# Module 14: Build a dashboard
`🟡 Moderate` · 30–45 min

A dashboard answers **a few specific questions at a glance**. The hard part isn't the charts. It's deciding what matters.

## 1. Plan it first 🟢

Answer these (or have your AI interview you):
- **Who** looks at it, and **how often**? (Supervisor every shift? Manager weekly?)
- **What 3–5 questions** should it answer? e.g. *Are we on target this week? Which site is behind? Is it getting better or worse?*
- **What data** does each question need, and **where does it come from**?
- **How fresh** must it be? (Live, daily, weekly?)
- **Who is allowed to see it?** (See [Module 10](10-data-security.md).)

## 2. Pick the right tool

| Tool | Best for | Sharing | Level |
|---|---|---|---|
| **Power BI** | Company dashboards, many data sources, scheduled refresh | Company workspace, with permissions | 🟡 |
| **Excel** | Quick dashboards on one workbook: PivotCharts + slicers | Share the file (SharePoint) | 🟢 |
| **Single-file HTML dashboard** | A local tool that visualises a CSV in the browser, no install | Share the file; data stays local | 🟡 |
| **Python (e.g. Streamlit)** | Analysts comfortable with Python; heavier calculations | Needs hosting (talk to IT) | 🔴 |

**If your workplace already uses Power BI, use it for anything shared.** Use the others for personal tools and prototypes.

## 3. Design rules that make dashboards useful

- **Top row = the key numbers** (e.g. total tonnes, % of target), large and clear.
- **One question per chart.** Title each chart with the question it answers.
- **Pick the simple chart:** line = trend over time; bar = compare categories; table = exact values. Avoid pies with more than 3 slices, 3-D charts and gauges.
- **Show the target or last period** so numbers have context.
- **Consistent colours:** one colour per site/category everywhere, red only for "needs attention".
- **Say when the data was last updated.**
- **Less is more.** If nobody acts on a chart, remove it.

## 4. Exercise: an HTML dashboard from the sample data 🟡

In your own repo (Module 8), copy [`projects/_sample-data/site-production.csv`](../projects/_sample-data/site-production.csv) into your folder and ask your AI:

> Build a single-file HTML dashboard (index.html, no installs; you may load Chart.js from a CDN) that lets me pick a CSV like site-production.csv. Show:
> 1. Key number tiles: total tonnes, total hours, average tonnes per hour
> 2. A line chart of tonnes per day
> 3. A bar chart of tonnes by site
> 4. A filter to choose a site
>
> Use clear titles that say what each chart shows, one consistent colour per site, and note the date range of the data. Keep all data in the browser; nothing is uploaded. Plan it first and wait for my OK.

Then improve it one step at a time: add a target line, highlight days below target in red, make it work on a phone.

## 5. Same thing in Power BI 🟡

1. **Get Data → Text/CSV** → choose the sample file → **Transform Data** (check the date and number types) → **Close & Apply**.
2. Add **Card** visuals for the key numbers, a **Line chart** (Date × tonnes), a **Bar chart** (Site × tonnes) and a **Slicer** for Site.
3. Ask your AI for any DAX you need: *"Write a DAX measure for average tonnes per operating hour."*
4. Publish to a company workspace only. **Never "Publish to web".**

## ✅ Checkpoint

- [ ] I wrote down who the dashboard is for and the 3–5 questions it answers
- [ ] I built a dashboard from the sample data (HTML, Excel or Power BI)
- [ ] Every chart has a title that says what question it answers

← [Module 13](13-connect-to-other-apps.md) · [Back to start](../README.md)
