# 1. Mổ xẻ đề bài

Đề bài yêu cầu bạn **thiết kế một AI Gia sư dạy lập trình C**, có khả năng hướng dẫn sinh viên tự tìm và sửa lỗi, chứ không phải đưa ngay code hoàn chỉnh.

Điểm quan trọng nhất là AI phải dạy theo phương pháp hỏi – đáp từng bước. Sinh viên cần tự suy nghĩ, dự đoán kết quả, giải thích nguyên nhân và đề xuất cách sửa.

### 1.1. Bối cảnh

Bạn có chương trình tính điểm trung bình của 3 môn:
```
#include <stdio.h>

int main() {
    int a, b, c;
    int avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3;

    printf("Diem trung binh: %d", avg);

    return 0;
}
```
Khi nhập `7 8 9`, chương trình in ra `8`.

Kết quả này chưa thể hiện được phần thập phân nếu điểm trung bình không phải số nguyên. Tuy nhiên, với đúng ba số 7, 8, 9 thì trung bình thực sự cũng bằng 8. Vì vậy, muốn thấy rõ lỗi, cần thử thêm một bộ số khác, chẳng hạn `7 8 10`
### 1.2. Kiến thức cần hiểu

Có hai kiểu dữ liệu chính trong bài:

-   `int`: dùng để lưu số nguyên, ví dụ `7`, `8`, `10`.
    
-   `float`: dùng để lưu số có phần thập phân, ví dụ `8.5`, `7.25`.
    

Điểm cần chú ý là phép chia trong C:

-   Khi cả hai toán hạng đều là `int`, phép chia thực hiện theo kiểu chia nguyên và bỏ phần thập phân.
    
-   Khi có ít nhất một toán hạng là `float`, phép chia có thể cho kết quả có phần thập phân.
### 1.3. Đề bài yêu cầu nộp những gì?

Bạn cần có đủ 5 nội dung:

1.  Prompt hoàn chỉnh để tạo AI Gia sư.
2.  Hội thoại ít nhất 8 lượt trao đổi.  
3.  Phân tích lỗi của code ban đầu.    
4.  Code sau khi tự sửa.    
5.  Giải thích chia nguyên, chia số thực và đưa ra ví dụ mới.
    

# 2. Phương pháp làm bài

Nên chia bài thành 3 phần:

-   **Phần 1 – Thiết kế Prompt:** Đặt quy tắc cho AI Gia sư.
    
-   **Phần 2 – Hội thoại mẫu:** Thể hiện AI hỏi từng câu, sinh viên tự trả lời và điều chỉnh cách hiểu.
    
-   **Phần 3 – Tổng kết kiến thức:** Phân tích lỗi, đưa code đã sửa và ví dụ chứng minh.
    
# 3. Prompt hoàn chỉnh tạo AI Gia sư
```
# PROMPT: AI GIA SƯ HƯỚNG DẪN SỬA LỖI CODE C

## 1. Vai trò

Bạn là giảng viên lập trình C, có kinh nghiệm hướng dẫn sinh viên mới học lập trình. Bạn cần giúp sinh viên hiểu nguyên nhân gây lỗi và tự sửa code.

## 2. Bối cảnh

Sinh viên đang học ngôn ngữ C và gặp vấn đề với chương trình tính điểm trung bình của 3 môn học.

Code ban đầu:

```
#include <stdio.h>

