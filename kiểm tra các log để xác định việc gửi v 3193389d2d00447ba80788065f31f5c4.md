# kiểm tra các log để xác định việc gửi và nhận email có thành công hay thất bại.

Trong Zimbra Mail Server, bạn có thể  Thông tin về các giao dịch gửi và nhận email thường được ghi vào các tệp nhật ký sau:

1. **Tệp nhật ký gửi email (Outgoing Mail Logs):** Thông tin về việc gửi email từ Zimbra tới các máy chủ email khác được ghi vào tệp nhật ký này. Đường dẫn mặc định của tệp này là `/var/log/zimbra.log`.
2. **Tệp nhật ký nhận email (Incoming Mail Logs):** Thông tin về việc nhận email từ các máy chủ email khác được ghi vào tệp nhật ký này. Đường dẫn mặc định của tệp này là `/var/log/zimbra.log`.

Để kiểm tra log gửi và nhận thành công hoặc thất bại, bạn có thể sử dụng các lệnh dòng lệnh hoặc một trình duyệt log.

**Sử dụng lệnh dòng lệnh:**

1. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra.
2. Sử dụng các lệnh `grep` để tìm kiếm thông tin liên quan trong tệp nhật ký. Ví dụ, để tìm kiếm các thông báo gửi email thành công:
    
    ```
    grep "status=sent" /var/log/zimbra.log
    
    ```
    
    Để tìm kiếm các thông báo gửi email thất bại:
    
    ```
    grep "status=failed" /var/log/zimbra.log
    
    ```
    
    Tùy thuộc vào cấu hình của hệ thống và loại thông báo, bạn có thể sử dụng các biểu thức chính quy để tìm kiếm cụ thể hơn.
    

**Sử dụng giao diện người dùng Zimbra Admin Console:**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Trong giao diện người dùng, chuyển đến mục "Auditing and Reports" hoặc "Kiểm tra và Báo cáo."
3. Sử dụng các bộ lọc và tùy chọn tìm kiếm để xác định thông tin gửi và nhận thành công hoặc thất bại.

Lưu ý rằng việc kiểm tra log gửi và nhận email cần kiểm tra các thông báo gửi và nhận trong tệp nhật ký và phân tích thông tin để xác định thành công hoặc thất bại. Thông tin cụ thể về cấu hình và loại log có thể thay đổi dựa trên phiên bản và cấu hình cụ thể của Zimbra Mail Server của bạn.