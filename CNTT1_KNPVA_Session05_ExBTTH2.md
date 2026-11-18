# XÂY DỰNG CHUỖI PROMPT VIẾT BÀI PR SẢN PHẨM CÔNG NGHỆ

## 1. Phân tích yêu cầu đề bài

**Mục tiêu:**

Xây dựng một chuỗi gồm 3 Prompt để hỗ trợ AI viết bài PR giới thiệu sản phẩm AI Chatbot dành cho doanh nghiệp.

**Các yêu cầu cần giải quyết:**

- Xác định khách hàng mục tiêu và những khó khăn họ đang gặp phải.
- Xây dựng dàn ý chi tiết cho bài viết PR.
- Viết bài PR hoàn chỉnh từ dàn ý đã tạo.
- Tối ưu từ khóa SEO để bài viết dễ tiếp cận người đọc.
- Đảm bảo nội dung giữa các phần không bị lặp lại hoặc thay đổi giọng văn.
- Có cách xử lý khi AI đang viết nhưng bị dừng giữa chừng.

## 2. Lựa chọn phương pháp và giải thích

**Phương pháp lựa chọn: Prompt Chaining.**

Prompt Chaining là kỹ thuật chia một nhiệm vụ lớn thành nhiều Prompt nhỏ. Kết quả của Prompt trước được sử dụng làm dữ liệu đầu vào cho Prompt tiếp theo.

**Lý do lựa chọn:**

Bài viết PR dài từ 1.000 đến 1.500 từ có nhiều công đoạn. Nếu chỉ sử dụng một Prompt, AI có thể viết thiếu ý, lặp nội dung hoặc không giữ được sự thống nhất.

Vì vậy, em chọn Prompt Chaining vì:

- Chia công việc thành từng bước rõ ràng.
- Giúp nội dung được xây dựng có trình tự.
- Dễ kiểm tra và chỉnh sửa từng phần.
- Giúp duy trì giọng văn thống nhất trong toàn bài.
- Có thể tiếp tục viết khi AI bị dừng giữa chừng.

## 3. Xây dựng chuỗi Prompt giải quyết bài toán

### Prompt 1: Nghiên cứu khách hàng mục tiêu

**Mục đích:** Xác định đối tượng khách hàng và những vấn đề mà AI Chatbot có thể giải quyết.

**Prompt sử dụng:**

```text
Bạn là chuyên viên nghiên cứu thị trường trong lĩnh vực công nghệ.

Nhiệm vụ:
Nghiên cứu đối tượng khách hàng mục tiêu cho sản phẩm
AI Chatbot dành cho doanh nghiệp.

Hãy thực hiện các yêu cầu:

1. Xác định nhóm khách hàng mục tiêu.
2. Phân tích nhu cầu của từng nhóm khách hàng.
3. Liệt kê ít nhất 5 khó khăn mà doanh nghiệp thường gặp.
4. Đề xuất cách AI Chatbot có thể giải quyết từng khó khăn.
5. Xác định lợi ích nổi bật của sản phẩm.

Yêu cầu:
- Trình bày rõ ràng, dễ hiểu.
- Không tự tạo ra thông tin về tính năng sản phẩm.
- Nếu thiếu thông tin, hãy ghi rõ phần cần bổ sung.
- Giữ giọng văn chuyên nghiệp và đáng tin cậy.

Định dạng đầu ra:
- Khách hàng mục tiêu.
- Nhu cầu khách hàng.
- Danh sách khó khăn (Pain Points).
- Giải pháp của AI Chatbot.
- Lợi ích nổi bật.

Cuối cùng, tổng hợp kết quả thành dữ liệu
để chuyển sang Prompt 2.
```

**Kết quả đầu ra của Prompt 1:**

- Khách hàng mục tiêu: Doanh nghiệp vừa và nhỏ, cửa hàng trực tuyến, bộ phận chăm sóc khách hàng.
- Khó khăn:
  1. Khách hàng phải chờ lâu mới được phản hồi.
  2. Nhân viên phải trả lời nhiều câu hỏi giống nhau.
  3. Khó hỗ trợ khách hàng ngoài giờ làm việc.
  4. Khó quản lý lượng lớn tin nhắn.
  5. Chi phí chăm sóc khách hàng cao.
