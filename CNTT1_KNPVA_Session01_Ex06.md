## Phần 1: Giải thích hình tượng Chiếc cốc nước

1. Context Window là gì?

Context Window (cửa sổ ngữ cảnh) có thể hiểu đơn giản là dung lượng chứa thông tin mà AI có thể sử dụng trong một phiên hội thoại.

Hãy tưởng tượng Context Window giống như một chiếc cốc nước:

-   Chiếc cốc: Là dung lượng bộ nhớ giới hạn của AI.
    
-   Nước trong cốc: Là nội dung tin nhắn của khách hàng và câu trả lời của AI.
    
-   Rót thêm nước: Mỗi lượt trò chuyện mới sẽ bổ sung thêm thông tin vào bộ nhớ.
    
-   Cốc đầy: Khi lượng thông tin vượt quá giới hạn, AI không thể giữ toàn bộ nội dung cũ trong Context Window.
    

2. Vì sao AI quên thông tin ở Lượt 1?

Trong tình huống MartX, nhân viên và khách hàng đã trò chuyện liên tục 45 lượt. Các câu trả lời dài về rau củ khiến lượng thông tin tích lũy tăng lên đến 32.000 Tokens.

Khi Context Window gần đạt giới hạn, hệ thống có thể phải loại bỏ một phần nội dung cũ để tiếp nhận thông tin mới. Hiện tượng này gọi là Truncation (cắt gọt dữ liệu).

Vì vậy, thông tin ở Lượt 1 như tên khách hàng Trần Văn B và mã đơn hàng #MTX-9988 có thể bị loại khỏi phần ngữ cảnh AI còn sử dụng được.

Khi khách hàng hỏi tiếp ở Lượt 42, AI không còn thấy thông tin cũ nên nhầm tên khách hàng và yêu cầu cung cấp lại mã đơn hàng.

Kết luận: AI không có trí nhớ vô hạn. Việc quên thông tin không nhất thiết là do hệ thống bị lỗi mà có thể do Context Window đã đầy và nội dung cũ bị cắt bỏ.

## Phần 2: Phương án quản lý RAM bộ nhớ

Phương án 1: Thao tác từ phía người dùng (Nhân viên CSKH)

-   Hạn chế trò chuyện lan man, tránh để AI trả lời quá dài.
    
-   Khi kết thúc một nội dung tư vấn, yêu cầu AI tóm tắt các thông tin quan trọng.
    
-   Lưu lại thông tin khách hàng như tên, mã đơn hàng, sản phẩm và yêu cầu hỗ trợ.
    
-   Khi cần thiết, gửi lại bản tóm tắt để AI tiếp tục tư vấn chính xác.
    

Ví dụ:

`Hãy ghi nhớ trong phần ngữ cảnh hiện tại: Khách hàng Trần Văn B, mã đơn hàng #MTX-9988, mua tại MartX Q1. Khi tư vấn tiếp, hãy sử dụng đúng thông tin này.`

Phương án 2: Thiết kế từ phía hệ thống MartX

-   Xây dựng cơ sở dữ liệu riêng để lưu thông tin khách hàng và đơn hàng.
    
-   Mỗi khách hàng cần có mã định danh để hệ thống tìm đúng thông tin.
    
-   Khi khách hàng đặt câu hỏi, hệ thống tự động lấy lại dữ liệu cần thiết và cung cấp cho AI.
    
-   Tạo bản tóm tắt hội thoại sau mỗi giai đoạn tư vấn để giảm lượng Token phải đưa vào Context Window.
    

