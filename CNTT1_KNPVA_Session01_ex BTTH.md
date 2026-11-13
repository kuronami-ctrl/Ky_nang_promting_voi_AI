# BÀI TẬP TỔNG HỢP: CẨM NANG SỬ DỤNG AI HIỆU QUẢ CHO TÂN SINH VIÊN

## 1. SƠ ĐỒ CÁC BƯỚC XÂU CHUỖI PROMPT (PROMPT CHAINING)

**Prompt Chaining** là phương pháp chia một yêu cầu lớn thành nhiều yêu cầu nhỏ. Sau khi AI hoàn thành từng phần, chúng ta sử dụng kết quả đó để tiếp tục yêu cầu tiếp theo.

**Sơ đồ thực hiện:**

Bước 1: Đưa ra yêu cầu tổng thể
↓
Bước 2: Prompt 1 - Tìm hiểu LLM
↓
Bước 3: Prompt 2 - Nhận diện ảo giác AI
↓
Bước 4: Prompt 3 - Tìm hiểu cấu trúc CREATE
↓
Bước 5: Prompt 4 - Tổng hợp thành cẩm nang
↓
Kết quả: Cuốn cẩm nang hoàn chỉnh

## 2. NỘI DUNG CÁC PROMPT THÀNH PHẦN

### Prompt 1: Tìm hiểu cách AI hoạt động (LLM)

Bạn là giảng viên môn AI Prompting. Hãy giải thích cho sinh viên năm nhất hiểu mô hình LLM hoạt động như thế nào.

Yêu cầu:
- Giải thích AI dự đoán từ tiếp theo như thế nào.
- Giải thích Token là gì bằng ví dụ đơn giản.
- Nêu vai trò của Token khi nhập câu hỏi cho AI.
- Sử dụng ngôn ngữ dễ hiểu, không dùng thuật ngữ phức tạp.
- Có ví dụ liên quan đến việc học lập trình C.

### Prompt 2: Tìm hiểu 3 cách nhận diện ảo giác AI

Dựa trên kiến thức về LLM, hãy trình bày 3 cách giúp sinh viên nhận diện hiện tượng AI tạo ra thông tin sai (ảo giác AI).

Yêu cầu:
- Giải thích ảo giác AI là gì.
- Đưa ra 3 cách kiểm tra câu trả lời của AI.
- Mỗi cách có một ví dụ thực tế liên quan đến học lập trình.
- Trình bày ngắn gọn, dễ hiểu với sinh viên năm nhất.
- Không sử dụng thông tin thiếu căn cứ.

### Prompt 3: Tạo cấu trúc Prompt theo CREATE

Bạn là chuyên gia hướng dẫn sử dụng AI. Hãy giải thích cấu trúc Prompt CREATE và tạo một Prompt mẫu giúp sinh viên năm nhất học lập trình C hiệu quả.

Yêu cầu:
- Giải thích ý nghĩa của 6 thành phần trong CREATE.
- Có ví dụ minh họa cụ thể.
- Prompt mẫu phải yêu cầu AI giải thích code từng dòng, tìm lỗi và đưa ra cách sửa.
- Sử dụng ngôn ngữ đơn giản, dễ hiểu.

### Prompt 4: Tổng hợp thành cẩm nang hoàn chỉnh

Dựa trên kết quả của 3 phần trước, hãy tổng hợp thành một cuốn cẩm nang ngắn có tiêu đề "Cẩm nang sử dụng AI hiệu quả cho tân sinh viên".

Yêu cầu:
- Gồm 3 phần: LLM hoạt động thế nào, 3 cách nhận diện ảo giác AI và cấu trúc Prompt CREATE.
- Nội dung logic, dễ hiểu, có ví dụ thực tế.
- Phù hợp với sinh viên năm nhất ngành Công nghệ thông tin.
- Trình bày ngắn gọn, rõ ràng, không lan man.

---

# 3. CUỐN CẨM NANG KẾT QUẢ HOÀN CHỈNH

# CẨM NANG SỬ DỤNG AI HIỆU QUẢ CHO TÂN SINH VIÊN

**Học lập trình an toàn - Hiểu AI - Sử dụng AI đúng cách**

## PHẦN 1. AI ĐOÁN TỪ NHƯ THẾ NÀO? (LLM)

### 1.1. LLM là gì?

LLM là mô hình AI được huấn luyện bằng một lượng lớn dữ liệu văn bản để có thể hiểu câu hỏi và tạo ra câu trả lời bằng ngôn ngữ tự nhiên.

### 1.2. AI hoạt động như thế nào?

AI hoạt động bằng cách dự đoán từ hoặc phần từ tiếp theo dựa trên nội dung người dùng đã nhập.

Ví dụ:

Khi chúng ta nhập câu: "Ngôn ngữ lập trình C là..."

AI có thể dự đoán những từ tiếp theo như "một ngôn ngữ lập trình phổ biến".

AI tiếp tục dự đoán từng phần để tạo thành câu trả lời hoàn chỉnh.

### 1.3. Token là gì?

Token là những đơn vị nhỏ mà AI sử dụng để xử lý văn bản. Một từ có thể tương ứng với một hoặc nhiều Token.

