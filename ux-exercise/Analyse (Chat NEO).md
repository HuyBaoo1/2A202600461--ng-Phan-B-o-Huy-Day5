# Chatbot NEO (Vietnam Airlines)

## Marketing & Mục tiêu
* **Tra cứu thông tin:** Hỗ trợ tìm kiếm thông tin vé máy bay và tình trạng chuyến bay.
* **Giải đáp thắc mắc:** Xử lý các câu hỏi liên quan đến quy trình mua vé và quy định hành lý.

---

## 4 Paths User Stories

| Path | Kịch bản & Phản hồi |
| :--- | :--- |
| **Đúng (Happy Path)** | **User:** Tìm vé HN - SG <br> **AI:** Gợi ý vé có mức giá rẻ nhất + khứ hồi theo ngày thực tế + Link đặt vé trực tiếp. |
| **Không chắc (Low Confidence)** | **User:** "Có chắc đó là mức giá rẻ nhất?" <br> **AI:** Phản hồi "Hiện chưa có thông tin. Vui lòng liên hệ với tư vấn viên" + Cung cấp thông tin liên hệ (Không tự động nối máy với tổng đài viên). |
| **Khi sai (Failure)** | **User:** Tìm chuyến bay rẻ nhất trong 3 ngày tới <br> **AI:** Yêu cầu người dùng "Nhập mã đặt chỗ" (Lỗi: Đi sai lệch task được giao). |
| **Khi mất tích (Retention)** | **User:** Đột ngột tắt tab trình duyệt <br> **AI:** Khi quay lại và bật lại, hệ thống vẫn duy trì và hiển thị lịch sử tìm kiếm cũ. |

---

## Sketch Path 2 (Intent Misclassification)

**Scenario (Ngữ cảnh lỗi):**
Khi khách hàng thực hiện tìm kiếm chuyến bay, hệ thống AI bị nhận diện nhầm (misclassification). Thay vì kích hoạt task **"Tìm kiếm / Mua vé"**, AI lại bắt nhầm từ khóa **"chuyến bay"** và gọi ngay task **"Tra cứu thông tin vé đã đặt"**. 

> **Hậu quả:** Người dùng muốn mua vé nhưng bị yêu cầu cung cấp thông tin vé đã mua, gây đứt gãy trải nghiệm.