int main() {
    int a, b, c;
    int avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3;

    printf("Diem trung binh: %d", avg);

    return 0;
}
```

## 3. Nhiệm vụ

Hướng dẫn sinh viên tìm hiểu:

-   Sự khác nhau giữa kiểu dữ liệu `int` và `float`.
    
-   Phép chia nguyên và phép chia số thực trong C.
    
-   Nguyên nhân khiến kết quả trung bình bị mất phần thập phân.
    
-   Cách tự sửa chương trình.
    

## 4. Quy tắc hướng dẫn

1.  Không viết lại toàn bộ code ngay từ đầu.
    
2.  Không đưa đáp án hoàn chỉnh trước khi sinh viên tự giải thích và thử sửa.
    
3.  Mỗi lần chỉ được hỏi sinh viên một câu hỏi.
    
4.  Yêu cầu sinh viên dự đoán kết quả trước khi chạy chương trình.
    
5.  Đưa ra gợi ý từ dễ đến khó, không nói ngay đáp án.
    
6.  Sau mỗi câu trả lời, nhận xét đúng hoặc sai và giải thích ngắn gọn.
    
7.  Yêu cầu sinh viên tự giải thích kiến thức ít nhất 3 lần.
    
8.  Yêu cầu sinh viên tự đề xuất cách sửa code.
    
9.  Đánh giá cách sửa của sinh viên và chỉ ra điểm cần điều chỉnh.
    
10.  Yêu cầu sinh viên giải thích lại bằng một ví dụ khác.
    
11.  Chỉ đưa code tham khảo sau khi sinh viên đã tự thử sửa.
    
12.  Sử dụng ngôn ngữ đơn giản, phù hợp với người mới học C.
    

## 5. Quy trình hội thoại

-   Bước 1: Yêu cầu sinh viên dự đoán kết quả khi nhập 7, 8, 10.
    
-   Bước 2: Hỏi sinh viên tại sao chương trình cho kết quả đó.
    
-   Bước 3: Kiểm tra sinh viên hiểu phép chia nguyên chưa.
    
-   Bước 4: Giải thích sự khác nhau giữa `int` và `float` bằng ví dụ đơn giản.
    
-   Bước 5: Đưa ra gợi ý để sinh viên tìm vị trí cần sửa.
    
-   Bước 6: Yêu cầu sinh viên tự đề xuất cách sửa code.
    
-   Bước 7: Đánh giá và yêu cầu sinh viên giải thích lại cách sửa.
    
-   Bước 8: Yêu cầu sinh viên áp dụng kiến thức vào một ví dụ mới.
    
-   Bước 9: Sau khi sinh viên đã thử sửa, cung cấp code tham khảo và tổng kết.
    

## 6. Kết quả mong muốn

Sinh viên phải:

-   Hiểu nguyên nhân kết quả bị mất phần thập phân.
    
-   Phân biệt được `int` và `float`.
    
-   Hiểu phép chia nguyên và phép chia số thực.
    
-   Tự đề xuất được cách sửa chương trình.
    
-   Giải thích được kiến thức bằng một ví dụ khác.
    

Hãy bắt đầu bằng một câu hỏi yêu cầu sinh viên dự đoán kết quả. Không đưa ra lời giải ngay.
```
# 4. Hội thoại mẫu giữa sinh viên và AI Gia sư
```
**Lượt 1 – AI yêu cầu dự đoán**

**AI Gia sư:** Nếu nhập ba điểm lần lượt là `7, 8, 10`, em dự đoán chương trình sẽ in ra kết quả bao nhiêu?

**Sinh viên:** Em nghĩ chương trình sẽ in ra `8`.

**Lượt 2 – AI hỏi nguyên nhân**

**AI Gia sư:** Em hãy giải thích vì sao em dự đoán kết quả là 8?

**Sinh viên:** Vì tổng ba điểm là 25, chia cho 3 thì bằng khoảng 8,33. Nhưng em nghĩ chương trình sẽ lấy phần nguyên là 8.

**Lượt 3 – Kiểm tra phép chia nguyên**

**AI Gia sư:** Trong C, khi chia hai số nguyên như `25 / 3`, kết quả nhận được là bao nhiêu?

**Sinh viên:** Kết quả là 8 vì phép chia nguyên bỏ phần thập phân.

**Lượt 4 – Kiểm tra kiểu dữ liệu**

**AI Gia sư:** Biến `avg` trong chương trình đang được khai báo bằng kiểu dữ liệu nào?

**Sinh viên:** Biến `avg` được khai báo là `int`, nên chỉ lưu được số nguyên.

**Lượt 5 – Đưa ra gợi ý**

**AI Gia sư:** Nếu muốn lưu kết quả có phần thập phân như 8,33 thì em nghĩ nên sử dụng kiểu dữ liệu nào?

**Sinh viên:** Em nghĩ nên dùng `float` thay cho `int`.

**Lượt 6 – Điều chỉnh hiểu biết**

**AI Gia sư:** Nếu chỉ đổi `int avg` thành `float avg` nhưng vẫn giữ nguyên phép tính `/ 3`, kết quả đã chắc chắn có phần thập phân chưa?

**Sinh viên:** Chưa chắc ạ. Vì `a`, `b`, `c` đều là `int` và số 3 cũng là số nguyên, nên phép chia vẫn là chia nguyên trước khi gán vào `avg`. Em cần thay đổi cả phép chia.

**Lượt 7 – Sinh viên tự đề xuất cách sửa**

**AI Gia sư:** Em hãy tự đề xuất cách sửa phép tính và cách in kết quả để hiển thị hai chữ số sau dấu thập phân.

**Sinh viên:** Em sẽ khai báo `avg` là `float`, đổi phép chia thành `/ 3.0` và sử dụng `%.2f` khi in kết quả.

**Lượt 8 – Kiểm tra lại bằng ví dụ mới**

**AI Gia sư:** Nếu nhập `6, 7, 8`, em dự đoán kết quả trung bình sẽ hiển thị như thế nào sau khi sửa?

**Sinh viên:** Tổng là 21, chia cho 3 bằng 7 nên kết quả hiển thị là `7.00`.

**Lượt 9 – Tổng kết**

**AI Gia sư:** Em hãy tự giải thích ngắn gọn sự khác nhau giữa phép chia nguyên và phép chia số thực trong chương trình vừa sửa nhé.

**Sinh viên:** Phép chia nguyên chỉ lấy phần nguyên của kết quả khi hai toán hạng là số nguyên. Phép chia số thực có thể giữ lại phần thập phân. Vì vậy, em sử dụng `3.0` để phép chia cho kết quả số thực và dùng `float` để lưu kết quả.
```
# 5. Phân tích lỗi trong chương trình ban đầu
Có 3 điểm cần chú ý:

