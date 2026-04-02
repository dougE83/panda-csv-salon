# Export Bay

**Purpose:** Write your processed data out to a file.

After cleaning, transforming, or analyzing your data, this bay handles getting it back out in the format you need.

---

## What's in the notebook

- Export to CSV
- Export to Excel (`.xlsx`)
- Export to JSON
- Export to Parquet

---

## Choosing an Export Format

| Format | Best for |
|---|---|
| CSV | Universal compatibility, sharing with anyone |
| Excel | Sharing with non-technical stakeholders |
| JSON | Web applications, APIs |
| Parquet | Large datasets, downstream data pipelines, preserves dtypes |

---

## Pandas 3.x Notes

**Parquet and Arrow:** Pandas 3.x uses Arrow-backed dtypes by default for strings. Parquet handles these natively, making it the most reliable format for round-tripping data without dtype loss.

**Excel:** Requires `openpyxl` (included in this repo's dependencies). For reading `.xls` files (old format), you would need `xlrd` separately.

---

## Output Location

By default, exports in this notebook go to the `parking_bay/` folder so your output stays alongside your input. Change the path in any cell to write elsewhere.

---

## When to use this bay

- After cleaning or transforming data that needs to be passed to another process
- When delivering a processed file to a stakeholder
- When saving an intermediate state of your data to pick up later
