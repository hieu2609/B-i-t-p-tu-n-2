# Nhật ký sửa lỗi

- **Bộ chấm (`runner_w02.py`, `autograde_w02.py`)**: tiến trình con crash `UnicodeEncodeError` trên Windows (cp1252) khi bài làm in chữ có dấu, làm TODO bị chấm lỗi (kể cả BMI). Nay JSON ASCII-safe và ép `-X utf8`.
- **`practice/checks/check_practice.py`**: ép UTF-8 khi chạy bài luyện.
- **`exercises/ex02` TODO 4 (BMI)**: nhận `1,75` (dấu phẩy), `175` (cm → m), báo lỗi khi chiều cao/cân nặng ≤ 0 thay vì `ZeroDivisionError`.
- **`exercises/ex03`, `solutions/ex03`**: số thực nhập bằng dấu phẩy không còn `ValueError`.
- **`html/week02-journey.html`**: ô số dùng `inputmode="decimal"`, nhận dấu phẩy; BMI tự đổi cm → m; mẫu Python trong Playground cũng nhận dấu phẩy.
- **`html/week02-journey.html` (điểm cứng 10.0)**: vòng điểm hero + badge Practice + phiếu minh chứng từng hardcode `10.0 / Xuất sắc / 3/3 PASS`, nên xóa code rồi chấm lại vẫn thấy điểm cũ. Đã sửa:
  - Hero bắt đầu ở trạng thái **Chưa chấm** (`— / 10`, `--p:0`).
  - Mỗi lần bấm **🎯 Chấm điểm** cập nhật hero theo điểm thật từ Pyodide.
  - Ô code trống → reset hero + phiếu chấm (không giữ điểm lần trước).
  - Nút **Xóa lịch sử** cũng reset UI + `localStorage` (`w02_grade_history`).
  - Phiếu minh chứng lấy điểm từ lần chấm Live IDE gần nhất, không ghi sẵn 10/10.
- **`html/week02-journey.html` (hộp thoại input)**: thay `window.prompt` ("This page says") bằng modal tùy chỉnh khớp giao diện Studio. Khi chọn chế độ hỏi từng dòng, mỗi `input("…")` hiện hộp thoại (ví dụ *Nhập chiều cao (m):*), OK/Enter xác nhận, Cancel = EOFError. Áp dụng cho cả **Chạy** và **Chấm điểm**.
