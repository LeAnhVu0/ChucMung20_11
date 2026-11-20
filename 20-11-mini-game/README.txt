MINI-GAME 20/11 — HỘP QUÀ YÊU THƯƠNG
==================================

1. Chạy website
- Mở index.html bằng Chrome/Edge, hoặc chạy một web server tĩnh:
  python -m http.server 5500
- Truy cập: http://localhost:5500
- Triển khai lên Vercel / GitHub Pages / Netlify bằng cách upload index.html.

2. Cơ chế mini-game
- Giao diện người nhận chỉ hiển thị KHOẢNG giá trị "20K – 500K"; không liệt kê mệnh giá cụ thể.
- Không hiển thị tỷ lệ trúng hoặc giới hạn 50K/100K cho người nhận trước khi mở hộp.
- Có sáu hộp quà, người dùng tự chọn một hộp.
- Kết quả rút chỉ có 50.000đ hoặc 100.000đ; tỷ lệ 50/50.
- Chỉ chọn một lần trong cùng trình duyệt, dữ liệu lưu trong localStorage.
- Có animation mở hộp, pháo giấy, popup kết quả và xuất phiếu quà ra PNG.

3. Thay đổi thông tin
Mở index.html, tìm đoạn const CONFIG:
  receiver: "cô giáo của anh"
  sender: "anh"
  prizes: [50000, 100000]
  storageKey: "teacher-day-2026-love-gift-v1"

Lời chúc nằm trong phần HTML .hero-copy và hàm showResult() trong script.

4. Thử lại lượt quay trên trình duyệt dùng cho kiểm thử
Mở Developer Tools (F12) > Console, nhập:
  localStorage.removeItem('teacher-day-2026-love-gift-v1'); location.reload();
Hoặc thay storageKey để tạo lượt quay mới trên tất cả trình duyệt.

5. Lưu ý
- localStorage chỉ hạn chế một lượt quay trên một trình duyệt/thiết bị.
  Dùng trình duyệt khác, xoá dữ liệu, chế độ riêng tư hoặc sửa mã JS có thể quay lại.
  Muốn giới hạn thật sự trên nhiều thiết bị thì phải có backend xác thực.
- QUAN TRỌNG: Đây là web tĩnh. Người nhận có kiến thức kỹ thuật vẫn có thể xem JavaScript,
  đọc danh sách giải thưởng và sửa kết quả trong trình duyệt. Không có bí mật thực sự phía client.
  Nếu cần giấu hoàn toàn quy tắc ngẫu nhiên, phải xử lý quay thưởng ở backend / serverless function.
- Phiếu PNG là thiệp lưu niệm; không tự chuyển khoản.
- Không yêu cầu API, tài khoản hoặc thư viện bên ngoài.
- Hỗ trợ responsive 320px trở lên và giảm animation theo tùy chọn hệ điều hành.
