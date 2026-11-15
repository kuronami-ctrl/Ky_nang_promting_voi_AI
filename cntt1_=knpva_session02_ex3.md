
# SESSION 02 – EX07: XÂY DỰNG MASTER PROMPT XỬ LÝ KHỦNG HOẢNG TRUYỀN THÔNG TECHSHOP

## Phần 1. Thiết kế chi tiết 6 khối CREATE

### 1. Character (C) – Vai trò

Bạn là Trưởng phòng Chăm sóc khách hàng (CSKH) của TechShop, có kinh nghiệm xử lý khiếu nại và giải quyết các vấn đề liên quan đến khách hàng. Bạn có trách nhiệm đại diện công ty gửi email xin lỗi và giải trình sự cố giao hàng.

### 2. Request (R) – Nhiệm vụ

Soạn email gửi đến từng khách hàng có đơn hàng linh kiện PC bị giao chậm từ 4 đến 6 ngày trong đợt Black Friday.

Email cần thực hiện các nhiệm vụ:
- Chân thành xin lỗi khách hàng.
- Giải thích rõ nguyên nhân giao hàng chậm.
- Thông báo lộ trình giao hàng mới.
- Đưa ra phương án bồi thường bằng Voucher giảm giá 15% cho đơn hàng tiếp theo.
- Cung cấp thông tin liên hệ để khách hàng được hỗ trợ nhanh chóng.

### 3. Examples (E) – Ví dụ

Sử dụng câu văn thể hiện sự đồng cảm và chân thành như:

"TechShop thành thật xin lỗi Quý khách vì sự chậm trễ trong quá trình giao hàng. Chúng tôi hiểu rằng việc nhận hàng không đúng thời gian cam kết đã gây ảnh hưởng đến kế hoạch và trải nghiệm mua sắm của Quý khách."

### 4. Adjustment (A) – Tinh chỉnh

- Sử dụng giọng văn chuyên nghiệp, lịch sự, chân thành và cầu thị.
- Thể hiện sự đồng cảm với sự bất tiện của khách hàng.
- Không đổ lỗi cho đơn vị vận chuyển hoặc bên thứ ba.
- Không sử dụng những lời giải thích mang tính bao biện.
- Không hứa hẹn những điều công ty chưa chắc chắn thực hiện được.
- Nội dung ngắn gọn, rõ ràng, tránh dài dòng.
- Luôn đặt quyền lợi và sự hài lòng của khách hàng lên hàng đầu.

### 5. Type of Output (T) – Định dạng

Trình bày theo cấu trúc email chuyên nghiệp gồm:

- Tiêu đề email: Nêu rõ nội dung xin lỗi và thông báo giao hàng.
- Lời chào: Kính gửi Quý khách [Tên khách hàng].
- Đoạn 1: Xin lỗi và thể hiện sự đồng cảm.
- Đoạn 2: Giải thích nguyên nhân sự cố giao hàng.
- Đoạn 3: Thông báo thời gian giao hàng mới và phương án bồi thường.
- Lời cam kết: Khẳng định trách nhiệm của TechShop.
- Thông tin liên hệ: Cung cấp hotline hỗ trợ khẩn cấp.
- Lời kết: Cảm ơn khách hàng đã thông cảm và tiếp tục tin tưởng TechShop.

### 6. Extras (E) – Gia vị bổ sung

Thông tin cần sử dụng trong email:

- Công ty: TechShop.
- Sự kiện: Black Friday.
- Số lượng đơn hàng bị ảnh hưởng: 3.000 đơn.
- Sản phẩm: Card màn hình, Nguồn máy tính, RAM.
- Thời gian giao hàng chậm: Từ 4 đến 6 ngày.
- Nguyên nhân: Hệ thống phân loại hàng hóa tự động tại kho bị quá tải.
- Chính sách bồi thường: Voucher giảm giá 15% cho đơn hàng tiếp theo.
- Tên khách hàng: [Tên khách hàng].
- Mã đơn hàng: [Mã đơn hàng].
- Thời gian giao hàng mới: [Ngày giao hàng dự kiến đã xác nhận].
- Hotline VIP: [Số hotline CSKH].
- Không tự ý tạo số hotline hoặc ngày giao hàng khi chưa có thông tin chính thức.

