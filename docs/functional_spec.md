# RTS 22 Transaction Reporting Simulator

### Functional Specification (Simplified for Learning & Demonstration)

---

## 1. Objective

The purpose of this simulator is to recreate a simplified version of the **MiFIR RTS 22 transaction reporting workflow**.
It demonstrates how trade data is:

1. mapped to RTS 22 reportable fields,
2. validated using ARM-style business rules, and
3. separated into **valid reports** and **rejects**.

This functional spec describes the scope, logic, and outputs of the simulator.

---

## 2. Scope

### **In Scope**

* A simplified RTS 22 dataset (selected mandatory fields only)
* Sample trade data in CSV/XLSX
* Field-level mapping (input → RTS22 output)
* Basic validation rules:

  * required fields
  * minimum values
  * basic formatting
* Error handling and reject file creation
* Manual outputs (“golden source”) for testing
* Future automated Python pipeline

### **Out of Scope**

* Full RTS 22 reporting schema (all 65+ fields)
* Connectivity to an ARM (e.g., UnaVista)
* Real regulatory submission
* Intraday lifecycle event handling
* Complex business logic for derivatives or multi-leg instruments

---

## 3. Inputs

| File                   | Description                           |
| ---------------------- | ------------------------------------- |
| `sample_trades.*`      | Raw trade data (input dataset)        |
| `mapping_rts22.csv`    | Field mapping definitions             |
| `validation_rules.csv` | Simplified ARM-style validation rules |

---

## 4. Processing Workflow

### **Step 1 – Load Trade Data**

The simulator ingests a small set of sample trades in CSV/XLSX format.

### **Step 2 – Apply RTS 22 Mapping**

Each RTS 22 target field is populated using:

* a direct mapping (`source_column`)
* a rule-based value (`RULE:`)
* or a hard-coded value (`HARD-CODE`)

The result is a preliminary RTS 22-style report.

### **Step 3 – Apply Validation Rules**

Validation rules include:

* **Required field** check
* **Minimum value** check (e.g., quantity > 0)
* **Basic consistency** checks

If a rule fails:

* the row is excluded from the valid report
* an entry is added to the rejects file with `error_code` + `error_message`

### **Step 4 – Generate Outputs**

Two output files are produced:

1. **RTS 22 Report** (successful rows)
2. **Reject File** (failed rows with validation errors)

Manual "golden copy" outputs (`rts22_report_manual.csv`, `rejects_manual.csv`) are included for comparison.

---

## 5. Outputs

| File                         | Description                           |
| ---------------------------- | ------------------------------------- |
| `rts22_report_generated.csv` | Clean RTS 22 report after validations |
| `rejects_generated.csv`      | Rejects with error codes and messages |
| Manual output CSVs           | Used for testing & reference          |

---

## 6. Future Enhancements

* Add more RTS 22 fields
* Add more complex rule types (timestamp comparisons, LEI checks, venue determination)
* Introduce data lineage diagrams
* Build an automated test suite
* Add a visual dashboard for reporting quality metrics
* Extend simulator to EMIR and SFTR

---

This functional specification supports the structure of the project and describes the expected behaviour of the reporting simulator.
