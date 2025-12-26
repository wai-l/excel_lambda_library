# Excel LAMBDA Library

A personal library of reusable Excel **LAMBDA functions** for finance, time-series, and data shaping tasks.

This repository treats Excel formulas as **source code**:
- functions are stored as text
- versioned with Git
- documented and testable
- manually imported into Excel via Name Manager or bundled into a library workbook / add-in

## Structure

```text
excel-lambda-library/
├── README.md
├── lambdas/
│   ├── FIN_MONTHLY_REV_REC.txt
├── docs/
│   └── FIN_MONTHLY_REV_REC.md
└── tests/
    └── test_cases.csv
```

## Naming conventions

### Prefixes
- ```FIN_``` – finance & accounting logic
- ```DAT_``` – date / time-series / data shaping
- ```UTL_``` – generic utilities

### Output suffixes (where helpful)
- ```_SCALAR``` – single value
- ```_VEC``` – single row/column
- ```_TBL``` – 2D table

## How to use a function in Excel
1. Copy the formula from lambdas/<NAME>.lam.txt
2. Open Name Manager
3. Create a new name using the file name (without extension)
4. Paste the formula
5. Use it like a native Excel function

Example:
```excel
    =FIN_MONTHLY_REV_REC_TBL(A1, B1, C1)
```

## Function Index

### Finance
| Function | Returns | Description | Formula | Documentation |
|--------|--------|-------------|---------|----------------|
| FIN_MONTHLY_REV_REC_TBL | Table | Monthly revenue recognition from total contract value | [Link](lambdas/FIN_MONTHLY_REV_REC_TBL.txt)  | [Link](docs/FIN_MONTHLY_REV_REC_TBL.md) |