# Automall DSR Consolidation

!!! success "Built — Consolidates 14+ Monthly DSR Files"

---

## Overview

The Automall DSR Consolidation project is a Python-based Excel consolidation script (`consolidate_excel.py`) that automates the merging of monthly Daily Sales Report (DSR) files from the Automall operation. Developed using the Claude Code CLI, this script successfully consolidates 14 or more monthly DSR files into a unified dataset for analysis and reporting.

---

## Problem Statement

The Automall operation generates individual DSR files on a monthly basis, each containing sales, pricing, and inventory data. Prior to this automation, consolidating these files was a manual, error-prone process that consumed significant time and introduced inconsistencies. The volume of data — spanning 14+ months — made manual consolidation impractical for regular reporting cycles.

---

## Solution

The `consolidate_excel.py` script automates the entire consolidation process.

| Aspect | Detail |
|---|---|
| **Language** | Python |
| **Key Library** | openpyxl / pandas (Excel processing) |
| **Input** | 14+ monthly DSR Excel files |
| **Output** | Single consolidated Excel workbook |
| **Development Tool** | Claude Code CLI |

The script reads all DSR files from a specified directory, normalizes column headers and data formats, merges the data into a single DataFrame, and outputs a clean, consolidated Excel file ready for Power BI ingestion or manual analysis.

---

## Impact

This automation eliminates hours of manual data consolidation work each reporting cycle, reduces the risk of human error in data merging, and provides a consistent, repeatable process that can be executed on demand. The consolidated output feeds directly into Power BI-ready datasets used for leadership dashboards and strategic analysis.
