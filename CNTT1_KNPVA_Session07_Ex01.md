# PHÂN TÍCH ĐỀ BÀI: TỔNG HỢP KẾT QUẢ HỌC TẬP 30 SINH VIÊN JAVA CƠ BẢN

Trước tiên, cần hiểu rằng đây không đơn thuần là bài tập tính điểm. Đề bài yêu cầu bạn sử dụng AI để **đọc nhiều tài liệu khác nhau, kiểm tra dữ liệu, ghép thông tin chính xác và tạo ra một báo cáo kết quả học tập hoàn chỉnh.**
## I. MỔ XẺ ĐỀ BÀI

### 1. Bối cảnh: 

Bạn đóng vai trò là trợ lý đào tạo tại Trung tâm CNTT.

Trung tâm có một lớp gồm 30 sinh viên đã học xong môn Java cơ bản. Bạn được giao nhiệm vụ tổng hợp điểm và đánh giá kết quả học tập của cả lớp.
Bạn nhận được 4 file dữ liệu:
|file|nội dung|
|-|-
|file 1|danh sách sinh viên và mã sinh viên
|file 2|điểm chuyên cần và bài tập
|file 3|điểm giữa kì
|file 4|điểm cuối kì và nhận xét giảng viên
**Điểm khó của bài toán:**

-   Mỗi file có cách trình bày khác nhau. 
-   Có thể có thông tin bị lặp.    
-   Có sinh viên trùng họ tên.
  -   Có trường hợp bị thiếu điểm.
-   Cần đảm bảo không ghép nhầm điểm của sinh viên này sang sinh viên khác.
### 2. Vấn đề:

Có 4 vấn đề chính:

**Vấn đề 1: Dữ liệu nằm rải rác**

Thông tin của một sinh viên không nằm trong cùng một file. Bạn phải tổng hợp từ cả 4 file.

**Vấn đề 2: Nguy cơ ghép nhầm sinh viên**

Hai sinh viên có thể trùng họ tên nhưng mã sinh viên khác nhau.

Vì vậy, phải sử dụng mã sinh viên để xác định chính xác từng người.

**Vấn đề 3: Dữ liệu có thể bị thiếu hoặc trùng**

Ví dụ:

-   Một sinh viên không có điểm giữa kỳ.
    
-   Một sinh viên xuất hiện hai lần trong danh sách.
    
-   Một sinh viên có hai kết quả điểm cuối kỳ khác nhau.
    

Bạn phải phát hiện và báo lại, không tự ý sửa hoặc đoán.

**Vấn đề 4: Cần tính toán và đánh giá**

Sau khi dữ liệu đã được kiểm tra, bạn cần tính điểm tổng kết, phân loại đạt hoặc chưa đạt và thống kê kết quả toàn lớp.

### 3. Yêu cầu: 

Đề yêu cầu 6 sản phẩm:
1.  Prompt đọc và xử lý từng file.
2.  Prompt đối chiếu dữ liệu giữa các file.    
3.  Bảng tổng hợp kết quả của 30 sinh viên.    
4.  Báo cáo tỷ lệ đạt và chưa đạt.    
5.  Danh sách các trường hợp bất thường.    
6.  Báo cáo nhận xét tình hình học tập khoảng 500 từ.
    
## II. PHƯƠNG PHÁP LÀM BÀI
### Bước 1: Đọc và xử lý từng file riêng biệt

**Mục đích:** Lấy thông tin từ 4 file và chuyển thành các bảng có cấu trúc giống nhau.
Cần viết 4 prompt riêng:

