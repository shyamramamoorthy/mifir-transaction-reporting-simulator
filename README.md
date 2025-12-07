# MiFIR RTS 22 Transaction Reporting Simulator

*A hands-on learning and demonstration project for regulatory change & operations-focused PM roles.*

This project simulates the end-to-end **MiFIR RTS 22 Transaction Reporting process**, following the same structure a bank uses when delivering a regulatory change project.

It demonstrates:

* Regulatory interpretation
* Field mapping & data modelling
* Validation rule design
* Exception handling
* Manual reporting logic
* Version control & documentation

I built this to deepen my domain knowledge and to create a real, tangible example of my ability to deliver regulatory & operational data projects.

---

## 1. Background – What is RTS 22?

MiFIR **Regulatory Technical Standards (RTS) 22** define how investment firms must report **transactions in financial instruments** to their regulator. Reports must follow strict rules on:

* Instrument identifiers (ISINs)
* Quantities & prices
* Buyer/seller data
* Timestamps
* Execution venue
* LEIs and reference data quality

Approved Reporting Mechanisms (ARMs) apply validation checks and reject incorrect reports.

This project recreates a simplified version of that reporting logic for learning & demonstration.

---

## 2. What this simulator does

Given a set of **sample trades**, the simulator walks through the same lifecycle as a real bank:

### ✔ Step 1 — Map trade data to RTS 22 fields

Using a custom mapping sheet (`mapping_rts22.csv`).

### ✔ Step 2 — Apply validation rules

Using a simple “ARM-style” rules engine (`validation_rules.csv`).

### ✔ Step 3 — Produce two outputs

* `rts22_report_generated.csv` — valid RTS22 records
* `rejects_generated.csv` — failed records with error codes

The project currently contains manual outputs (golden copies) produced during early phases.

---

## 3. Repository structure

```
data/          # Sample trades (CSV/XLSX)
mapping/       # RTS 22 field mapping logic
validation/    # Validation rules (required fields, min values, etc.)
output/        # Manual report + reject files (used as golden source)
src/           # (Phase 9+) Python simulator code
tests/         # (Phase 11+) Automated test cases
docs/          # (Phase 12+) Design and functional documentation
```

---

## 4. Delivery Phases

This project mirrors how a real bank manages a regulatory reporting initiative.

1. **Phase 1** – Create folder structure & sample trade spreadsheet
2. **Phase 2** – Build RTS 22 field-mapping sheet
3. **Phase 3** – Build validation logic sheet
4. **Phase 4** – Manually produce RTS 22 transaction report
5. **Phase 5** – Manually produce “rejects” file
6. **Phase 6** – Convert Excel tabs into CSVs
7. **Phase 7** – Create GitHub repository
8. **Phase 8** – Documentation & narrative (current phase)
9. **Phase 9+** – Add Python code to automate mapping & validation

This phased breakdown reflects real-world regulatory project methodology.

---

## 5. Skills Demonstrated

* **Regulatory change delivery** (MiFIR RTS 22 reporting)
* Data lineage & field-level mapping
* Controls / validation rule design
* Exception & rejection handling
* Process modelling & operational readiness
* Documentation (functional specs, mapping, rules, outputs)
* Version control (Git, GitHub)
* Building a simplified reporting engine (Python, CSV)

This project is intended as a learning tool and as a portfolio piece for interviews.

---

## 6. How to run the simulator (coming in Phase 10)

Once coding phases are complete, the simulator will run via:

```
pip install -r requirements.txt
python -m mifir_simulator.pipeline
```

---

## 7. Future Enhancements

* Add more RTS 22 fields & richer validation rules
* Add reconciliation logic
* Add LEI validation against GLEIF
* Add dashboard visualisation
* Extend to EMIR or SFTR to demonstrate multi-reg framework skills
* Add unit tests comparing generated vs manual outputs

---

## 8. Skills Demonstrated (Detailed)

### 🔹 Regulatory & Compliance Understanding

* Interpreting MiFIR RTS 22 requirements
* Translating regulatory text into data and reporting logic
* Understanding ARM validation behaviour and reject scenarios
* Designing reporting processes aligned with control expectations

### 🔹 Data, Mapping & Controls

* Building field-level mappings (input → RTS22 output)
* Designing rule-based and hard-coded transformations
* Documenting data lineage and dependencies
* Creating validation logic for completeness, accuracy & consistency

### 🔹 Operational Process Modelling

* Designing exception handling and reject management
* Creating golden-source outputs for testing
* Thinking through BAU workflows and control frameworks

### 🔹 Delivery & Documentation

* Structuring the work into phases that mirror real regulatory programmes
* Writing functional specifications and phased delivery plans
* Maintaining clear documentation (README, spec, mapping, rules)
* Using Git/GitHub for version control and project transparency

### 🔹 Technical Competency (Light but Valuable for PMs)

* Working with CSV/XLSX data
* Using Python (planned in Phase 9+) to simulate reporting logic
* Designing a modular pipeline architecture (mapping → validation → output)
* Creating automated tests to compare generated outputs to manual ones

This project demonstrates my ability to lead **data-heavy, regulation-driven, multi-phase** initiatives in a banking environment.

