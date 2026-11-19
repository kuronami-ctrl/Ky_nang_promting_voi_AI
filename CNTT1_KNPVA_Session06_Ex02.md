
# BÁO CÁO: SO SÁNH TRADE-OFF CÁC GIẢI PHÁP VIẾT PROMPT

## Bước 1: Đề xuất 2 prompt mẫu

### Giải pháp 1: Prompt đơn giản, ngắn gọn

Bạn hãy giải thích Feynman Prompt gia sư và Rubric chấm bài tự động. Trình bày ngắn gọn, dễ hiểu bằng gạch đầu dòng và nêu tác dụng của từng phương pháp.

### Giải pháp 2: Prompt chi tiết, có nhiều ràng buộc

Bạn là một trợ lý AI hỗ trợ sinh viên học tập và nghiên cứu.

Hãy trình bày nội dung về hai phương pháp sau:
1. Feynman Prompt gia sư.
2. Rubric chấm bài tự động.

Yêu cầu cụ thể:

- Giải thích khái niệm của từng phương pháp bằng ngôn ngữ đơn giản, phù hợp với sinh viên năm nhất.
- Nêu mục đích và tác dụng của từng phương pháp.
- Với Feynman Prompt gia sư: giải thích cách AI đặt câu hỏi, hướng dẫn người học diễn đạt lại kiến thức và phát hiện phần chưa hiểu.
- Với Rubric chấm bài tự động: giải thích cách sử dụng tiêu chí và thang điểm để đánh giá bài làm.
- Trình bày bằng gạch đầu dòng, chia thành từng mục rõ ràng.
- Mỗi phương pháp tối đa 5 gạch đầu dòng.
- Có một ví dụ ngắn minh họa cho mỗi phương pháp.
- Không sử dụng thuật ngữ chuyên ngành khó hiểu nếu không giải thích.
- Không viết lời chào, lời dẫn nhập hoặc lời kết xã giao.
- Không trình bày nội dung ngoài yêu cầu.
- Đảm bảo thông tin chính xác, dễ hiểu và không tự tạo ra số liệu.

## Bước 2: Lập bảng so sánh Trade-off

| Tiêu chí | Giải pháp 1 (Đơn giản) | Giải pháp 2 (Chi tiết) |
|---|---|---|
| Độ dễ hiểu | Cao, dễ viết | Trung bình, cần đọc kỹ |
| Tốn token | Ít | Nhiều hơn |
| Thời gian viết prompt | Nhanh | Lâu hơn |
| Mức độ chi tiết | Cơ bản | Đầy đủ |
| Chặn lỗi biên | Trung bình | Tốt |
| Khả năng kiểm soát định dạng | Trung bình | Cao |
| Phù hợp với yêu cầu phức tạp | Chưa tốt | Tốt |

**Nhận xét:**

- Giải pháp 1 có ưu điểm là ngắn gọn, dễ sử dụng và tiết kiệm token. Tuy nhiên, AI có thể bỏ sót một số nội dung hoặc trình bày chưa đúng mong muốn.
- Giải pháp 2 có ưu điểm là quy định rõ nội dung, định dạng và cách trình bày. Nhược điểm là prompt dài hơn và mất thời gian xây dựng.

## Bước 3: Lựa chọn và chạy thử

### 1. Phương án được lựa chọn

Chọn **Giải pháp 2 (Prompt chi tiết)**.

**Lý do lựa chọn:**

- Nội dung yêu cầu được chia thành từng phần rõ ràng.
- AI biết chính xác cần giải thích những kiến thức nào.
- Có giới hạn số lượng gạch đầu dòng và yêu cầu định dạng.
- Hạn chế tình trạng AI trả lời lan man hoặc bỏ sót nội dung.
- Phù hợp với bài tập cần kết quả đầy đủ để đưa vào báo cáo.

### 2. Kết quả chạy thử

**1. Feynman Prompt gia sư**

- **Khái niệm:** Là cách sử dụng AI để hướng dẫn người học giải thích lại kiến thức bằng ngôn ngữ đơn giản.
- **Mục đích:** Giúp người học hiểu sâu và phát hiện phần kiến thức chưa nắm vững.
- **Cách hoạt động:** AI đặt câu hỏi, yêu cầu người học giải thích và đưa ra gợi ý khi người học gặp khó khăn.
- **Ví dụ:** Khi học về vòng lặp trong C, AI yêu cầu sinh viên giải thích vòng lặp hoạt động như thế nào bằng lời của mình.

**2. Rubric chấm bài tự động**

- **Khái niệm:** Là phương pháp sử dụng bảng tiêu chí và thang điểm để AI hỗ trợ đánh giá bài làm.
- **Mục đích:** Giúp người học biết bài làm đạt yêu cầu ở mức độ nào.
- **Cách hoạt động:** AI dựa vào các tiêu chí đã cung cấp để nhận xét và đánh giá từng phần.
- **Ví dụ:** Khi chấm bài thuyết trình, AI đánh giá theo các tiêu chí như nội dung, cách trình bày, ví dụ và mức độ hoàn thành yêu cầu.

