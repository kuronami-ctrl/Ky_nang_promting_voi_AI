
# BÀI LÀM: KỸ THUẬT ÉP CẤU TRÚC ĐẦU RA JSON CHO AI

## Phần 1. Phân tích nguyên nhân lỗi

**1. Nguyên nhân AI tự động thêm lời chào và lời kết luận**

AI thường được huấn luyện để giao tiếp tự nhiên, lịch sự và thân thiện với người dùng. Vì vậy, khi nhận được yêu cầu, AI có xu hướng tự động thêm lời chào ở đầu và lời cảm ơn hoặc lời chúc ở cuối câu trả lời.

Trong trường hợp của TechShop, AI đã thêm lời chào trước chuỗi JSON và lời chúc sau chuỗi JSON.

**2. Tác hại của lỗi**

- Hệ thống không nhận được chuỗi JSON thuần túy.
- Lệnh `JSON.parse()` không thể đọc dữ liệu do xuất hiện ký tự không hợp lệ ở đầu chuỗi.
- Quá trình chuyển dữ liệu vào Database bị gián đoạn.
- Làm ảnh hưởng đến hoạt động tự động của hệ thống ERP.

**Kết luận:**

Lỗi xảy ra do AI trả về nội dung giao tiếp thông thường thay vì chỉ trả về dữ liệu có cấu trúc JSON. Vì vậy, cần sử dụng kỹ thuật Negative Constraint để giới hạn những nội dung AI không được phép tạo ra.

## Phần 2. Hoàn thiện Prompt ép cấu trúc

**Prompt hoàn chỉnh:**

```text
C – Character (Vai trò):
Bạn là một hệ thống chuyên trích xuất dữ liệu bảo hành cho phần mềm ERP của TechShop.

R – Request (Nhiệm vụ):
Đọc biên bản tiếp nhận bảo hành được cung cấp và trích xuất các thông tin sau:
- customer_name: Tên khách hàng.
- device: Tên thiết bị.
- issue: Mô tả lỗi của thiết bị.

E – Examples (Ví dụ):
Dữ liệu đầu vào:
Khách hàng Trần Văn A mang đến Laptop Dell XPS 15 để bảo hành do bị liệt phím Space.

Kết quả đầu ra:
{
  "customer_name": "Trần Văn A",
  "device": "Laptop Dell XPS 15",
  "issue": "Liệt phím Space"
}

A – Adjustment (Tinh chỉnh):
- Chỉ trích xuất thông tin có trong văn bản đầu vào.
- Không tự suy đoán hoặc thêm thông tin không có.
- Nếu không tìm thấy thông tin, trả về chuỗi rỗng "".
- Giữ nguyên nội dung thông tin được trích xuất.
- Không thêm lời chào hoặc lời kết luận.

T – Type of Output (Định dạng):
Chỉ trả về chuỗi JSON thuần túy.
- Không sử dụng Markdown Code Block.
- Không giải thích nội dung.
- Không thêm lời chào, lời cảm ơn hoặc lời chúc.
- Không thêm bất kỳ văn bản nào ngoài JSON.
- Kết quả phải bắt đầu bằng ký tự { và kết thúc bằng ký tự }.
- Sử dụng đúng 3 khóa: customer_name, device, issue.
- Đảm bảo đúng cú pháp JSON để hệ thống có thể xử lý.

E – Extras (Gia vị bổ sung):
Đây là dữ liệu được sử dụng trực tiếp trong hệ thống ERP của TechShop.
Ưu tiên tính chính xác và khả năng xử lý tự động.
Không được tự ý thay đổi tên các trường dữ liệu.

BIÊN BẢN CẦN XỬ LÝ:
[Dán nội dung biên bản bảo hành vào đây]
```


