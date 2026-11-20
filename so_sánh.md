## BẢNG SO SÁNH TRADE-OFF GIỮA 2 GIẢI PHÁP

| Tiêu chí | Giải pháp 1 (Đơn giản) | Giải pháp 2 (Chi tiết) |
| :--- | :--- | :--- |
| **Độ dễ hiểu** | Cao (Ngắn gọn, dễ đọc, dễ viết nhanh) | Trung bình (Dài, cấu trúc nhiều tầng) |
| **Tốn token** | Ít (~80–100 tokens/lượt gọi) | Nhiều hơn (~300–350 tokens/lượt gọi) |
| **Chặn lỗi biên** | Trung bình (Dễ bị AI tự suy diễn khi thiếu dữ liệu hoặc bị học viên lừa chấm 10 điểm) | Cực tốt (Bắt được lỗi bài trống, lạc đề và chống Prompt Injection) |
| **Tính nhất quán (Output)** | Thấp (Mỗi lần chạy AI có thể trả về một kiểu trình bày khác nhau) | Rất cao (Cố định bảng biểu và các đề mục rõ ràng) |
| **Khả năng tích hợp hệ thống** | Kém (Khó bóc tách dữ liệu tự động qua API) | Tốt (Dễ dàng parse dữ liệu vào LMS/Database) |


## BƯỚC 3: LỰA CHỌN PHƯƠNG ÁN & CHẠY THỬ NGHIỆM

### 1. Lựa chọn phương án tối ưu và lý do
* **Phương án được chọn:** **Giải pháp 2 (Chi tiết, có nhiều ràng buộc)**.
* **Lý do đánh đổi (Trade-off):**
  1. **Đặc thù nghiệp vụ giáo dục đòi hỏi độ chính xác cao:** Trong quy trình chấm bài tự động, việc tiết kiệm vài trăm token ở Giải pháp 1 không bù đắp được rủi ro chấm sai điểm, AI tự bịa kiến thức (hallucination) hoặc bị học viên qua mặt bằng các câu lệnh gian lận.
  2. **Đảm bảo tính đồng nhất dữ liệu:** Giải pháp 2 ép AI xuất kết quả theo đúng khung Markdown cố định, giúp hệ thống dễ dàng lưu trữ lịch sử học tập và hiển thị đồng đều cho hàng trăm học viên cùng lúc.

---

### 2. Kết quả chạy thử nghiệm (Test Run)

#### Dữ liệu đầu vào (Test Input):
* **Chủ đề:** Cơ chế hoạt động của RAM (Bộ nhớ truy cập ngẫu nhiên).
* **Tài liệu gốc:** RAM là bộ nhớ tạm thời của máy tính, lưu trữ dữ liệu và chương trình đang chạy để CPU truy xuất nhanh. Dữ liệu trên RAM sẽ bị mất hoàn toàn khi tắt máy hoặc mất điện.
* **Tiêu chí Rubric:** (1) Độ chính xác: 5đ; (2) Tính đơn giản kiểu Feynman: 3đ; (3) Ví dụ thực tế: 2đ. Tổng: 10đ.
* **Bài giải thích của học viên:** "RAM giống như cái bàn làm việc của bạn vậy. Khi bạn làm việc, bạn lấy sách vở từ tủ (ổ cứng) bày lên bàn để đọc cho nhanh. Nhưng cuối ngày đi ngủ (tắt máy), bạn phải dọn sạch cái bàn đó đi. Hệ thống lưu trữ dữ liệu khả biến (volatile memory) này giúp tối ưu hiệu năng."

#### Kết quả phản hồi thực tế từ AI (Test Output):

> ### 1. Bảng điểm Rubric
> | Tiêu chí | Điểm đạt | Điểm tối đa | Nhận xét ngắn |
> | :--- | :---: | :---: | :--- |
> | Độ chính xác | 4.5 | 5.0 | Nắm đúng bản chất bộ nhớ tạm và mất dữ liệu khi tắt máy. Thiếu ý kết nối trực tiếp với tốc độ xử lý của CPU. |
> | Tính đơn giản kiểu Feynman | 2.5 | 3.0 | Hình ảnh cái bàn rất dễ hiểu, nhưng câu cuối dùng từ "dữ liệu khả biến (volatile memory)" hơi hàn lâm. |
> | Ví dụ thực tế | 2.0 | 2.0 | Ví dụ cái bàn làm việc và tủ sách cực kỳ trực quan, chính xác. |
> | **TỔNG ĐIỂM** | **9.0** | **10.0** | **Xuất sắc** |
> 
> ### 2. Phân tích lỗ hổng Feynman (Gap Analysis)
> - **Điểm làm tốt:** Phép ẩn dụ "cái bàn làm việc" giải thích xuất sắc vai trò lưu trữ tạm thời và sự khác biệt giữa RAM với ổ cứng.
> - **Lỗ hổng / Từ ngữ hàn lâm:** Cụm từ *"dữ liệu khả biến (volatile memory)"* là thuật ngữ kỹ thuật chuyên ngành, người mới học sẽ không hiểu nếu bạn không giải thích kèm theo.
> 
> ### 3. Gợi ý cải thiện
> - **Cách ví von lại:** Thay vì viết *"dữ liệu khả biến (volatile memory)"*, bạn chỉ cần viết: *"Loại bộ nhớ 'não cá vàng' này chỉ nhớ được khi còn điện, cứ tắt nguồn là quên sạch."*
> - **Câu hỏi gợi mở:** Trong ví dụ cái bàn làm việc của bạn, nhân vật nào sẽ là người ngồi đọc sách trên chiếc bàn đó (tương ứng với CPU trong máy tính)?


