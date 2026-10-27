# ♟️ BÀI THI KẾT THÚC MÔN - NHÓM 12
## ĐỀ TÀI: SAFE SQUARES NOT THREATENED BY BISHOPS
*(Tính các ô an toàn không bị khống chế bởi quân Tượng)*

---

## 📌 1. Giới thiệu chung
Đây là dự án ứng dụng mô phỏng và tính toán số ô an toàn trên bàn cờ kích thước $N \times N$ khi đặt các quân Tượng (Bishops) vào các vị trí bất kỳ. 

Chương trình cung cấp giao diện đồ họa (GUI) trực quan giúp người dùng dễ dàng nhập dữ liệu, tính toán số ô không bị đe dọa và trực quan hóa toàn bộ bàn cờ cùng phạm vi khống chế của quân Tượng.

---

## 👥 2. Thông tin Nhóm thực hiện
* **Nhóm thực hiện:** Nhóm 12
* **Bài thi:** Kết thúc môn học
* **Các thành phần chính trong dự án:**
  * `Bai_thi.py`: Giao diện ứng dụng hoàn chỉnh (CustomTkinter + PIL).
  * `Thuật toán.py`: Thuật toán cốt lõi xử lý tính toán các đường chéo và ô an toàn.
  * `background_app.jpg`: Hình nền giao diện.
  * `icon_app.ico`: Biểu tượng ứng dụng.

---

## ✨ 3. Tính năng chính
- **Giao diện người dùng (GUI):** Xây dựng bằng `customtkinter`, đẹp mắt và dễ tương tác.
- **Tính toán tối ưu:** Sử dụng tập hợp (`set`) lưu trữ đường chéo $r - c$ và $r + c$ để kiểm tra ô bị đe dọa với độ phức tạp tối ưu.
- **Trực quan hóa bàn cờ:** 
  - Hiển thị trực tiếp bàn cờ $N \times N$.
  - Phân biệt rõ các trạng thái: Ô an toàn (Safe), Ô bị đe dọa (Danger) và Vị trí quân Tượng (Bishop).
  - Hỗ trợ xem bàn cờ kích thước từ nhỏ đến lớn (lên tới $N \le 150$).
- **Xử lý linh hoạt dữ liệu đầu vào:** Cho phép nhập tọa độ theo nhiều định dạng và tự động trích xuất cặp tọa độ $(Row, Column)$.

---

## 🛠️ 4. Yêu cầu hệ thống & Cài đặt

### Yêu cầu:
- Python 3.8 trở lên

### Cài đặt các thư viện phụ thuộc:
Chạy lệnh sau trong terminal/command prompt để cài đặt các thư viện cần thiết:

```bash
pip install customtkinter pillow
```

---

## 🚀 5. Hướng dẫn sử dụng

### 🔹 Cách 1: Chạy ứng dụng Giao diện (GUI)
Chạy tệp `Bai_thi.py` để mở ứng dụng giao diện:
```bash
python Bai_thi.py
```
1. Tại màn hình chính, nhấn **START**.
2. Nhập kích thước bàn cờ $N$.
3. Nhập danh sách tọa độ các quân Tượng (Ví dụ: `2 3 4 5` ứng với 2 quân Tượng ở ô $(2,3)$ và $(4,5)$).
4. Nhấn **CALCULATE & DRAW** để xem kết quả và trực quan hóa bàn cờ.

### 🔹 Cách 2: Chạy phiên bản Console/Command Line
Chạy tệp `Thuật toán.py` nếu chỉ muốn tính toán nhanh qua dòng lệnh:
```bash
python "Thuật toán.py"
```

---

## 🧮 6. Giải thuật xử lý (Core Logic)
Một quân Tượng tại vị trí $(r, c)$ sẽ đe dọa tất cả các ô $(i, j)$ thỏa mãn một trong hai điều kiện đường chéo:
1. **Đường chéo chính:** $r - c = i - j$
2. **Đường chéo phụ:** $r + c = i + j$

Thuật toán duyệt qua toàn bộ bàn cờ $N \times N$ và kiểm tra xem vị trí $(i, j)$ có nằm trên đường chéo bị khống chế hay không để xác định ô an toàn.