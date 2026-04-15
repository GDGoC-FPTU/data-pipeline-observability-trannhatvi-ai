[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574343&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** vitrannhat@gmail.com
**Name:** Trần Nhật Vĩ

---

## Mo ta

Bài lab này xây dựng một ETL pipeline cơ bản gồm các bước:

- Extract dữ liệu từ file JSON
- Validate dữ liệu (loại bỏ dữ liệu lỗi)
- Transform dữ liệu (chuẩn hóa và tính toán)
- Load dữ liệu ra file CSV

Ngoài ra, bài lab còn thực hiện stress test để so sánh hành vi của agent khi xử lý dữ liệu sạch và dữ liệu bị nhiễu (garbage data).

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mo ta cach ban chay thi nghiem Clean vs Garbage data
Testing with CLEAN data:
Agent: Based on my data, the best choice is Laptop at $1200.

Testing with GARBAGE data:
Agent: Based on my data, the best choice is Nuclear Reactor at $999999.
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Pipeline chạy thành công, không lỗi
- Dữ liệu không hợp lệ (price <= 0 hoặc category rỗng) đã bị loại bỏ
- File processed_data.csv được tạo
- Dữ liệu đã được chuẩn hóa và thêm timestamp