Ví dụ:

Khi nhập một câu hỏi dài, AI phải xử lý nhiều Token hơn so với một câu hỏi ngắn.

**Lưu ý:**
- Không nên nhập quá nhiều nội dung không cần thiết.
- Hãy đặt câu hỏi rõ ràng, tập trung vào vấn đề cần giải quyết.
- Nên chia câu hỏi dài thành nhiều phần nhỏ để AI dễ xử lý.

## PHẦN 2. BA CÁCH NHẬN DIỆN ẢO GIÁC AI

### 2.1. Ảo giác AI là gì?

Ảo giác AI là hiện tượng AI đưa ra thông tin sai hoặc không có căn cứ nhưng lại trình bày giống như thông tin chính xác.

Sinh viên có thể áp dụng 3 cách sau:

### Cách 1: Kiểm tra thông tin từ nguồn đáng tin cậy

- Không nên tin ngay mọi câu trả lời của AI.
- Đối chiếu với giáo trình, tài liệu học tập hoặc trang web chính thức.

**Ví dụ:** AI đưa ra một lệnh lập trình C. Hãy kiểm tra lại trong tài liệu học hoặc tài liệu chính thức trước khi sử dụng.

### Cách 2: Chạy thử chương trình để kiểm tra

- Không chỉ đọc code do AI tạo ra.
- Hãy chạy thử chương trình trên Dev-C++ hoặc VS Code.
- Kiểm tra xem chương trình có hoạt động đúng yêu cầu không.

**Ví dụ:** AI viết chương trình tính tổng hai số nhưng kết quả hiển thị không đúng. Sinh viên cần kiểm tra lại code và yêu cầu AI giải thích lỗi.

### Cách 3: Yêu cầu AI giải thích và cung cấp căn cứ

- Yêu cầu AI giải thích tại sao lại đưa ra câu trả lời đó.
- Yêu cầu AI chỉ ra phần nào chưa chắc chắn.
- Kiểm tra lại những thông tin quan trọng.

**Ví dụ:** Khi AI đưa ra một hàm trong ngôn ngữ C, hãy yêu cầu giải thích chức năng của hàm và cách sử dụng.

## PHẦN 3. CẤU TRÚC PROMPT MẪU THEO CREATE

### 3.1. CREATE là gì?

CREATE là cấu trúc giúp người dùng viết câu lệnh cho AI đầy đủ, rõ ràng và dễ hiểu hơn. Nhờ đó, AI có thể đưa ra câu trả lời phù hợp với yêu cầu.

### 3.2. Ý nghĩa 6 thành phần trong CREATE

**C - Context (Bối cảnh):**

Cung cấp hoàn cảnh hoặc tình huống để AI hiểu người dùng đang gặp vấn đề gì.

**R - Request (Yêu cầu):**

Nêu rõ công việc mà người dùng muốn AI thực hiện.

**E - Explanation (Giải thích):**

Cung cấp thêm thông tin, dữ liệu hoặc giải thích để AI hiểu rõ yêu cầu.

**A - Action (Hành động):**

Chỉ rõ những bước hoặc công việc AI cần thực hiện.

**T - Tone (Giọng điệu):**

Quy định cách AI diễn đạt câu trả lời, ví dụ: đơn giản, dễ hiểu, nghiêm túc hoặc thân thiện.

**E - Extras (Bổ sung):**

Đưa ra những yêu cầu bổ sung để kết quả phù hợp hơn, ví dụ: giới hạn độ dài, không sử dụng kiến thức nâng cao.

### 3.3. Prompt mẫu CREATE khi học lập trình C

**C - Context (Bối cảnh):**

Tôi là sinh viên năm nhất ngành Công nghệ thông tin, đang học lập trình C và chưa có nhiều kiến thức.

**R - Request (Yêu cầu):**

Hãy giúp tôi viết chương trình tính tổng hai số nguyên a và b.

**E - Explanation (Giải thích):**

Giá trị a = 5, b = 6. Kết quả mong muốn là 11. Tôi muốn hiểu cách sử dụng biến và phép cộng trong C.

**A - Action (Hành động):**

1. Viết chương trình C hoàn chỉnh.
2. Giải thích từng dòng code.
3. Mô phỏng kết quả khi chạy chương trình.
4. Nếu có lỗi, hãy chỉ ra nguyên nhân và cách sửa.

**T - Tone (Giọng điệu):**

Sử dụng ngôn ngữ đơn giản, dễ hiểu, giải thích chậm rãi như đang hướng dẫn người mới học.

**E - Extras (Bổ sung):**

Không sử dụng kiến thức nâng cao. Không bỏ qua bước giải thích. Code phải chạy được trên Dev-C++.

### 3.4. Lợi ích của cấu trúc CREATE

- Giúp AI hiểu rõ bối cảnh và yêu cầu.
- Giúp câu trả lời đầy đủ, đúng trọng tâm.
- Giúp sinh viên dễ hiểu kiến thức mới.
- Tiết kiệm thời gian khi học tập.
- Giúp sinh viên chủ động hơn trong quá trình học lập trình.


