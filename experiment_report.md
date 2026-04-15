# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** vitrannhat@gmail.com
**Name:** 2A202600497 - Trần Nhật Vĩ
**Date:** 4/15/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

#### Clean Data

- Agent chọn sản phẩm hợp lý
- Giá trị nằm trong khoảng bình thường
- Không bị ảnh hưởng bởi dữ liệu lỗi

#### Garbage Data

- Agent bị ảnh hưởng bởi outlier (giá cực lớn)
- Không phát hiện dữ liệu bất thường
- Quyết định không thực tế

#### Phân tích vấn đề
Các lỗi trong garbage data:

- Duplicate ID
- Sai kiểu dữ liệu ("ten dollars")
- Giá trị cực đoan (999999)
- Null values

Agent không có cơ chế:

- Kiểm tra outlier
- Validate kiểu dữ liệu
- Xử lý missing values

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

- Data Quality ảnh hưởng trực tiếp đến AI output
- Garbage data có thể dẫn đến quyết định sai nghiêm trọng
- ETL pipeline và validation là bắt buộc trước khi dùng AI

## Đề xuất cải thiện
- Thêm kiểm tra outlier (ví dụ: giá > ngưỡng hợp lý)
- Validate kiểu dữ liệu (price phải là số)
- Loại bỏ duplicate
- Xử lý missing values