**PROMPT 1 – ĐỌC FILE 1**
```
Bạn là trợ lý xử lý dữ liệu sinh viên.

Hãy đọc File 1 và trích xuất:
- Mã sinh viên.
- Họ tên.

Yêu cầu:
- Trình bày thành bảng.
- Giữ nguyên thông tin trong file.
- Không tự sửa hoặc tạo dữ liệu.
- Phát hiện mã sinh viên bị trùng hoặc bị thiếu.
- Báo lại những trường hợp bất thường.
```
**PROMPT 2 – ĐỌC FILE 2**
```
Hãy đọc File 2 và trích xuất:
- Mã sinh viên.
- Điểm chuyên cần.
- Điểm bài tập.

Yêu cầu:
- Trình bày thành bảng.
- Điểm phải nằm trong khoảng 0–10.
- Không tự điền điểm còn thiếu.
- Phát hiện mã sinh viên bị trùng.
- Giữ nguyên dữ liệu gốc.
```
**PROMPT 3 – ĐỌC FILE 3**
```
Hãy đọc File 3 và trích xuất:
- Mã sinh viên.
- Điểm giữa kỳ.

Yêu cầu:
- Trình bày thành bảng.
- Điểm phải nằm trong khoảng 0–10.
- Không tự điền điểm còn thiếu.
- Phát hiện dữ liệu trùng hoặc không hợp lệ.
- Giữ nguyên dữ liệu gốc.
```
**PROMPT 4 – ĐỌC FILE 4**
```
Hãy đọc File 4 và trích xuất:
- Mã sinh viên.
- Điểm cuối kỳ.
- Nhận xét của giảng viên.

Yêu cầu:
- Trình bày thành bảng.
- Điểm phải nằm trong khoảng 0–10.
- Không tự điền điểm còn thiếu.
- Phát hiện dữ liệu trùng hoặc không hợp lệ.
- Giữ nguyên nhận xét của giảng viên.
```
**Kết quả cần đạt:** Có 4 bảng dữ liệu riêng biệt, mỗi bảng chứa đúng thông tin của file tương ứng.
### Bước 2: Đối chiếu dữ liệu giữa 4 file

**Mục đích:** Ghép thông tin của cùng một sinh viên từ 4 file thành một bảng chung.

Đây là bước quan trọng nhất vì nếu ghép nhầm sinh viên thì toàn bộ kết quả tính điểm có thể sai.

Prompt thực hiện:
```
Bạn là trợ lý tổng hợp dữ liệu học tập.

Hãy đối chiếu 4 bảng dữ liệu đã trích xuất.

Yêu cầu:
1. Sử dụng mã sinh viên làm căn cứ ghép dữ liệu.
2. Không ghép chỉ dựa vào họ tên.
3. Lấy danh sách File 1 làm danh sách sinh viên chính.
4. Ghép điểm chuyên cần, bài tập, giữa kỳ và cuối kỳ tương ứng.
5. Phát hiện sinh viên thiếu điểm.
6. Phát hiện mã sinh viên bị trùng giữa các file.
7. Nếu một mã sinh viên có hai kết quả khác nhau, đánh dấu "Dữ liệu trùng cần xác minh".
8. Nếu dữ liệu thiếu, ghi "Thiếu dữ liệu".
9. Không tự sửa, đoán hoặc bổ sung điểm.

Đầu ra:
- Bảng dữ liệu đã đối chiếu.
- Danh sách sinh viên thiếu dữ liệu.
- Danh sách dữ liệu trùng hoặc không hợp lệ.
- Danh sách mã sinh viên xuất hiện ngoài File 1.
```
**Kết quả cần đạt:** Một bảng chung có đủ thông tin của từng sinh viên và danh sách các trường hợp cần kiểm tra.
### Bước 3: Tính điểm tổng kết và phân loại

**Mục đích:** Sau khi dữ liệu được kiểm tra, AI mới thực hiện tính điểm.

