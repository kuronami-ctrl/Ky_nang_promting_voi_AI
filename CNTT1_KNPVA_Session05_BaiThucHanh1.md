# LẬP KẾ HOẠCH TÀI CHÍNH CÁ NHÂN BẰNG CHAIN-OF-THOUGHT

## 1. Phân tích yêu cầu đề bài

**Mục tiêu:**

Thiết kế một Prompt để AI hỗ trợ lập kế hoạch tài chính cá nhân hàng tháng, giúp người dùng quản lý thu nhập, chi tiêu, trả nợ và tiết kiệm hợp lý.

**Các dữ liệu đầu vào cần có:**

- Thu nhập hàng tháng.
- Thuế và các khoản khấu trừ.
- Chi phí cố định.
- Các khoản nợ cần thanh toán.
- Mục tiêu tiết kiệm.

**Các yêu cầu cần giải quyết:**

- Tính số tiền còn lại sau khi trừ thuế và chi phí cố định.
- Xác định số tiền cần trả nợ.
- Dành ít nhất 20% thu nhập sau thuế để tiết kiệm.
- Phân bổ số tiền còn lại cho các khoản chi tiêu.
- Kiểm tra tổng số tiền và tỷ lệ phần trăm để tránh sai sót.

## 2. Lựa chọn phương pháp và giải thích

**Phương pháp lựa chọn: Chain-of-Thought (CoT).**

CoT là kỹ thuật yêu cầu AI chia một vấn đề lớn thành nhiều bước nhỏ để xử lý lần lượt.

**Lý do lựa chọn:**

Bài toán tài chính có nhiều phép tính cộng, trừ, nhân, chia và nhiều điều kiện cần đáp ứng. Nếu yêu cầu AI đưa ra kết quả ngay, có thể xảy ra sai sót hoặc phân bổ ngân sách không hợp lý.

Vì vậy, em chọn CoT vì:

- Giúp AI xử lý bài toán theo từng bước rõ ràng.
- Dễ kiểm tra các phép tính trung gian.
- Hạn chế bỏ sót các khoản chi tiêu và trả nợ.
- Giúp kết quả cuối cùng hợp lý và dễ theo dõi.

## 3. Tạo Prompt giải quyết bài toán

**Prompt sử dụng:**

```text
Bạn là một trợ lý tư vấn tài chính cá nhân.

Nhiệm vụ: Hãy giúp người dùng lập kế hoạch tài chính
hàng tháng dựa trên các thông tin được cung cấp.

Dữ liệu đầu vào:
- Thu nhập hàng tháng:
- Thuế và các khoản khấu trừ:
- Chi phí cố định:
- Các khoản nợ cần thanh toán:
- Mục tiêu tiết kiệm:

Yêu cầu thực hiện:

Hãy suy nghĩ từng bước một và tính toán chi tiết
trước khi đưa ra quyết định.

Thực hiện theo 4 bước:

Bước 1: Tính thu nhập sau thuế và trừ các chi phí
cố định để xác định số tiền còn lại.

Bước 2: Tính tổng số tiền cần trả nợ tối thiểu
và đảm bảo thanh toán đúng hạn.

Bước 3: Trích ít nhất 20% thu nhập sau thuế
để đưa vào khoản tiết kiệm.

Bước 4: Phân bổ số tiền còn lại cho các khoản:
- Nhu cầu thiết yếu.
- Chi tiêu cá nhân.
- Quỹ dự phòng.

Quy tắc:
- Ghi rõ công thức và kết quả của từng phép tính.
- Không tự ý tạo thêm dữ liệu.
- Nếu thiếu thông tin, hãy hỏi lại người dùng.
- Không phân bổ vượt quá số tiền hiện có.
- Kiểm tra tổng ngân sách và tỷ lệ phần trăm.
- Tổng tỷ lệ phân bổ phải bằng 100%.

Định dạng kết quả:

Phần 1: Các bước tính toán.
Trình bày công thức và kết quả của từng bước.

Phần 2: Bảng phân bổ ngân sách.

Sử dụng bảng Markdown gồm các cột:
| Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |

Phần 3: Kiểm tra kết quả.
- Tổng số tiền đã phân bổ.
- Tổng tỷ lệ phần trăm.
- Số tiền còn lại.
- Đánh giá kế hoạch có hợp lý hay không.

Yêu cầu trình bày:
Sử dụng ngôn ngữ đơn giản, dễ hiểu,
ngắn gọn và rõ ràng.
```

## 4. Dữ liệu dùng để kiểm thử Prompt

Giả sử người dùng có tình hình tài chính như sau:

-   Thu nhập hàng tháng: 15.000.000 đồng.    
-   Thuế và các khoản khấu trừ: 1.000.000 đồng.    
-   Chi phí cố định: 4.000.000 đồng.    
-   Khoản nợ phải trả tối thiểu: 2.000.000 đồng.    
-   Mục tiêu tiết kiệm: 20% thu nhập sau thuế.