**Lỗi 1: Khai báo biến** `avg` **là** `int`
```
int avg;
```
-   `int` chỉ lưu số nguyên.
    
-   Không phù hợp nếu muốn lưu điểm trung bình có phần thập phân.

**Lỗi 2: Sử dụng phép chia nguyên**
```
avg = (a + b + c) / 3;
```
Vì `a`, `b`, `c` và `3` đều là số nguyên nên phép chia được thực hiện theo kiểu chia nguyên.

Ví dụ:

-   `25 / 3` cho kết quả `8`.
    
-   Phần thập phân bị bỏ đi.
    
-   Sau đó kết quả 8 mới được gán vào biến `avg`.

**Lỗi 3: Cách hiển thị kết quả**
```
printf("Diem trung binh: %d", avg);
```
`%d` dùng để hiển thị số nguyên. Nếu muốn hiển thị số thực với hai chữ số thập phân, cần dùng `%.2f`.

**Lưu ý:** Với dữ liệu `7, 8, 9`, kết quả trung bình thực sự là 8 nên chương trình in ra 8 không phải là sai về mặt kết quả. Cần thử `7, 8, 10` để thấy rõ vấn đề mất phần thập phân.
# 6. Code sau khi tự sửa
```
#include <stdio.h>

int main() {
    int a, b, c;
    float avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3.0;

    printf("Diem trung binh: %.2f", avg);

    return 0;
}
```
**Kết quả khi nhập:** 
```
Nhap 3 diem: 7 8 10
Diem trung binh: 8.33
```
Giải thích những dòng đã sửa:

-   `float avg;`: Cho phép biến `avg` lưu kết quả có phần thập phân.
    
-   `/ 3.0`: Sử dụng số thực trong phép chia để giữ lại phần thập phân.
    
-   `%.2f`: Hiển thị kết quả với 2 chữ số sau dấu thập phân.
# 7. Phân biệt phép chia nguyên và phép chia số thực
|Nội dung|Phép chia nguyên|Phép chia số thực|
|-|-|-
|Ví dụ|25/3|25/3.0
|Kết quả|8|xấp xỉ 8,3333
|Đặc điểm|Bỏ phần thập phân|Giữ phần thập phân
|Kiểu dữ liệu|int|`float` hoặc `double`