Prompt thực hiện:
```
Bạn là trợ lý tính điểm học tập.

Dựa trên bảng dữ liệu đã đối chiếu, hãy tính điểm tổng kết theo công thức:

Tổng kết =
Chuyên cần × 10%
+ Bài tập × 20%
+ Giữa kỳ × 30%
+ Cuối kỳ × 40%

Quy định:
- Chỉ tính điểm khi có đủ 4 đầu điểm hợp lệ.
- Nếu thiếu điểm, ghi "Thiếu dữ liệu".
- Nếu có dữ liệu trùng chưa được xác minh, không tính điểm cho trường hợp đó.
- Điểm tổng kết làm tròn đến 1 chữ số thập phân.
- Từ 5,0 trở lên: Đạt.
- Dưới 5,0: Chưa đạt.
- Không tự suy đoán nguyên nhân điểm thấp.

Đầu ra gồm:
Mã SV | Họ tên | Chuyên cần | Bài tập |
Giữa kỳ | Cuối kỳ | Tổng kết | Kết quả|
```
**Kết quả cần đạt:** Bảng tổng hợp kết quả học tập của 30 sinh viên.
### Bước 4: Thống kê và phát hiện bất thường

**Mục đích:** Biết tình hình chung của lớp và phát hiện các trường hợp cần xử lý.

Prompt thực hiện:
```
Dựa trên bảng kết quả đã tính, hãy lập báo cáo thống kê.

Yêu cầu:
1. Tổng số sinh viên trong danh sách.
2. Số sinh viên đạt học phần.
3. Số sinh viên chưa đạt.
4. Số sinh viên thiếu dữ liệu hoặc chưa thể kết luận.
5. Tính tỷ lệ đạt và chưa đạt trên tổng số sinh viên đủ điều kiện phân loại.
6. Liệt kê sinh viên có dữ liệu trùng, thiếu hoặc không hợp lệ.
7. Không tự suy đoán nguyên nhân điểm thấp.

Trình bày bằng bảng và gạch đầu dòng.
Không tự tạo số liệu nếu dữ liệu chưa đủ.
```
**Kết quả cần đạt:** Có số lượng, tỷ lệ đạt, chưa đạt và danh sách các trường hợp bất thường.
### **Bước 5: Viết báo cáo nhận xét khoảng 500 từ**

**Mục đích:** Dựa trên số liệu thực tế để nhận xét tình hình học tập của cả lớp.

Prompt thực hiện:
```
Bạn là trợ lý đào tạo tại Trung tâm CNTT.

Dựa trên bảng điểm và báo cáo thống kê đã có,
hãy viết báo cáo nhận xét tình hình học tập
của lớp Java cơ bản.

Yêu cầu:
- Độ dài khoảng 500 từ.
- Nhận xét kết quả học tập chung.
- Phân tích tỷ lệ đạt và chưa đạt.
- Nhận xét kết quả các đầu điểm nếu dữ liệu cho phép.
- Nêu các trường hợp thiếu hoặc bất thường.
- Đưa ra đề xuất cải thiện việc học tập.
- Chỉ sử dụng thông tin có trong dữ liệu.
- Không tự suy đoán nguyên nhân sinh viên có điểm thấp.
- Không tự tạo số liệu.
- Trình bày rõ ràng, ngôn ngữ dễ hiểu.
```
## III. CÁCH XỬ LÝ CÁC TRƯỜNG HỢP BẤT THƯỜNG
|Trường hợp|Cách xử lí|
|-|-
|Hai sinh viên trùng tên|Dùng mã sv để phân biệt
|Thiếu điểm giữa kì|Ghi "Thiếu dữ liệu"
|Điểm lớn hơn 10|Đánh dấu điểm không hợp lệ
|Điểm nhỏ hơn 10|Đánh dấu điểm không hợp lệ
|Một mã SV xuất hiện nhiều lần|Báo dữ liệu trùng
|Hai dòng trùng mã nhưng khác điểm|Chờ xác minh, không tự chọn
|Mã SV không có trong File 1|Đưa vào danh sách cần kiểm tra
|Thiếu nhận xét giảng viên|Ghi thiếu nhận xét, không tự viết thay
