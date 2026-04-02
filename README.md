# Panda's CSV Salon
<img width="2048" height="2048" alt="Gemini_Generated_Image_zegp47zegp47zegp" src="https://github.com/user-attachments/assets/4babae89-cff0-41db-a701-c13e41deef33" />

> A one-stop shop for working with CSV files using Python Pandas 3.x.

Welcome to the Salon. Think of it like a car repair shop for your data — park your file, choose a bay, do the work, drive away with a clean script.

---

## Getting Started

**Requirement:** [UV](https://docs.astral.sh/uv/) must be installed.

```bash
git clone https://github.com/dougE83/panda-csv-salon.git
cd panda-csv-salon
uv sync
uv run jupyter lab
```

That's it. UV handles the entire environment.

---

## How It Works

1. **Park your file** — drop your CSV into the `parking_bay/` folder
2. **Choose a bay** — pick the workshop that matches what you want to do
3. **Run the blocks** — each notebook has pre-built code blocks for common operations; delete any you don't need
4. **Generate a script** — run the final cell to export a clean `.py` script into the `scripts/` folder

---

## The Bays

| Bay | What it does |
|---|---|
| [Intake](bays/intake/README.md) | First look — shape, types, basic stats |
| [Inspection](bays/inspection/README.md) | Data quality — nulls, duplicates, outliers |
| [Cleaning](bays/cleaning/README.md) | Fix issues found in inspection |
| [Transformation](bays/transformation/README.md) | Reshape — pivot, melt, merge, new columns |
| [Analysis](bays/analysis/README.md) | Aggregate, correlate, summarize |
| [Visualization](bays/visualization/README.md) | Charts — histogram, bar, scatter, heatmap |
| [Export](bays/export/README.md) | Output to CSV, Excel, JSON, Parquet |

---

## Suggested Order

If you're new to the dataset or starting fresh:

**Intake → Inspection → Cleaning → Transformation → Analysis → Visualization → Export**

Already know what you need? Jump straight to that bay — each notebook is self-contained.

---

## Pandas 3.x

This repo is built for **pandas 3.x**. Key things to know if you're coming from older versions:

- **Copy-on-Write is default** — chained assignment no longer silently modifies the original DataFrame. The notebooks model the correct patterns throughout.
- **Strings are no longer `object` dtype** — string columns are now `StringDtype` (Arrow-backed) by default. Code that checks `dtype == 'object'` to detect strings needs updating.
- **`pd.read_csv()` has new defaults** — see the [Intake bay README](bays/intake/README.md) for a full breakdown.

---

## The Parking Bay

Drop any CSV files you want to work on into `parking_bay/`. Each notebook has a config cell at the top — set `CSV_FILE` to the name of your file. You can park multiple files at once (useful for merges in the Transformation bay).

Note: CSV files in `parking_bay/` are excluded from git by default. Your data stays local.

---

## Generating Scripts

Each notebook ends with a **Script Generator** cell. Before running it:

1. Delete any code blocks above that you don't want in the output
2. Run the Script Generator cell
3. A clean `.py` script is saved to `scripts/` — ready to run anywhere or share with others

Generated scripts are also excluded from git by default. Move or rename them if you want to commit them.

---

## Repo Structure

```
panda-csv-salon/
├── parking_bay/        ← drop your CSV files here
├── bays/
│   ├── intake/
│   ├── inspection/
│   ├── cleaning/
│   ├── transformation/
│   ├── analysis/
│   ├── visualization/
│   └── export/
└── scripts/            ← generated .py scripts land here
```
