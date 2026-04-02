# Analysis Bay

**Purpose:** Extract insights and summarize your data.

This is where you answer questions about the data — what's the average, what's trending, what correlates with what, how is it distributed.

---

## What's in the notebook

- Summary statistics (overall and by group)
- Correlation matrix
- Group by summaries
- Value counts and frequency distributions
- Binning / bucketing numeric values
- Cross tabulation

---

## Reading a Correlation Matrix

Values range from -1 to 1:
- **1.0** — perfect positive correlation
- **0.0** — no correlation
- **-1.0** — perfect negative correlation

A value above **0.7** or below **-0.7** is generally considered a strong correlation worth investigating.

---

## Pandas 3.x Notes

`df.corr()` in pandas 3.x only works on numeric columns by default — string/StringDtype columns are automatically excluded. If you're getting unexpected results, check your column types first.

---

## When to use this bay

- After cleaning and transforming your data
- When you need to summarize data for a report or presentation
- When walking stakeholders through what the data shows
- When looking for relationships between variables before building a visualization
