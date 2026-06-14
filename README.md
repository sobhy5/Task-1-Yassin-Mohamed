# Project 1: Data Cleaning & Preparation
**DecodeLabs Industrial Training | Batch 2026**

## Overview
This project demonstrates data cleaning and preparation on a raw cafe sales dataset. The goal is to transform messy, unreliable data into a production-ready "gold standard" dataset.

## Dataset
- **Source**: Cafe Sales — Dirty Data (synthetic, Kaggle-style)
- **Raw records**: 315 rows × 8 columns
- **Clean records**: 300 rows × 8 columns
- **Columns**: Transaction_ID, Date, Item, Category, Quantity, Price_Per_Unit, Total_Spent, Payment_Method

## Files
| File | Description |
|------|-------------|
| `cafe_sales_DIRTY.csv` | Raw dataset with all injected issues |
| `cafe_sales_CLEAN.csv` | Final cleaned dataset |
| `cleaning_notebook.ipynb` | Step-by-step Jupyter notebook |
| `change_log.pdf` | PDF change log documenting every fix |

## Issues Found & Fixed
| Issue | Count | Method |
|-------|-------|--------|
| Duplicate rows | 10 | drop_duplicates() |
| Bad date formats (DD/MM/YYYY) | 20 | Standardized to ISO 8601 |
| Missing Quantity values | 16 | Median imputation |
| Negative Quantity values | 5 | Replaced with median |
| Price outliers (>$50) | 3 | Capped → per-item median |
| Missing Payment_Method | 20 | Mode imputation |
| Inconsistent Item casing | 23 variants | strip().title() |
| NULL string Category values | 5 | Item-Category lookup |

## How to Run
1. Upload `cafe_sales_DIRTY.csv` to Colab Files panel
2. Open `cleaning_notebook.ipynb` in Google Colab
3. Run All Cells

## Tools
- Python 3
- pandas
- numpy

## Verification (0% Error Gate)
- Duplicate rows: **0** ✓
- Missing values: **0** ✓
- Negative quantities: **0** ✓
- Bad date formats: **0** ✓
