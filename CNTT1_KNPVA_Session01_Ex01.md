# BÀI TẬP: NHẬN DIỆN BẢN CHẤT HOẠT ĐỘNG CỦA LLM

## PHẦN 1. BÓC TÁCH NHẬN THỨC SAI CỦA NAM

Trong báo cáo, Nam đã mắc 2 sai lầm khi hiểu về cách hoạt động của ChatGPT.

### Sai lầm 1: Cho rằng ChatGPT bị hỏng phần mềm hoặc máy chủ bị lỗi tính toán

**Giải thích:**

- ChatGPT hoạt động dựa trên cơ chế Next Token Prediction (dự đoán Token tiếp theo).
- Điều này có nghĩa là AI dự đoán từ hoặc phần từ tiếp theo dựa trên nội dung đã có để tạo thành câu trả lời.
- AI không hoạt động giống như máy tính bỏ túi có sẵn thuật toán chuyên dùng để thực hiện phép cộng.

**Áp dụng vào tình huống:**

Khi Nam nhập phép tính 15.480 + 28.750, ChatGPT có thể tạo ra kết quả sai vì mô hình dự đoán câu trả lời dựa trên xác suất và dữ liệu đã học, chứ không nhất thiết thực hiện phép cộng bằng công cụ tính toán.

Vì vậy, kết quả sai không có nghĩa là phần mềm hoặc máy chủ bị hỏng.

### Sai lầm 2: Cho rằng AI có hàng trăm tỷ tham số thì chắc chắn tính toán chính xác 100%

**Giải thích:**

- Pre-training là quá trình AI được huấn luyện trước bằng một lượng lớn dữ liệu văn bản.
- Trong quá trình này, AI học cách nhận biết các mẫu ngôn ngữ và mối liên hệ giữa các từ.
- Số lượng tham số lớn giúp mô hình có khả năng xử lý thông tin phức tạp hơn, nhưng không đảm bảo AI luôn tính toán chính xác.

**Áp dụng vào tình huống:**

Dù ChatGPT có rất nhiều tham số, mô hình vẫn có thể nhầm lẫn khi thực hiện phép tính số học.

Điều này cho thấy LLM là mô hình dự đoán ngôn ngữ dựa trên xác suất, không phải máy tính chuyên dụng để thực hiện mọi phép tính chính xác.

**Kết luận phần 1:**

Nam đã nhầm lẫn giữa AI tạo câu trả lời bằng cách dự đoán xác suất với máy tính thực hiện phép tính theo thuật toán. Vì vậy, không thể khẳng định ChatGPT bị hỏng chỉ vì đưa ra một phép cộng sai.

---

## PHẦN 2. SỬA LỖI VÀ ĐỀ XUẤT PROMPT

### 2.1. Cách sửa lỗi

Để hạn chế sai sót khi thực hiện phép tính, chúng ta nên yêu cầu ChatGPT sử dụng công cụ hỗ trợ tính toán như Python hoặc Code Interpreter.

Thay vì chỉ yêu cầu AI trả lời kết quả, hãy yêu cầu AI sử dụng công cụ tính toán và kiểm tra lại kết quả.

### 2.2. Prompt mẫu đề xuất

**Prompt sử dụng Python / Code Interpreter:**

Bạn là trợ lý hỗ trợ tính toán cho nhân viên dữ liệu.

Tôi cần tính phép cộng sau:

15.480 + 28.750

Yêu cầu:
1. Sử dụng công cụ Python hoặc Code Interpreter để thực hiện phép tính, không chỉ dự đoán kết quả bằng ngôn ngữ.
2. Hiển thị phép tính cụ thể.
3. Kiểm tra lại kết quả bằng một cách tính khác.
4. Đưa ra kết quả cuối cùng rõ ràng, chính xác.

### 2.3. Kết quả tính toán

Ta có:

15.480 + 28.750 = 44.230

Kiểm tra lại:

15.480 + 28.000 = 43.480

43.480 + 750 = 44.230

Vậy kết quả chính xác là **44.230**.

### 2.4. Lưu ý khi sử dụng AI

- Không nên coi ChatGPT là máy tính bỏ túi.
- Không nên tin tuyệt đối vào kết quả tính toán do AI đưa ra.
- Nên sử dụng Python, Code Interpreter hoặc máy tính chuyên dụng khi cần tính toán chính xác.
- Luôn kiểm tra lại kết quả trước khi sử dụng trong công việc.


