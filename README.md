[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112920&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600798
**Student Email:** quangdk2k4@gmail.com
**Name:** Tran Van Quang

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian bang Python va pandas. Pipeline doc du lieu san pham tu `raw_data.json`, kiem tra chat luong du lieu, loai bo record khong hop le, chuan hoa category, tinh gia sau khi giam 10%, them timestamp xu ly va luu ket qua ra `processed_data.csv`.

Lab cung co phan quan sat tac dong cua data quality len AI Agent thong qua viec so sanh ket qua khi Agent doc clean data va garbage data.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Sau khi chay thanh cong, file `processed_data.csv` se duoc tao trong thu muc project.

### Chay Agent Simulation (Stress Test)

```bash
python generate_garbage.py
python agent_simulation.py
```

Ket qua thi nghiem Clean Data vs Garbage Data duoc ghi trong `experiment_report.md`.

### Chay test local

```bash
pytest
```

---

## Cau truc thu muc

```text
solution.py              # ETL Pipeline script
raw_data.json            # Du lieu dau vao
processed_data.csv       # Output cua pipeline
generate_garbage.py      # Tao garbage_data.csv
agent_simulation.py      # Mo phong AI Agent doc du lieu
experiment_report.md     # Bao cao thi nghiem
README.md                # Huong dan va tom tat bai lam
```

---

## Ket qua

Pipeline xu ly 5 records tu `raw_data.json`. Sau validation, 3 records hop le duoc giu lai va 2 records bi loai do `price <= 0` hoac `category` rong. File output co them cac cot `discounted_price` va `processed_at`, dong thoi `category` duoc chuan hoa ve Title Case.
