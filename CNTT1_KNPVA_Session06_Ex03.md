# BÁO CÁO: XÂY DỰNG CHUỖI PROMPT TÍCH HỢP FEYNMAN VÀ RUBRIC CHẤM BÀI TỰ ĐỘNG

## I. BÁO CÁO THIẾT KẾ GIẢI PHÁP

### 1. Mục tiêu

Xây dựng một quy trình sử dụng AI để hỗ trợ sinh viên học tập thông qua hai phương pháp:

- **Feynman Prompt gia sư:** Giúp sinh viên hiểu kiến thức bằng cách tự giải thích lại theo cách đơn giản.
- **Rubric chấm bài tự động:** Sử dụng các tiêu chí có sẵn để đánh giá mức độ hiểu bài của sinh viên.

### 2. Ý tưởng giải quyết

Sử dụng Prompt Chaining để chia bài toán lớn thành 3 bước nhỏ, thực hiện tuần tự:

- **Bước 1 - Kiểm tra dữ liệu:** Kiểm tra chủ đề học tập và câu trả lời của sinh viên.
- **Bước 2 - Gia sư Feynman:** Đánh giá phần giải thích, phát hiện kiến thức chưa chính xác và đưa ra hướng dẫn.
- **Bước 3 - Chấm điểm Rubric:** Dựa trên kết quả bước 2 để đánh giá theo tiêu chí và đưa ra nhận xét cuối cùng.

### 3. Sơ đồ hoạt động

Sinh viên nhập thông tin
        |
        v
Bước 1: Kiểm tra dữ liệu
        |
        v
Bước 2: Gia sư Feynman
        |
        v
Bước 3: Chấm điểm Rubric
        |
        v
Xuất kết quả cuối cùng

---

## II. PROMPT THỰC THI CÁC BƯỚC

### 1. Prompt 1: Kiểm tra dữ liệu đầu vào

**Vai trò:** Trợ lý kiểm tra thông tin học tập.

**Prompt:**

Bạn là trợ lý kiểm tra dữ liệu học tập.

Hãy kiểm tra các thông tin sau:
- Chủ đề học tập.
- Phần giải thích của sinh viên.

Yêu cầu:
- Nếu thiếu chủ đề hoặc câu trả lời, thông báo thông tin cần bổ sung.
- Nếu dữ liệu không đúng định dạng, yêu cầu nhập lại.
- Nếu dữ liệu hợp lệ, xác nhận và chuyển sang bước tiếp theo.
- Không tự ý bổ sung dữ liệu còn thiếu.
- Không dừng toàn bộ quy trình chỉ vì một dữ liệu không hợp lệ.

**Đầu ra:** Dữ liệu hợp lệ hoặc thông báo lỗi cụ thể.

### 2. Prompt 2: Gia sư Feynman

**Vai trò:** Gia sư AI sử dụng phương pháp Feynman.

**Prompt:**

Bạn là gia sư AI áp dụng phương pháp Feynman.

Dựa trên chủ đề và câu trả lời đã được kiểm tra ở bước 1, hãy thực hiện:

- Đánh giá sinh viên đã hiểu chủ đề đến đâu.
- Chỉ ra nội dung đúng và nội dung chưa chính xác.
- Giải thích lại những phần sinh viên chưa hiểu bằng ngôn ngữ đơn giản.
- Đưa ra một câu hỏi ngắn để sinh viên tự kiểm tra kiến thức.

Yêu cầu:
- Không sử dụng thuật ngữ khó hiểu nếu không giải thích.
- Không tự tạo thông tin không có căn cứ.
- Trình bày ngắn gọn bằng gạch đầu dòng.

**Đầu ra:** Bản nhận xét và hướng dẫn học tập.

### 3. Prompt 3: Chấm điểm bằng Rubric

**Vai trò:** Người đánh giá bài học tự động.

**Prompt:**

Bạn là trợ lý AI chấm bài theo Rubric.

Dựa trên kết quả ở bước 2, hãy đánh giá sinh viên theo 4 tiêu chí:

1. Hiểu đúng kiến thức: 4 điểm.
2. Giải thích rõ ràng: 2 điểm.
3. Sử dụng ví dụ phù hợp: 2 điểm.
4. Khả năng diễn đạt bằng ngôn ngữ đơn giản: 2 điểm.

Yêu cầu:
- Chấm điểm từng tiêu chí.
- Tổng điểm tối đa là 10.
- Giải thích ngắn gọn lý do cho từng điểm.
- Không tự cộng điểm khi thiếu bằng chứng.
- Nếu không có đủ dữ liệu, ghi rõ chưa thể đánh giá.
- Đưa ra nhận xét và đề xuất cải thiện.

**Đầu ra:** Bảng điểm và nhận xét cuối cùng.

---

## III. CƠ CHẾ XỬ LÝ LỖI DỮ LIỆU

Để tránh AI đưa ra kết quả sai khi dữ liệu đầu vào có vấn đề, thiết lập các quy tắc:

| Trường hợp | Cách xử lý |
|---|---|
| Thiếu chủ đề | Yêu cầu sinh viên bổ sung |
| Không có câu trả lời | Yêu cầu nhập nội dung |
| Câu trả lời quá ngắn | Yêu cầu bổ sung thông tin |
| Sai định dạng | Thông báo và hướng dẫn nhập lại |
| Thiếu dữ liệu chấm điểm | Ghi rõ tiêu chí chưa đủ căn cứ đánh giá |
| Dữ liệu không hợp lệ | Không chuyển dữ liệu lỗi sang bước tiếp theo |

**Nguyên tắc:** Mỗi bước chỉ tiếp nhận dữ liệu hợp lệ từ bước trước. Nếu có lỗi, thông báo cụ thể và cho phép người dùng sửa lại thay vì tự đoán dữ liệu.

---

## IV. KẾT QUẢ CHẠY THỬ

### 1. Dữ liệu đầu vào

- Chủ đề: Vòng lặp trong ngôn ngữ lập trình C.
- Câu trả lời của sinh viên:

"Vòng lặp là một cấu trúc trong lập trình giúp chương trình thực hiện một công việc nhiều lần. Trong C có vòng lặp for, while và do while."

### 2. Kết quả bước 1: Kiểm tra dữ liệu

- Chủ đề: Đã cung cấp.
- Câu trả lời: Đã cung cấp.
- Định dạng: Hợp lệ.
- Kết luận: Đủ điều kiện chuyển sang bước 2.

### 3. Kết quả bước 2: Gia sư Feynman

**Nội dung đã hiểu đúng:**
- Sinh viên hiểu vòng lặp dùng để thực hiện một công việc nhiều lần.
- Nhận biết được ba loại vòng lặp cơ bản trong C.

**Nội dung cần bổ sung:**
- Chưa giải thích cách hoạt động của từng loại vòng lặp.
- Chưa nêu điều kiện để vòng lặp tiếp tục hoặc kết thúc.

**Giải thích đơn giản:**

Vòng lặp giống như việc lặp lại một hành động nhiều lần. Ví dụ, muốn in các số từ 1 đến 5, chúng ta có thể sử dụng vòng lặp thay vì viết năm lệnh in riêng biệt.

**Câu hỏi kiểm tra:**

Vòng lặp `for` trong C sẽ dừng khi nào?

### 4. Kết quả bước 3: Chấm điểm Rubric

| Tiêu chí | Điểm tối đa | Điểm đạt |
|---|---:|---:|
| Hiểu đúng kiến thức | 4 | 4 |
| Giải thích rõ ràng | 2 | 1 |
| Sử dụng ví dụ phù hợp | 2 | 0 |
| Diễn đạt đơn giản | 2 | 2 |
| **Tổng điểm** | **10** | **7** |

**Nhận xét:**

- Sinh viên đã hiểu khái niệm cơ bản về vòng lặp.
- Cách diễn đạt tương đối rõ ràng và dễ hiểu.
- Chưa có ví dụ minh họa và chưa giải thích cách hoạt động của từng loại vòng lặp.

**Đề xuất cải thiện:**

Sinh viên nên bổ sung ví dụ thực tế và giải thích điều kiện bắt đầu, tiếp tục và kết thúc của vòng lặp.

---

