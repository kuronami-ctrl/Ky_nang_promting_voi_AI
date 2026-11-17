## 1. Phân tích yêu cầu đề bài

### 1.1. Mục tiêu

Xây dựng một chuỗi Prompt liên kết với nhau để AI giải quyết một công việc lớn thông qua nhiều bước nhỏ.

Hệ thống cần thực hiện được các yêu cầu:

-   Tiếp nhận và kiểm tra dữ liệu đầu vào.
    
-   Phân tích thông tin và sắp xếp công việc.
    
-   Lập kế hoạch phù hợp với thời gian có sẵn.
    
-   Kiểm tra lại kết quả trước khi trả lời.
    
-   Xử lý dữ liệu thiếu, sai định dạng hoặc bị trùng lặp.
    

### 1.2. Bài toán lựa chọn

Tôi lựa chọn xây dựng **StudyBot AI – Trợ lý học tập thông minh**.

Đây là chatbot hỗ trợ sinh viên quản lý bài tập và sắp xếp thời gian học tập.

Ví dụ: Sinh viên cung cấp danh sách bài tập, hạn nộp và thời gian cần hoàn thành. AI sẽ kiểm tra thông tin, sắp xếp thứ tự ưu tiên và tạo kế hoạch học tập.

### 1.3. Các vấn đề cần giải quyết

-   Người dùng có thể nhập thiếu tên bài hoặc thời gian thực hiện.
    
-   Ngày tháng có thể được viết theo nhiều định dạng khác nhau.
    
-   Danh sách có thể chứa bài tập bị trùng.
    
-   Thời gian có sẵn có thể không đủ để hoàn thành tất cả bài tập.
    
-   AI có thể đưa ra kế hoạch chưa hợp lý nếu không kiểm tra lại.
    

## 2. Lựa chọn phương pháp thực hiện

Tôi sử dụng kết hợp 3 phương pháp:

### 2.1. Chain-of-Thought (Xử lý theo từng bước)

Yêu cầu AI chia công việc lớn thành các bước nhỏ và thực hiện theo thứ tự.

Ví dụ:

1.  Kiểm tra dữ liệu.
    
2.  Sắp xếp bài tập.
    
3.  Lập kế hoạch.
    
4.  Kiểm tra kết quả.
    

Cách này giúp AI làm việc có trình tự và hạn chế bỏ sót thông tin.

### 2.2. Prompt Chaining (Nối các Prompt)

Chia công việc thành nhiều Prompt riêng biệt. Kết quả của Prompt trước được chuyển sang Prompt tiếp theo.

Ví dụ:

-   Prompt 1 kiểm tra dữ liệu.
    
-   Prompt 2 sắp xếp bài tập.
    
-   Prompt 3 lập kế hoạch.
    
-   Prompt 4 kiểm tra kết quả cuối cùng.
    

### 2.3. Xử lý khi gặp lỗi

Hệ thống cần có cách xử lý khi:

-   Thiếu thông tin: yêu cầu người dùng bổ sung.
    
-   Sai ngày tháng: đánh dấu và yêu cầu sửa.
    
-   Bài tập bị trùng: giữ một bản ghi và thông báo.
    
-   Không đủ thời gian: lập kế hoạch trong giới hạn cho phép và ghi rõ phần còn lại.
    

Nếu một bài tập bị lỗi, hệ thống vẫn tiếp tục xử lý những bài tập hợp lệ khác.

## 3. Thiết kế chuỗi Prompt liên kết

Chuỗi Prompt gồm 4 bước được thực hiện lần lượt.

### Prompt 1: Kiểm tra và làm sạch dữ liệu

**Mục đích:** Kiểm tra thông tin người dùng cung cấp, phát hiện dữ liệu thiếu, sai hoặc trùng lặp.

```
VAI TRÒ:
Bạn là trợ lý kiểm tra dữ liệu học tập.

NHIỆM VỤ:
Kiểm tra danh sách bài tập do sinh viên cung cấp.

CÁC BƯỚC:
1. Kiểm tra tên bài tập.
2. Kiểm tra hạn nộp.
3. Kiểm tra thời gian cần hoàn thành.
4. Phát hiện bài tập bị trùng.
5. Kiểm tra ngày tháng có hợp lệ không.
6. Chuẩn hóa ngày tháng về dạng DD/MM/YYYY.

CÁCH XỬ LÝ:
- Thiếu thông tin: đánh dấu THIẾU DỮ LIỆU.
- Ngày tháng sai: đánh dấu DỮ LIỆU KHÔNG HỢP LỆ.
- Bài tập trùng: giữ một bản ghi và ghi nhận bản trùng.
- Không tự ý đoán hoặc bổ sung thông tin.
- Không để một bài tập lỗi làm ảnh hưởng đến bài tập hợp lệ khác.

KẾT QUẢ:
Trả về:
1. Danh sách bài tập hợp lệ.
2. Danh sách bài tập cần sửa hoặc bổ sung.
3. Danh sách bài tập bị trùng.

Sử dụng định dạng JSON thống nhất để chuyển sang bước tiếp theo.
```

