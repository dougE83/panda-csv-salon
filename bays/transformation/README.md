# Transformation Bay

**Purpose:** Reshape and restructure your data to get it into the shape you need.

Cleaning fixes problems. Transformation changes the structure — adding columns, combining datasets, pivoting rows to columns, and more.

---

## What's in the notebook

- Add calculated columns
- Rename columns
- Reorder columns
- Group by and aggregate
- Pivot table (long to wide)
- Melt (wide to long)
- Merge / join two DataFrames
- Concatenate DataFrames
- Apply custom functions

---

## Key Concepts

**Merge vs Concat**
- `pd.merge()` — joins two DataFrames on a shared key column (like a SQL JOIN)
- `pd.concat()` — stacks DataFrames on top of each other (or side by side)

**Pivot vs Melt**
- Pivot makes a DataFrame wider (rows become columns)
- Melt makes a DataFrame longer (columns become rows)

**GroupBy**
- Groups rows by one or more columns, then applies an aggregation function
- Most common pattern: `df.groupby('col').agg({'value_col': 'sum'})`

---

## Pandas 3.x Notes

GroupBy behavior is more consistent in 3.x. The `.agg()` method is the preferred way to aggregate — avoid chaining `.sum()`, `.mean()` etc. directly off `.groupby()` for anything beyond simple cases.

---

## When to use this bay

- After cleaning, when you need to reshape the data for analysis
- When combining multiple CSV files from the parking bay
- When preparing data for a specific report or chart format
