# Cleaning Bay

**Purpose:** Fix the problems identified in the Inspection bay.

Data rarely arrives clean. This bay covers the most common fixes you'll need to make before your data is trustworthy enough to analyze.

---

## What's in the notebook

- Drop duplicate rows
- Handle missing values (drop or fill)
- Standardize column names (strip whitespace, snake_case)
- Fix data types (convert columns to the correct type)
- Clean string columns (strip whitespace, normalize case)
- Filter out unwanted rows
- Drop unnecessary columns

---

## Pandas 3.x — Cleaning Patterns

With Copy-on-Write enabled by default, always reassign after any operation that modifies data:

```python
# Correct pattern
df = df.drop_duplicates()
df = df.dropna(subset=['important_column'])
df = df.reset_index(drop=True)
```

For string operations on `StringDtype` columns (new default in 3.x), the `.str` accessor still works the same way:

```python
df['name'] = df['name'].str.strip().str.lower()
```

---

## When to use this bay

- After running the Inspection bay and identifying issues
- Any time you receive updated or new data
- Before running any analysis or building any visualizations
