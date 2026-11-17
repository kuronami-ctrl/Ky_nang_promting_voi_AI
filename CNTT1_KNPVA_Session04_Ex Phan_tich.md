## 1. Phân tích yêu cầu đề bài

**Mục tiêu:**

Tạo ra 2 cách viết câu lệnh (Prompt) khác nhau để yêu cầu AI giải quyết một công việc có nhiều bước. Sau đó so sánh và chọn cách viết hiệu quả hơn.

**Những vấn đề cần giải quyết:**

- **Chain-of-Thought (Suy luận theo từng bước):** Yêu cầu AI chia công việc thành các bước nhỏ, thực hiện lần lượt để tránh bỏ sót.
- **Prompt Chaining (Nối các bước Prompt):** Chia một công việc lớn thành nhiều phần. Kết quả của phần trước được sử dụng làm thông tin đầu vào cho phần tiếp theo.
- **Xử lý khi gặp lỗi:** Quy định AI cần làm gì khi thiếu thông tin, dữ liệu không hợp lý hoặc không đủ thời gian thực hiện.

**Bài toán lựa chọn:**

Lập kế hoạch học tập cho sinh viên dựa trên số bài tập cần làm, thời gian thực hiện và hạn nộp của từng bài.

## 2. Lựa chọn phương pháp và giải thích

Tôi lựa chọn kết hợp hai phương pháp:

**Phương pháp 1: Suy luận theo từng bước**

Yêu cầu AI thực hiện công việc theo trình tự:

1. Kiểm tra thông tin các bài tập.
2. Xác định bài tập cần ưu tiên.
3. Phân chia thời gian thực hiện.
4. Kiểm tra lại kế hoạch.

Cách này giúp AI xử lý công việc có thứ tự và hạn chế bỏ sót thông tin.

**Phương pháp 2: Chia công việc thành nhiều Prompt**

Thay vì yêu cầu AI làm tất cả trong một lần, tôi chia công việc thành từng phần. Ví dụ: kiểm tra dữ liệu trước, sau đó mới sắp xếp thứ tự ưu tiên và lập kế hoạch.

Cách này giúp dễ kiểm tra và sửa lại từng phần nếu có sai sót.

**Lý do lựa chọn:**

Hai phương pháp trên phù hợp với bài toán lập kế hoạch học tập vì công việc có nhiều bước liên quan đến nhau. Nếu thực hiện không theo thứ tự, AI có thể sắp xếp thời gian chưa hợp lý hoặc bỏ sót bài tập.

## 3. Đề xuất 2 Prompt mẫu

### Giải pháp 1: Prompt đơn giản, ngắn gọn

```text
Bạn là trợ lý học tập. Hãy giúp tôi lập kế hoạch hoàn thành
các bài tập dựa trên thời gian có sẵn và hạn nộp bài.

Hãy thực hiện theo các bước:
1. Kiểm tra thông tin các bài tập.
2. Xác định bài nào cần ưu tiên.
3. Sắp xếp thời gian thực hiện từng bài.
4. Kiểm tra xem kế hoạch có phù hợp với thời gian có sẵn không.

Nếu thiếu thông tin, hãy hỏi lại tôi.

Trình bày kết quả ngắn gọn, dễ hiểu bằng tiếng Việt.
```

**Giải thích:**

Đây là cách viết Prompt đơn giản. Người dùng chỉ cần nói rõ vai trò của AI, công việc cần làm và các bước thực hiện.

Ưu điểm là ngắn gọn, dễ viết và không mất nhiều thời gian. Tuy nhiên, câu lệnh chưa quy định cụ thể cách xử lý khi dữ liệu bị thiếu hoặc khi thời gian không đủ để hoàn thành tất cả bài tập.

### Giải pháp 2: Prompt chi tiết, có nhiều yêu cầu hơn

```text
VAI TRÒ:
Bạn là trợ lý học tập, có nhiệm vụ giúp sinh viên sắp xếp
công việc và thời gian học tập hợp lý.

NHIỆM VỤ:
Lập kế hoạch hoàn thành các bài tập dựa trên thời gian có sẵn,
hạn nộp và mức độ quan trọng của từng bài.

CÁC BƯỚC THỰC HIỆN:

Bước 1: Kiểm tra thông tin
- Liệt kê tất cả các bài tập cần hoàn thành.
- Xác định thời gian cần thiết cho từng bài.
- Kiểm tra hạn nộp của từng bài.
- Nếu thiếu thông tin quan trọng, hãy hỏi lại người dùng.

Bước 2: Sắp xếp thứ tự ưu tiên
- Ưu tiên bài tập có hạn nộp gần nhất.
- Chú ý đến mức độ quan trọng của từng bài.
- Không tự ý thay đổi thông tin người dùng đã cung cấp.

Bước 3: Lập kế hoạch học tập
- Sắp xếp các bài tập theo thứ tự ưu tiên.
- Chia thời gian phù hợp cho từng bài.
- Không sắp xếp tổng thời gian vượt quá thời gian người dùng có.
- Nếu không đủ thời gian, hãy thông báo rõ phần việc còn lại.

Bước 4: Kiểm tra lại kế hoạch
- Kiểm tra xem có bài tập nào bị bỏ sót không.
- Kiểm tra tổng thời gian thực hiện.
- Kiểm tra xem các bài có được sắp xếp hợp lý không.

Bước 5: Xử lý khi gặp vấn đề
- Nếu thiếu thông tin, hãy hỏi lại người dùng.
- Nếu dữ liệu không hợp lý hoặc mâu thuẫn, hãy thông báo rõ.
- Nếu không đủ thời gian, hãy đề xuất kế hoạch tiếp tục
  vào ngày hôm sau.
- Không tự ý tạo thêm thông tin hoặc thời gian.

YÊU CẦU KẾT QUẢ:
1. Liệt kê các bài tập.
2. Nêu thứ tự ưu tiên và lý do.
3. Lập lịch thực hiện cụ thể.
4. Chỉ ra công việc chưa hoàn thành (nếu có).
5. Đưa ra kết luận ngắn gọn.

Sử dụng tiếng Việt đơn giản, dễ hiểu.
Trình bày rõ ràng, không viết dài dòng.
Chỉ nêu kết quả và giải thích ngắn gọn cho các lựa chọn.
```