---

## Phần 2. Master Prompt hoàn chỉnh

### Prompt áp dụng thực tế

```text
C – CHARACTER (VAI TRÒ):

Bạn là Trưởng phòng Chăm sóc khách hàng (CSKH) của TechShop, có kinh nghiệm xử lý khiếu nại và giải quyết các vấn đề liên quan đến khách hàng. Bạn đại diện công ty gửi email xin lỗi và giải trình sự cố giao hàng.

R – REQUEST (NHIỆM VỤ):

Hãy soạn một email gửi riêng đến từng khách hàng có đơn hàng linh kiện PC bị giao chậm từ 4 đến 6 ngày trong đợt Black Friday.

Email cần:
- Chân thành xin lỗi khách hàng.
- Giải thích minh bạch nguyên nhân giao hàng chậm.
- Thông báo thời gian giao hàng mới.
- Tặng Voucher giảm giá 15% cho đơn hàng tiếp theo.
- Cung cấp hotline hỗ trợ khẩn cấp.

E – EXAMPLES (VÍ DỤ):

Tham khảo cách diễn đạt:

"TechShop thành thật xin lỗi Quý khách vì sự chậm trễ trong quá trình giao hàng. Chúng tôi hiểu rằng việc nhận hàng không đúng thời gian cam kết đã gây ảnh hưởng đến kế hoạch và trải nghiệm mua sắm của Quý khách."

A – ADJUSTMENT (TINH CHỈNH):

- Giọng văn chuyên nghiệp, chân thành, cầu thị và đồng cảm.
- Không đổ lỗi cho đơn vị vận chuyển hoặc bên thứ ba.
- Không đưa ra lời giải thích mang tính bao biện.
- Không hứa suông hoặc cam kết thời gian chưa được xác nhận.
- Không sử dụng ngôn ngữ thiếu tôn trọng khách hàng.
- Nội dung súc tích, rõ ràng, dễ hiểu.
- Thể hiện trách nhiệm của TechShop trong việc khắc phục sự cố.

T – TYPE OF OUTPUT (ĐỊNH DẠNG):

Trình bày dưới dạng email chuyên nghiệp với cấu trúc:

1. Tiêu đề email rõ ràng.
2. Lời chào trang trọng.
3. Đoạn 1: Xin lỗi và thể hiện sự đồng cảm.
4. Đoạn 2: Giải thích nguyên nhân sự cố.
5. Đoạn 3: Thông báo lịch giao hàng mới và Voucher bồi thường.
6. Lời cam kết khắc phục và chịu trách nhiệm.
7. Thông tin hotline hỗ trợ khẩn cấp.
8. Lời cảm ơn và chữ ký TechShop.

EXTRAS – GIA VỊ BỔ SUNG:

Thông tin sự cố:
- Công ty: TechShop.
- Sự kiện: Black Friday.
- Số đơn hàng bị ảnh hưởng: 3.000 đơn.
- Sản phẩm: Card màn hình, Nguồn máy tính, RAM.
- Thời gian chậm: 4 đến 6 ngày.
- Nguyên nhân: Hệ thống phân loại hàng hóa tự động tại kho bị quá tải.
- Bồi thường: Voucher giảm giá 15% cho đơn hàng tiếp theo.

Thông tin khách hàng:
- Tên khách hàng: [Tên khách hàng].
- Mã đơn hàng: [Mã đơn hàng].
- Ngày giao hàng mới: [Ngày giao hàng đã xác nhận].
- Hotline VIP: [Số hotline chính thức].
g cách và định dạng cần thực hiện.

Trong tình huống của TechShop, việc sử dụng CREATE giúp email thể hiện sự chân thành, minh bạch, có phương án bồi thường cụ thể và góp phần lấy lại niềm tin của khách hàng.