- Giải pháp: Sử dụng AI Chatbot để hỗ trợ trả lời câu hỏi, tự động tiếp nhận yêu cầu và giảm công việc lặp lại.

### Prompt 2: Xây dựng dàn ý bài PR

**Mục đích:** Sử dụng kết quả của Prompt 1 để xây dựng dàn ý cho bài viết.

**Dữ liệu đầu vào:** Toàn bộ kết quả nghiên cứu khách hàng từ Prompt 1.

**Prompt sử dụng:**

```text
Bạn là chuyên viên xây dựng nội dung Marketing.

Nhiệm vụ:
Dựa trên kết quả nghiên cứu khách hàng từ Prompt 1,
hãy xây dựng dàn ý chi tiết cho bài PR giới thiệu
sản phẩm AI Chatbot dành cho doanh nghiệp.

DỮ LIỆU TỪ PROMPT 1:
[Dán toàn bộ kết quả Prompt 1 vào đây]

Yêu cầu:

1. Xây dựng một tiêu đề thu hút.
2. Viết ý tưởng cho đoạn mở đầu (Lead).
3. Chia nội dung thành các tiêu đề H2 và H3.
4. Mỗi tiêu đề phải giải quyết một vấn đề của khách hàng.
5. Sắp xếp nội dung theo trình tự hợp lý.
6. Bổ sung phần giới thiệu lợi ích và giải pháp của sản phẩm.
7. Kết thúc bằng lời kêu gọi hành động (CTA).

Yêu cầu SEO:
- Đề xuất từ khóa chính.
- Đề xuất các từ khóa phụ.
- Đưa từ khóa vào những phần phù hợp.

Yêu cầu giọng văn:
Chuyên nghiệp, tin cậy, dễ hiểu và thống nhất.

Định dạng đầu ra:
- Tiêu đề bài viết.
- Từ khóa SEO.
- Đoạn mở đầu dự kiến.
- Dàn ý H2, H3.
- Nội dung chính cần triển khai ở từng phần.
- CTA dự kiến.

Cuối cùng, xuất toàn bộ dàn ý để chuyển sang Prompt 3.
Không tự ý thay đổi các vấn đề khách hàng đã xác định
ở Prompt 1.
```

**Kết quả đầu ra của Prompt 2:**

- Tiêu đề: AI Chatbot – Giải pháp hỗ trợ chăm sóc khách hàng hiệu quả cho doanh nghiệp.
- Từ khóa chính: AI Chatbot doanh nghiệp.
- Từ khóa phụ: Chatbot chăm sóc khách hàng, tự động hóa chăm sóc khách hàng.

**Dàn ý dự kiến:**

- Mở đầu: Những khó khăn trong việc chăm sóc khách hàng.
- H2: Những vấn đề doanh nghiệp thường gặp.
  - H3: Khách hàng phải chờ đợi phản hồi.
  - H3: Nhân viên mất nhiều thời gian trả lời câu hỏi.
- H2: AI Chatbot là gì?
- H2: Những lợi ích của AI Chatbot đối với doanh nghiệp.
  - H3: Hỗ trợ khách hàng nhanh chóng.
  - H3: Giảm công việc lặp lại.
  - H3: Hỗ trợ ngoài giờ làm việc.
- H2: Vì sao doanh nghiệp nên ứng dụng AI Chatbot?
- H2: Kết luận và lời kêu gọi hành động.

### Prompt 3: Viết bài PR hoàn chỉnh và tối ưu SEO

**Mục đích:** Sử dụng dàn ý từ Prompt 2 để viết thành bài PR hoàn chỉnh.

**Dữ liệu đầu vào:** Kết quả nghiên cứu từ Prompt 1 và dàn ý từ Prompt 2.

**Prompt sử dụng:**

