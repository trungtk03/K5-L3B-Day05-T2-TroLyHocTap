# Prototype Hướng Dẫn & Tài Liệu — Track T2 Giáo Dục

## 1. Giới thiệu tổng quan
Prototype này mô phỏng tính năng **Trợ lý học bài tối muộn (Study Mode)** tích hợp vào trang khoá học LMS ("Nhập môn phân tích dữ liệu" - Buổi 3: Thống kê mô tả).

- **Lớp:** L3B · **Track:** T2 Giáo dục
- **Nhóm:** TroLyHocTap
- **Thành viên:**
  - Nguyễn Hoàng Trung (MSSV: 2A202603826)
  - Nguyễn Tuấn Dũng (MSSV: 2A202603859)

## 2. Cách mở và trải nghiệm Prototype
1. Nhấp đúp mở trực tiếp file `index.html` trong thư mục này bằng bất kỳ trình duyệt hiện đại nào (Chrome, Edge, Firefox, Safari).
2. **Không cần cài đặt backend hay npm**: File HTML hoàn toàn khép kín (self-contained), tích hợp toàn bộ HTML, CSS và logic JavaScript.
3. Hoạt động offline 100% với bộ giả lập suy luận chuẩn mực cho cả 4 kịch bản.

## 3. Các tính năng cốt lõi trên Prototype

### 3.1 Bảng chuyển đổi kịch bản kiểm thử (Scenario Switcher)
- **KB1: Lỗi tài liệu §3.3 (Đắt nhất #1):**
  - Học viên phát hiện tài liệu ghi *"Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai"* nhưng chỉ ra phản ví dụ phương sai = 0.25 thì căn bậc hai là 0.5 > 0.25.
  - Prototype thể hiện AI ghi nhận sự sắc bén của học viên, giải thích rõ câu chỉ đúng khi phương sai > 1, cung cấp nút **Báo lỗi cho Giảng viên**, và **CHẶN TUYỆT ĐỐI việc tự đăng lên FAQ cả lớp**.
- **KB2: Xin đáp án Bài 3 sát giờ nộp (Đắt nhất #2):**
  - Học viên hỏi lúc 23:35 (sát hạn 23:59 ngày 13/11) xin đáp số 3a và kết luận câu 3b.
  - Prototype thể hiện AI từ chối mớm đáp án, hiển thị rào chắn liêm chính học thuật, hướng dẫn phương pháp Socratic trích từ §3.1, §3.2, §3.4.
  - Đồng thời cảnh báo rõ ràng khung giờ TA trực (08:00–22:00) và bật modal xác nhận hẹn 08:00 sáng mai nếu học viên muốn gửi vé.
- **KB3: Phân biệt Trung bình và Trung vị:**
  - Ca chuẩn mực giải thích so sánh giữa §3.1 và §3.2.
- **Ca lạ: Hỏi Slide 12 / p-value Buổi 7:**
  - Xử lý câu hỏi về nguồn không tồn tại (tài liệu không có slide) và câu hỏi về buổi chưa học (Buổi 7).

### 3.2 Bảng chuyển đổi 3 Mức tự chủ
Cho phép giảng viên và TA gạt công tắc để xem trực tiếp sự khác biệt giữa:
- **Mức ① Thụ động:** AI chỉ trích xuất tài liệu khô khan, học viên tự bơi.
- **Mức ② Cân bằng (Mức nhóm TroLyHocTap lựa chọn):**
  - `tra_cuu_tai_lieu`: Tự làm (chỉ đọc).
  - `goi_y_bai_tap`: Tự làm có rào chắn (gợi ý phương pháp Socratic, cấm xuất đáp án bài đang mở).
  - `chuyen_TA`: Cần học viên duyệt (cảnh báo ngoài giờ trực).
  - `dang_FAQ`: CẤM AI tự đăng (chỉ tạo bản nháp chờ Giảng viên duyệt).
- **Mức ③ Tự động hóa quá tay (Nguy hiểm):**
  - AI tự tiện giải hộ bài tập và tự đăng câu sai lên FAQ cả lớp.

### 3.3 Dashboard dành cho Giảng viên & TA (Bonus Track 2)
Bấm nút **"👨‍🏫 Dashboard TA / Giảng viên (Bonus)"** ở góc trên bên phải để chuyển sang màn hình quản trị:
- **Hàng chờ câu hỏi chuyển TA đêm muộn:** Hiển thị danh sách vé do học viên gửi lúc nửa đêm kèm nhãn hẹn giờ giải quyết sau 08:00 sáng mai.
- **Hàng chờ duyệt xuất bản FAQ:** Hiển thị bản thảo FAQ do AI gợi ý; Giảng viên có quyền bấm **"Duyệt xuất bản"** hoặc **"Hủy bỏ"**.

### 3.4 Kết nối AI Thật (Gemini API - Bonus)
Bấm nút **"⚙️ Gọi AI Thật (Gemini)"** trên thanh điều hướng để nhập Google Gemini API Key. Key được lưu tạm trong `sessionStorage` và gọi trực tiếp endpoint `gemini-1.5-flash`, kèm system prompt tuân thủ nghiêm ngặt Điều 11 Luật AI 134/2025/QH15 và rào chắn liêm chính học thuật.

## 4. Bảng ánh xạ các vị trí đánh số HAX / PAIR trên màn hình

| Số | Vị trí trên màn hình | Nguyên tắc HAX / PAIR | Ý nghĩa thiết kế |
|---|---|---|---|
| **[1]** | Huy hiệu AI & Trạng thái thẩm quyền | **HAX G1 / G2** | Minh bạch danh tính máy tính theo Luật AI 134/2025/QH15; giới hạn rõ quyền hạn sư phạm. |
| **[2]** | Khối Căn cứ trích dẫn (Evidence Block) | **HAX G11 + PAIR Explainability** | Trích dẫn đích danh mục §3.1, §3.2, §3.3 để học viên tự kiểm chứng, tránh tin tưởng mù quáng. |
| **[3]** | Khung gợi ý phương pháp Socratic | **HAX G10** (Thu hẹp nghi ngờ) | Chuyển câu hỏi đòi đáp án thành câu hỏi tư duy logic; không mớm kết quả bài đang mở. |
| **[4]** | Khung cảnh báo ngoài giờ trực TA | **PAIR Errors + Graceful Failure** | Báo rõ TA kết thúc trực lúc 22:00, tránh ru ngủ học viên thức đợi vô ích. |
| **[5]** | Nút bấm xác nhận & Modal gửi vé | **HAX G8 / G9 + PAIR User Control** | Học viên có quyền kiểm soát và gạt bỏ; ngăn ngừa gửi vé nhầm. |
| **[6]** | Hàng chờ duyệt FAQ trên Dashboard | **Bonus Track 2** | Giữ vững hàng rào kiểm soát tri thức; AI không bao giờ được tự tiện phát ngôn trước toàn khóa. |