### Prompt 2: Phân tích và sắp xếp thứ tự ưu tiên

**Mục đích:** Sử dụng dữ liệu hợp lệ từ Prompt 1 để xác định bài nào cần làm trước.

```
VAI TRÒ:
Bạn là trợ lý sắp xếp công việc học tập.

DỮ LIỆU ĐẦU VÀO:
Nhận danh sách bài tập hợp lệ từ bước 1.

NHIỆM VỤ:
Sắp xếp các bài tập theo thứ tự ưu tiên.

QUY TẮC:
1. Ưu tiên bài có hạn nộp gần nhất.
2. Nếu hai bài có hạn nộp giống nhau, ưu tiên bài quan trọng hơn.
3. Không thay đổi thông tin người dùng đã cung cấp.
4. Không sử dụng bài tập chưa đủ thông tin để sắp xếp.
5. Nếu có thông tin không rõ ràng, hãy ghi chú.

KẾT QUẢ:
- Danh sách bài tập theo thứ tự ưu tiên.
- Lý do sắp xếp.
- Danh sách bài tập chưa thể sắp xếp.

Chuyển kết quả sang bước lập kế hoạch.
```

### Prompt 3: Lập kế hoạch học tập

**Mục đích:** Sử dụng danh sách đã sắp xếp để chia thời gian học tập hợp lý.

```
VAI TRÒ:
Bạn là trợ lý lập kế hoạch học tập.

DỮ LIỆU ĐẦU VÀO:
- Danh sách bài tập đã được sắp xếp ở bước 2.
- Tổng thời gian học có sẵn do người dùng cung cấp.

NHIỆM VỤ:
Lập kế hoạch hoàn thành các bài tập.

QUY TẮC:
1. Thực hiện theo thứ tự ưu tiên.
2. Không vượt quá tổng thời gian có sẵn.
3. Không tự ý thay đổi thời gian cần thiết của từng bài.
4. Không đưa bài tập thiếu thông tin vào kế hoạch chính.
5. Nếu không đủ thời gian, ghi rõ phần việc còn lại.
6. Không tự ý khẳng định bài tập đã hoàn thành khi mới chỉ được xếp lịch.

KẾT QUẢ:
- Tên bài tập.
- Thời gian bắt đầu và kết thúc.
- Thời lượng thực hiện.
- Phần việc đã được xếp lịch.
- Phần việc cần tiếp tục vào ngày sau.

Chuyển kết quả sang bước kiểm tra cuối cùng.
```

### Prompt 4: Kiểm tra và hoàn thiện kết quả

**Mục đích:** Kiểm tra kế hoạch vừa tạo để hạn chế sai sót trước khi trả lời người dùng.

```
VAI TRÒ:
Bạn là trợ lý kiểm tra kế hoạch học tập.

DỮ LIỆU ĐẦU VÀO:
Nhận kế hoạch được tạo ở bước 3.

NHIỆM VỤ:
Kiểm tra lại toàn bộ kế hoạch.

CÁC ĐIỂM CẦN KIỂM TRA:
1. Có bỏ sót bài tập hợp lệ không?
2. Tổng thời gian có vượt quá thời gian có sẵn không?
3. Thứ tự thực hiện có phù hợp với hạn nộp không?
4. Có sử dụng dữ liệu sai hoặc chưa được xác nhận không?
5. Có thời gian nào bị xếp chồng lên nhau không?

CÁCH XỬ LÝ:
- Nếu kế hoạch hợp lý, xác nhận kết quả.
- Nếu phát hiện lỗi, chỉ rõ lỗi và đề xuất sửa.
- Nếu thiếu thông tin, ghi rõ nội dung cần bổ sung.
- Không tự ý tạo dữ liệu thay thế.
- Nếu không thể sửa do thiếu dữ liệu, trả về trạng thái CẦN BỔ SUNG.

KẾT QUẢ CUỐI CÙNG:
1. Bảng kế hoạch học tập.
2. Tổng thời gian sử dụng.
3. Danh sách công việc chưa được xếp lịch.
4. Thông tin cần bổ sung (nếu có).
5. Kết luận ngắn gọn.

Chỉ trả về kết quả đã được kiểm tra.
```

## 4. Thiết kế quy trình hoạt động

Chuỗi Prompt được thực hiện theo thứ tự:

**Bước 1:** Kiểm tra dữ liệu.

**Bước 2:** Sắp xếp thứ tự ưu tiên.

**Bước 3:** Lập kế hoạch học tập.

**Bước 4:** Kiểm tra kết quả cuối cùng.

