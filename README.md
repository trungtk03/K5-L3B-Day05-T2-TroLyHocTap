# K5-L3B-Day05-T2-TroLyHocTap

> **LAB5 — Thiết kế sản phẩm AI cho lúc nó sai · AI20K K5 · Ngày 5**  
> **Track T2: Giáo dục — Trợ lý học bài tối muộn, khi không còn ai để hỏi**

## Thông tin nhóm
- **Lớp:** L3B
- **Bàn / Zone:** G
- **Track:** T2 — Giáo dục
- **Tên nhóm:** TroLyHocTap
- **Repo URL:** `https://github.com/trungtk03/K5-L3B-Day05-T2-TroLyHocTap`

### Danh sách thành viên

| Họ và Tên | Mã Học Viên | Vai trò & Việc đã làm |
|---|---|---|
| **Nguyễn Hoàng Trung** *(Trưởng nhóm)* | **2A202603826** | - Khởi tạo repository và quản trị cấu trúc bài nộp.<br>- Thiết kế ma trận phân quyền và mức tự chủ cho 4 tool theo cost-of-error (§4).<br>- Lập trình hoàn thiện prototype HTML/JS tương tác và Dashboard TA/Giảng viên (§5).<br>- Tích hợp mô-đun gọi Gemini API thật.<br>- Phụ trách trình bày mức tự chủ và demo trước lớp. |
| **Nguyễn Tuấn Dũng** | **2A202603859** | - Xây dựng ma trận 9 kịch bản rủi ro phủ 4 lớp và phân tích chuyên sâu 2 kịch bản đắt nhất theo Ma trận 4 chiều Cost-of-error (§2).<br>- Thiết kế chi tiết trải nghiệm khi AI sai cho 2 kịch bản đắt nhất, xây dựng Khung phân loại lỗi tổng quát và ánh xạ toàn diện nguyên tắc Microsoft HAX / Google PAIR (§3).<br>- Thiết lập hệ thống 3 tiêu chí Pass/Fail định lượng đo lường được, bộ kiểm thử Test Suite và kế hoạch giảm thiểu rủi ro còn lại (§6).<br>- Soạn kịch bản Demo 4 phút, lời thoại thuyết trình mở đầu và danh mục 5 phương án ứng phó ca lạ phản biện trước Hội đồng (§7).<br>- Phụ trách trình bày lát cắt bài toán, UX khi AI sai và bảo vệ rào chắn liêm chính học thuật. |

---

## Cấu trúc Repository

```
K5-L3B-Day05-T2-TroLyHocTap/
├── spec.md                # Bản đặc tả chi tiết toàn diện từ §1 đến §7 (theo mẫu 03-spec-template.md)
├── README.md              # Giới thiệu nhóm và hướng dẫn điều hướng
└── prototype/             # Ứng dụng Prototype tương tác trực quan
    ├── index.html         # Prototype hoàn chỉnh (Giao diện học viên + Dashboard TA/Giảng viên + Kết nối AI)
    └── README.md          # Hướng dẫn sử dụng và giải thích các vị trí đánh số HAX/PAIR [1]..[6]
```

---

## Điểm nhấn nổi bật của bài nộp

1. **Phân tích chiều sâu Cost-of-error trong Giáo dục:**
   - Xác định rõ cái giá khi sai trong giáo dục: *"Rẻ mỗi lần nhưng âm thầm và diện rộng — học viên học sai mà không biết, và không ai báo"*.
   - Khóa chặt tool `dang_FAQ` ở mức **CẤM AI tự đăng** để ngăn chặn thảm họa phát tán kiến thức sai lệch hoặc lộ đáp án cho cả lớp (bẫy phản ví dụ toán học trong §3.3).
   - Thiết lập rào chắn liêm chính học thuật (Academic Integrity Guardrail) cho tool `goi_y_bai_tap`, ngăn chặn mớm đáp số bài tập 3 đang mở.
2. **Tuân thủ khung pháp lý & tiêu chuẩn quốc tế:**
   - Tuân thủ nghiêm ngặt **Điều 11 Luật Trí tuệ nhân tạo số 134/2025/QH15** về nghĩa vụ minh bạch danh tính AI khi tương tác trực tiếp với người dùng.
   - Áp dụng triệt để các nguyên tắc thiết kế **Microsoft HAX (G1, G2, G8, G9, G10, G11, G15)** và **Google PAIR (Explainability, Calibrated Trust, Graceful Failure)**.
3. **Prototype tương tác đạt chuẩn Bonus (+8 điểm):**
   - **Bấm qua mượt mà cả 4 kịch bản:** KB1 (Lỗi §3.3), KB2 (Bài 3 đang mở sát giờ), KB3 (Phân biệt trung bình/trung vị), Ca lạ (Slide 12 / Buổi 7).
   - **Gạt chuyển 3 mức tự chủ trực tiếp:** Thụ động vs Cân bằng (Mức chọn) vs Quá tay.
   - **Đạt Bonus Track T2:** Tích hợp giao diện **Dashboard quản trị dành cho TA & Giảng viên** để duyệt FAQ và xử lý vé hỏi đáp đêm muộn.
   - **Đạt Bonus Gọi AI Thật:** Tích hợp sẵn kết nối Google Gemini API với ô nhập key an toàn lưu sessionStorage.
