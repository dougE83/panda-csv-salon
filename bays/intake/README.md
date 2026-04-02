# Intake Bay

**Purpose:** Get a first look at your data before doing anything to it.

A quick intake run catches surprises early — wrong dtypes, unexpected nulls, more rows than expected. Always start here.

---

## What's in the notebook

- File shape (rows × columns)
- Column names and data types
- First and last rows
- Summary statistics
- Random sample
- Pandas 3.x `read_csv()` defaults explained

---

## Pandas 3.x — What Changed in `read_csv()`

| Behavior | Pandas 2.x | Pandas 3.x |
|---|---|---|
| String column dtype | `object` | `StringDtype` (Arrow-backed) |
| Copy-on-Write | Off | **On** |

### What this means in practice

**String dtype change:** When you load a CSV with text columns, those columns are now `StringDtype` instead of `object`. Code that checks `df[col].dtype == 'object'` to detect strings will no longer work. Use `pd.api.types.is_string_dtype(df[col])` instead.

**Copy-on-Write:** Modifying a slice of a DataFrame no longer modifies the original. This is the correct behavior — but if you have old code that relied on the old behavior, it will silently stop working. Always assign back to a variable:

```python
# Old pattern (broken in 3.x)
df[df['status'] == 'active']['value'] = 0

# Correct pattern
df.loc[df['status'] == 'active', 'value'] = 0
```

---

## When to use this bay

- Starting work on a new dataset
- Handing off work to someone else and want to show them the raw data
- Walking non-technical stakeholders through what the data looks like before any changes
