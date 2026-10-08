# Landing Page Thu Thập Email Khách Hàng - Du Lịch Hội An (2026)

Dự án Landing Page thu thập Lead (Email & Số điện thoại) chuyên biệt cho ngành Du lịch, được xây dựng dựa trên cấu trúc và thông tin cẩm nang du lịch Hội An từ bài viết của **Vinpearl**: [Kinh nghiệm du lịch Hội An trọn bộ](https://vinpearl.com/vi/kinh-nghiem-du-lich-hoi-an-tron-bo-thoi-gian-di-lai-an-o-vui-choi).

---

## 🌟 Điểm Nổi Bật Của Trang Landing Page

1. **Lead Magnet cuốn hút (Hook chuyển đổi cao)**:
   - Tặng Ebook PDF 35 trang: "Cẩm nang du lịch Hội An tự túc từ A - Z".
   - Tặng kèm Bản đồ số Google Maps ghim sẵn 50+ quán ăn & toạ độ check-in ít người biết.
   - Lịch trình mẫu chi tiết 3N2Đ và 2N1Đ chuẩn chi phí.
   - Tặng mã E-Voucher giảm 30% vé VinWonders Nam Hội An, thuyền sông Hoài, show Ký ức Hội An.

2. **Thiết kế UI/UX đậm chất Hội An**:
   - Tone màu nhận diện đặc trưng: Vàng hoa cúc cổ kính, đỏ đèn lồng, nâu gỗ và xanh sông Hoài.
   - Font chữ nghệ thuật: *Playfair Display* & *Plus Jakarta Sans*.
   - Chuẩn Responsive 100% trên cả Điện thoại (Mobile), Máy tính bảng (Tablet) và Máy tính để bàn (Desktop).

3. **Cơ chế thu thập dữ liệu (Email Capture)**:
   - **Hero Form** nổi bật ngay khi vừa vào trang.
   - **Quick Modal Form** bật lên khi khách hàng click các nút CTA giữa trang.
   - **Sticky Bottom Bar** tự động xuất hiện khi cuộn trang, nhắc nhở khách hàng tải tài liệu.
   - **Footer Form** thu email ở cuối bài viết.

4. **Tích hợp sẵn Mini Admin Leads Manager**:
   - Lưu trữ tự động toàn bộ email, tên, số điện thoại, thời gian dự kiến đi vào `localStorage`.
   - Xem trực tiếp danh sách leads ngay trên trang bằng nút **"Quản Lý Leads (Admin)"** ở góc footer.
   - **Xuất file Excel/CSV** chỉ với 1 click (đã cấu hình UTF-8 BOM chuẩn để mở bằng Microsoft Excel không bị lỗi tiếng Việt).

---

## 🚀 Hướng Dẫn Xem & Chạy Landing Page

1. **Cách nhanh nhất**:
   - Mở thư mục `c:\Users\Admin\Downloads\Dư án 1`
   - Nhấp đúp chuột vào file `index.html` để mở trực tiếp trên Chrome, Edge hoặc bất kỳ trình duyệt nào.

2. **Mở qua Local Server (nếu muốn)**:
   ```powershell
   # Trong thư mục dự án:
   python -m http.server 8080
   ```
   Sau đó truy cập: `http://localhost:8080` trên trình duyệt.

---

## 🔌 Hướng Dẫn Kết Nối Với Các Nền Tảng Email Marketing / Google Sheets

Mặc định trang đang lưu lead vào trình duyệt của bạn và cho phép xuất file Excel/CSV. Khi bạn muốn tích hợp tự động đẩy data về hệ thống:

### 1. Kết nối Google Sheets (Miễn phí & Dễ nhất)
Bạn có thể dùng dịch vụ **Google Apps Script Webhook** hoặc **SheetDB / Make.com / Zapier**:
Trong hàm `handleLeadSubmit()` của file [index.html](file:///c:/Users/Admin/Downloads/D%C6%B0%20%C3%A1n%201/index.html):
```javascript
fetch("YOUR_GOOGLE_SHEETS_WEBHOOK_URL", {
  method: "POST",
  body: JSON.stringify(newLead),
  headers: { "Content-Type": "application/json" }
});
```

### 2. Kết nối Mailchimp / Brevo / GetResponse
Thay thẻ `<form id="heroEmailForm">` bằng action form được cấp từ tài khoản Mailchimp/Brevo của bạn, hoặc dùng webhook API.

### 3. Kết nối Formspree (Nhận email thông báo ngay khi có khách đăng ký)
Đổi thuộc tính form thành:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```
