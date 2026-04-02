# Parking Bay

This is where you drop the CSV files you want to work on.

## How to use it

1. Copy or move your CSV file(s) into this folder
2. Open a bay notebook
3. In the config cell at the top, set `CSV_FILE` to your file name:

```python
CSV_FILE = "sales_data.csv"
```

4. Run the config cell — your data is loaded and ready

## Multiple files

You can have as many CSV files parked here as you need. This is especially useful if you're planning to merge or compare datasets in the Transformation bay.

## Note on git

CSV files in this folder are excluded from git by default (see `.gitignore`). Your data stays local and won't be accidentally committed to the repo.