Kết quả của bước trước được chuyển sang bước tiếp theo. Nếu một bước gặp lỗi, hệ thống đánh dấu lỗi và xử lý riêng, không làm dừng toàn bộ quá trình.

### Quy định chuyển dữ liệu giữa các bước

Để tránh AI hiểu nhầm thông tin, tôi sử dụng chung các trường dữ liệu:

-   `task_name`: Tên bài tập.
    
-   `deadline`: Hạn nộp.
    
-   `duration`: Thời gian cần hoàn thành.
    
-   `priority`: Mức độ quan trọng.
    
-   `status`: Trạng thái xử lý.
    

Các bước sau sử dụng lại thông tin này thay vì tự tạo một cách ghi mới.

## 5. Chạy thử hệ thống

### 5.1. Dữ liệu đầu vào

Giả sử sinh viên cung cấp danh sách sau:

STT

Tên bài tập

Hạn nộp

Thời gian cần

1

Lập trình C

20/11/2026

90 phút

2

Tiếng Nhật

2026-11-21

45 phút

3

Báo cáo CNTT

23/11/2026

120 phút

4

Bài tập Excel

22/11/2026

Chưa có

5

Lập trình C

20/11/2026

90 phút

6

Bài tập Python

31/02/2026

60 phút

Thời gian học có sẵn hôm nay: 180 phút.

### 5.2. Kết quả Prompt 1: Kiểm tra dữ liệu

**Danh sách hợp lệ:**

-   Lập trình C – Hạn nộp 20/11/2026 – 90 phút.
    
-   Tiếng Nhật – Hạn nộp 21/11/2026 – 45 phút.
    
-   Báo cáo CNTT – Hạn nộp 23/11/2026 – 120 phút.
    

**Dữ liệu cần xử lý:**

-   Bài tập Excel: Thiếu thời gian cần hoàn thành.
    
-   Lập trình C: Bị trùng, chỉ giữ một bản ghi.
    
-   Bài tập Python: Ngày 31/02/2026 không hợp lệ, cần người dùng sửa lại.
    

### 5.3. Kết quả Prompt 2: Sắp xếp thứ tự ưu tiên

1.  Lập trình C: Hạn nộp 20/11/2026.
    
2.  Tiếng Nhật: Hạn nộp 21/11/2026.
    
3.  Báo cáo CNTT: Hạn nộp 23/11/2026.
    

Bài tập Excel và Python chưa được đưa vào danh sách ưu tiên vì còn thiếu hoặc sai thông tin.

### 5.4. Kết quả Prompt 3: Lập kế hoạch

Thời gian

Công việc

Thời lượng

18:00 – 19:30

Lập trình C

90 phút

19:30 – 20:15

Tiếng Nhật

45 phút

20:15 – 21:00

Báo cáo CNTT

45 phút

Tổng thời gian sử dụng: 180 phút.

Báo cáo CNTT còn 75 phút cần tiếp tục vào ngày hôm sau.

### 5.5. Kết quả Prompt 4: Kiểm tra cuối cùng

**Kết quả kiểm tra:**

-   Không có bài tập hợp lệ nào bị bỏ sót.
    
-   Tổng thời gian sử dụng là 180 phút.
    
-   Không vượt quá thời gian học có sẵn.
    
-   Không có hai công việc bị xếp cùng một khoảng thời gian.
    
-   Bài tập Excel và Python được giữ riêng để chờ bổ sung thông tin.
    
-   Báo cáo CNTT còn 75 phút chưa được xếp lịch.
    

**Kết quả cuối cùng:**

Kế hoạch phù hợp với dữ liệu hợp lệ hiện có. Các bài tập thiếu hoặc sai thông tin đã được đánh dấu để người dùng bổ sung.

## 6. Đánh giá kết quả

### Ưu điểm

-   Công việc được chia thành từng bước rõ ràng.
    
-   Dữ liệu được kiểm tra trước khi sử dụng.
    
-   Hạn chế việc AI tự đoán thông tin.
    
-   Khi một bài tập bị lỗi, các bài tập hợp lệ vẫn được xử lý.
    
-   Có bước kiểm tra cuối cùng trước khi trả kết quả.
    

### Hạn chế

-   Cần viết nhiều Prompt hơn so với cách yêu cầu AI làm một lần.
    
-   Phải chuyển kết quả giữa các bước.
    
-   Nếu dữ liệu đầu vào thiếu nhiều thông tin, người dùng cần bổ sung để có kế hoạch đầy đủ.
    

### Cách tối ưu

-   Mỗi Prompt chỉ thực hiện một nhiệm vụ.
    
-   Không lặp lại những yêu cầu không cần thiết.
    
-   Sử dụng chung một cách ghi dữ liệu giữa các bước.
    
-   Chỉ chuyển những thông tin cần thiết sang bước tiếp theo.
    
-   Chỉ trả về kết quả và lý do chính, không yêu cầu AI giải thích quá dài.
    

