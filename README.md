# Data Cleaning Project

## 📁 project structure

(this week)
project/
├── data/                    # Raw CSV data
├── cleaned_data/            # Data after preliminary cleaning
├── config/
│   └── column_types_master.csv
├── reports/
│   ├── missing_values_report.csv
│   └── relation_integrity_report.csv
├── logs/
│   └── main.log             # Main program run log
└── scripts/
    ├── main.py
    ├── clean_missing.py
    ├── clean_format.py
    └── clean_relations.py

## 🧩 What the module does

### `clean_missing.py`
- Count the number of missing values per column in each CSV file
- Output: 'reports/missing_values_report.csv'

### `clean_format.py`
- Clean each column according to 'column_types_master.csv'
- Types supported: integer, real, date, timestamp, text
- Output: 'cleaned_data/'

### `clean_relations.py`
- Automatic identification of many-to-many relational tables
- Check if foreign key fields are missing or duplicated
- Output: 'reports/relation_integrity_report.csv'

### `main.py`
- Main program entry point
- All three modules are called sequentially
- Automatically log runs to 'logs/main.log'

---

## 🧩 Development plan for next week

### `clean_missing_strict.py`
- Goal: Automatically remove invalid records from a many-to-many relational table based on foreign key missing records flagged in relation_integrity_report.csv
- Requirements:
  - All records with missing values in key fields should be removed
  - The deleted records are written to logs/removed_rows/ audit logs
- Objective: To prepare a structurally complete data subset for subsequent deep analysis


## ✅ Start up

```bash
python scripts/main.py