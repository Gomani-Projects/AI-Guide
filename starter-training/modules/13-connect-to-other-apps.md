# Module 13: Connect your tool to Excel, Power BI and other apps
`🟡 Moderate → 🔴 Hard` · 30–45 min

Most useful tools don't live alone. They take data **from** something and hand results **to** something else. You rarely need to connect apps directly: a well-shaped **file** in a shared folder is usually the simplest, safest bridge.

```
 Source app  ──export──►  your tool  ──writes──►  CSV / XLSX  ──import──►  Excel · Power BI · other apps
 (Excel, a specialist      (cleans, calculates,     (in a known folder
  app, a system export)     checks, combines)        or SharePoint)
```

## The three ways to connect

| Pattern | How it works | Level |
|---|---|---|
| **File hand-off** | Your tool reads an export and writes a CSV/XLSX that the other app imports | 🟢–🟡 |
| **Automation inside the app** | A script or macro that runs *inside* Excel, Power BI or another app | 🟡–🔴 |
| **Live connection** | The app reads directly from a database, SharePoint list or API | 🔴 (talk to IT) |

**Always agree the file format first.** Ask your AI to write it down: column names, units, date format (DD/MM/YYYY vs ISO `2026-09-25`), decimal places, and what "missing" looks like. Put it in your repo's README. Most integration bugs are format mismatches.

---

## Excel 🟡

| Want to… | Use | Ask your AI |
|---|---|---|
| Get your tool's output into Excel | Have your tool write **CSV** (or XLSX) | *"Make my tool save its results as a CSV with these columns: …"* |
| Pull in files automatically and refresh | **Power Query** (Data → Get Data → From File / From Folder) | *"Write Power Query steps to combine every CSV in a folder, fix the date column, and remove blank rows."* |
| Automate clicks in Excel | **Office Scripts** (Automate tab; works with Power Automate) or **VBA** macros (desktop) | *"Write an Office Script that formats this table and adds a total row."* |
| Do heavier calculations | **Python in Excel** (`=PY(`) where available, or a standalone Python script that reads/writes the workbook | *"Write a Python script using openpyxl that reads Sheet1, calculates …, and writes a new sheet."* |
| Add a button/panel to Excel | An **Office add-in** (🔴, deploy through IT) | |

**Try it with the sample data:** open [`projects/_sample-data/site-production.csv`](../projects/_sample-data/site-production.csv) in Excel, then ask your AI for a formula or Power Query step that shows tonnes per shift by site.

---

## Power BI 🟡

- **Get Data → Text/CSV, Excel, Folder or SharePoint folder.** Pointing Power BI at a **folder** your tool writes to is a simple, robust pipeline.
- **Power Query** cleans and shapes the data on the way in. AI is good at writing the M code: *"Write Power Query M to unpivot these month columns into Month and Value."*
- **DAX measures** do the calculations. *"Write a DAX measure for tonnes per operating hour, ignoring rows where hours are zero."*
- **Refreshing:** files on your own PC need an on-premises **data gateway** to refresh after publishing; files on **SharePoint/OneDrive** refresh without one. Prefer SharePoint.
- **Sharing:** publish to a company workspace and share with specific people or groups.
  ⚠️ **Never use "Publish to web".** It makes the report public to anyone on the internet.

---

## Specialist software 🔴

Most industries have their own specialist apps (CAD, scheduling, accounting, design or engineering tools). Most **import and export common formats** such as CSV/Excel tables, and some support **scripting/macros**. What's available depends on the product and **your version and licence**.

Common patterns:
- **Pre-process before import:** your tool cleans, validates or reformats a CSV (renames columns, converts units, checks for missing values) so the import works first time.
- **Post-process after export:** your tool reads an export (e.g. a schedule or report table) and produces a summary, a report, or a file for Excel/Power BI.
- **Automate inside the app:** where the product supports scripts or macros, AI can help write them, but **only with the official docs**.

⚠️ **AI tools often guess wrong about specialist software.** Always:
1. Give the AI a **real sample export** (with confidential values replaced) and the **exact** import/export spec from the product's help for your version.
2. Tell it: *"Only use features documented in the material I've given you. If you're not sure something exists, say so instead of guessing."*
3. Test on a **copy** of a project, never a live one.
4. Check with whoever administers the software before automating anything in shared projects.

---

## Exercise 🟡

In your own repo (Module 8), ask your AI:

> Build a small local tool (single HTML file, no installs) that lets me pick a CSV file like projects/_sample-data/site-production.csv, checks for missing or negative values and lists any problems, then lets me download a cleaned CSV with an extra column "tonnes_per_hour". Keep all processing in the browser; don't upload the data anywhere.

Open the cleaned CSV in Excel or Power BI.

## ✅ Checkpoint

- [ ] I know the three ways to connect tools and why file hand-off is usually the best start
- [ ] I agreed a file format (columns, units, dates) before building
- [ ] (Optional) I cleaned the sample CSV with my own tool and opened it in Excel or Power BI

← [Module 12](12-deploy-mobile-app.md) · **Next: [Module 14: Build a dashboard](14-build-a-dashboard.md)** →