**Giải thích:**

Đây là cách viết Prompt chi tiết hơn. Thay vì chỉ yêu cầu AI lập kế hoạch, chúng ta quy định rõ từng bước AI cần thực hiện và cách xử lý khi gặp vấn đề.

Ưu điểm là kiểm soát công việc tốt hơn, hạn chế bỏ sót thông tin. Nhược điểm là câu lệnh dài hơn và cần nhiều thời gian để viết.

## 4. Bảng so sánh hai giải pháp

| Tiêu chí | Giải pháp 1 (Đơn giản) | Giải pháp 2 (Chi tiết) |
|---|---|---|
| Độ dễ hiểu | Cao, dễ đọc và dễ sử dụng | Trung bình, có nhiều nội dung hơn |
| Độ dài Prompt | Ngắn | Dài |
| Lượng nội dung AI cần xử lý | Ít hơn | Nhiều hơn |
| Khả năng hạn chế lỗi | Trung bình | Tốt |
| Xử lý khi thiếu thông tin | Chỉ yêu cầu hỏi lại | Có quy định cụ thể |
| Sắp xếp công việc | Cơ bản | Theo từng bước rõ ràng |
| Khả năng kiểm tra kết quả | Chưa chi tiết | Có bước kiểm tra riêng |

**Nhận xét:**

- Giải pháp 1 phù hợp với công việc đơn giản, không có quá nhiều yêu cầu.
- Giải pháp 2 phù hợp với công việc có nhiều bước, cần kiểm tra và xử lý các trường hợp phát sinh.

## 5. Lựa chọn phương án tối ưu

**Tôi lựa chọn Giải pháp 2 – Prompt chi tiết.**

**Lý do lựa chọn:**

- Có các bước thực hiện rõ ràng, giúp AI làm việc theo đúng trình tự.
- Có hướng xử lý khi thiếu thông tin hoặc không đủ thời gian.
- Có bước kiểm tra lại kết quả để hạn chế sai sót.
- Kết quả được trình bày theo yêu cầu nên người dùng dễ theo dõi.

Mặc dù Prompt dài hơn và cần nhiều nội dung hơn, nhưng đổi lại người dùng có thể kiểm soát công việc tốt hơn. Vì vậy, tôi cho rằng Giải pháp 2 phù hợp hơn với bài toán này.

## 6. Chạy thử Prompt đã chọn

**Dữ liệu đưa vào:**

Giả sử tôi có 3 bài tập cần hoàn thành:

| Bài tập | Thời gian cần | Hạn nộp | Mức độ quan trọng |
|---|---:|---|---|
| Lập trình C | 90 phút | Ngày mai | Cao |
| Từ vựng tiếng Nhật | 45 phút | Sau 2 ngày | Trung bình |
| Báo cáo môn CNTT | 120 phút | Sau 3 ngày | Cao |

Tổng thời gian có thể học hôm nay là **180 phút**.

**Kết quả AI trả về:**

**Bước 1: Kiểm tra thông tin**

- Có 3 bài tập cần hoàn thành.
- Tổng thời gian cần: 255 phút.
- Thời gian có sẵn: 180 phút.
- Như vậy, còn thiếu 75 phút để hoàn thành tất cả bài tập.

**Bước 2: Sắp xếp thứ tự ưu tiên**

1. Lập trình C: Hạn nộp ngày mai nên cần làm trước.
2. Từ vựng tiếng Nhật: Hạn nộp sau 2 ngày, thời gian thực hiện ngắn.
3. Báo cáo môn CNTT: Hạn nộp sau 3 ngày, có thể tiếp tục vào ngày hôm sau.

**Bước 3: Lập kế hoạch hôm nay**

| Thời gian | Công việc | Thời lượng |
|---|---|---:|
| 18:00 – 19:30 | Lập trình C | 90 phút |
| 19:30 – 20:15 | Từ vựng tiếng Nhật | 45 phút |
| 20:15 – 21:00 | Báo cáo môn CNTT | 45 phút |

**Bước 4: Kiểm tra kết quả**

- Lập trình C: Hoàn thành.
- Từ vựng tiếng Nhật: Hoàn thành.
- Báo cáo môn CNTT: Còn 75 phút, cần tiếp tục vào ngày hôm sau.
- Tổng thời gian học hôm nay: 180 phút, không vượt quá thời gian có sẵn.

**Nhận xét kết quả chạy thử:**

AI đã sắp xếp được các bài tập theo thời hạn, phân chia thời gian và xác định phần công việc chưa hoàn thành. Kết quả phù hợp với dữ liệu đã cung cấp.