### Phần 1: Các bước tính toán

#### Bước 1: Tính thu nhập sau thuế và trừ các chi phí cố định
* **Công thức:**
  * $\text{Thu nhập sau thuế} = \text{Thu nhập hàng tháng} - \text{Thuế và các khoản khấu trừ}$
  * $\text{Số tiền còn lại sau chi phí cố định} = \text{Thu nhập sau thuế} - \text{Chi phí cố định}$
* **Tính toán:**
  * Thu nhập sau thuế: $15.000.000 - 1.000.000 = 14.000.000 \text{ đồng}$
  * Số tiền còn lại sau khi trừ chi phí cố định: $14.000.000 - 4.000.000 = 10.000.000 \text{ đồng}$

#### Bước 2: Tính số tiền trả nợ tối thiểu
* **Công thức:** Trả toàn bộ số tiền nợ tối thiểu theo yêu cầu để đảm bảo thanh toán đúng hạn.
* **Tính toán:** $2.000.000 \text{ đồng}$
* **Số tiền còn lại sau khi trả nợ:** $10.000.000 - 2.000.000 = 8.000.000 \text{ đồng}$

#### Bước 3: Trích tiền tiết kiệm
* **Công thức:**
  * $\text{Tiết kiệm} = \text{Thu nhập sau thuế} \times 20\%$
* **Tính toán:** $14.000.000 \times 20\% = 2.800.000 \text{ đồng}$
* **Số tiền còn lại sau khi tiết kiệm:** $8.000.000 - 2.800.000 = 5.200.000 \text{ đồng}$

#### Bước 4: Phân bổ số tiền còn lại (5.200.000 đồng)
Số tiền còn lại được phân bổ hợp lý cho 3 khoản:
* **Nhu cầu thiết yếu (ăn uống, đi lại, sinh hoạt):** $3.200.000 \text{ đồng}$ (tương đương khoảng $22,86\%$ thu nhập sau thuế).
* **Chi tiêu cá nhân (giải trí, mua sắm):** $1.000.000 \text{ đồng}$ (tương đương khoảng $7,14\%$ thu nhập sau thuế).
* **Quỹ dự phòng (phòng rủi ro, phát sinh):** $1.000.000 \text{ đồng}$ (tương đương khoảng $7,14\%$ thu nhập sau thuế).

---

### Phần 2: Bảng phân bổ ngân sách

| Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |
| :--- | :--- | :--- | :--- |
| **Thuế và khấu trừ** | 1.000.000 đ | 6,67% | Trừ trực tiếp từ tổng thu nhập |
| **Chi phí cố định** | 4.000.000 đ | 26,67% | Nhà ở, điện, nước, internet... |
| **Trả nợ tối thiểu** | 2.000.000 đ | 13,33% | Đảm bảo thanh toán đúng hạn |
| **Tiết kiệm** | 2.800.000 đ | 18,67% | 20% trên thu nhập sau thuế (14 triệu) |
| **Nhu cầu thiết yếu** | 3.200.000 đ | 21,33% | Ăn uống, đi lại, sinh hoạt hằng ngày |
| **Chi tiêu cá nhân** | 1.000.000 đ | 6,67% | Giải trí, cá nhân khác |
| **Quỹ dự phòng** | 1.000.000 đ | 6,67% | Quỹ khẩn cấp, phát sinh |
| **Tổng cộng** | **15.000.000 đ** | **100,00%** | **Khớp 100% tổng thu nhập** |

---

### Phần 3: Kiểm tra kết quả

* **Tổng số tiền đã phân bổ:** 15.000.000 đồng (Khớp hoàn toàn với tổng thu nhập ban đầu).
* **Tổng tỷ lệ phần trăm:** 100,00%.
* **Số tiền còn lại:** 0 đồng (Ngân sách đã được phân bổ trọn vẹn, không có thâm hụt hay dư thừa chưa phân bổ).
* **Đánh giá kế hoạch:** Kế hoạch hoàn toàn hợp lý. Bạn đã hoàn thành nghĩa vụ tài chính (thuế, nợ), đạt được mục tiêu tiết kiệm đúng 20% trên thu nhập sau thuế, đồng thời vẫn đảm bảo nguồn lực cho sinh hoạt thiết yếu và quỹ dự phòng.

**Kết luận:**

Em lựa chọn kỹ thuật Chain-of-Thought vì bài toán có nhiều bước tính toán và yêu cầu phân bổ ngân sách cụ thể. Việc thiết kế Prompt theo từng bước giúp AI xử lý vấn đề rõ ràng hơn, dễ kiểm tra kết quả và hạn chế sai sót khi lập kế hoạch tài chính.