```text
Bạn là chuyên viên Content Marketing chuyên viết
bài PR cho các sản phẩm công nghệ.

Nhiệm vụ:
Dựa trên kết quả nghiên cứu khách hàng ở Prompt 1
và dàn ý ở Prompt 2, hãy viết bài PR hoàn chỉnh
giới thiệu sản phẩm AI Chatbot dành cho doanh nghiệp.

DỮ LIỆU ĐẦU VÀO:

1. Kết quả Prompt 1:
[Dán kết quả nghiên cứu khách hàng vào đây]

2. Kết quả Prompt 2:
[Dán dàn ý bài viết vào đây]

Yêu cầu viết bài:

- Độ dài từ 1.000 đến 1.500 từ.
- Có tiêu đề chính hấp dẫn.
- Có đoạn mở đầu giải quyết vấn đề của khách hàng.
- Triển khai đầy đủ các tiêu đề H2 và H3.
- Nội dung rõ ràng, có liên kết giữa các phần.
- Có lời kêu gọi hành động (CTA) ở cuối bài.

Yêu cầu SEO:

- Sử dụng từ khóa chính và từ khóa phụ tự nhiên.
- Không lặp từ khóa quá nhiều.
- Tiêu đề và các tiêu đề phụ phải phù hợp với nội dung.
- Nội dung dễ đọc và có giá trị với người xem.

Quy tắc:

- Giữ giọng văn chuyên nghiệp, tin cậy từ đầu đến cuối.
- Không thay đổi dàn ý đã được thống nhất.
- Không tự tạo ra tính năng hoặc số liệu chưa được cung cấp.
- Tránh lặp lại nội dung giữa các phần.
- Đảm bảo các đoạn văn có sự liên kết.

Nếu bài viết bị dừng giữa chừng:
Hãy dừng tại cuối một đoạn văn hoàn chỉnh và ghi lại
tiêu đề, đoạn cuối cùng đã viết.

Khi nhận được lệnh TIẾP TỤC:
- Tiếp tục ngay sau câu cuối cùng đã viết.
- Không viết lại nội dung cũ.
- Giữ nguyên dàn ý và giọng văn.
- Tiếp tục cho đến khi hoàn thành bài viết.

Đầu ra:
Một bài PR hoàn chỉnh từ 1.000 đến 1.500 từ,
đúng cấu trúc SEO và có CTA ở cuối bài.
```

## 4. Cách truyền dữ liệu giữa 3 Prompt

Để các bước không bị mất thông tin, cần chuyển kết quả của bước trước sang bước sau.

| Giai đoạn | Dữ liệu đầu vào | Kết quả đầu ra |
|---|---|---|
| Prompt 1 | Thông tin sản phẩm | Khách hàng và Pain Points |
| Prompt 2 | Kết quả Prompt 1 | Dàn ý và từ khóa SEO |
| Prompt 3 | Kết quả Prompt 1 và 2 | Bài PR hoàn chỉnh |

**Quy trình thực hiện:**

Prompt 1 → Prompt 2 → Prompt 3 → Bài PR hoàn chỉnh.

Mỗi bước đều phải sử dụng kết quả của bước trước, không được bỏ qua dữ liệu đã có.

## 5. Xử lý khi AI bị dừng giữa chừng

Trong trường hợp AI đang viết bài nhưng bị dừng do giới hạn độ dài, người dùng có thể sử dụng câu lệnh sau:

**Câu lệnh tiếp tục:**

```text
TIẾP TỤC VIẾT BÀI.

Hãy tiếp tục nội dung ngay sau câu cuối cùng
của phần trước.

Yêu cầu:
- Không viết lại nội dung đã hoàn thành.
- Không lặp lại tiêu đề hoặc đoạn văn cũ.
- Giữ nguyên dàn ý đã thống nhất.
- Giữ giọng văn chuyên nghiệp, tin cậy.
- Đảm bảo nội dung mới liên kết tự nhiên
  với đoạn văn trước đó.
- Tiếp tục cho đến khi hoàn thành bài viết
  từ 1.000 đến 1.500 từ.

Tiêu đề cuối cùng đã viết: [Ghi tiêu đề]
Câu cuối cùng đã viết: [Dán câu cuối cùng]
Phần tiếp theo cần triển khai: [Ghi tiêu đề H2/H3 tiếp theo]
```


