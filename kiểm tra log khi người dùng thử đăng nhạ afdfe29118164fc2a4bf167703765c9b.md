# kiểm tra log khi người dùng thử đăng nhập không thành công

Để trên Zimbra Mail Server, bạn có thể xem các tệp nhật ký của Zimbra. Thông tin về các lần đăng nhập không thành công thường được ghi vào tệp nhật ký `/var/log/zimbra.log`. Để kiểm tra các sự cố đăng nhập không thành công, bạn có thể sử dụng các lệnh dòng lệnh hoặc một trình duyệt log.

**Sử dụng lệnh dòng lệnh:**

1. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra.
2. Sử dụng lệnh `grep` để tìm kiếm các dòng liên quan đến đăng nhập không thành công trong tệp nhật ký Zimbra:
    
    ```
    grep "authentication failed" /var/log/zimbra.log
    
    ```
    
    Hoặc để kiểm tra các sự cố đăng nhập không thành công của một người dùng cụ thể:
    
    ```
    grep "authentication failed for user@example.com" /var/log/zimbra.log
    
    ```
    
    Thay `user@example.com` bằng địa chỉ email của người dùng bạn quan tâm.
    

**Sử dụng giao diện người dùng Zimbra Admin Console:**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Trong giao diện người dùng, chuyển đến mục "Auditing and Reports" hoặc "Kiểm tra và Báo cáo."
3. Trong mục này, bạn có thể tìm kiếm các sự cố đăng nhập không thành công bằng cách sử dụng các bộ lọc và tùy chọn tìm kiếm.

Lưu ý rằng tệp nhật ký Zimbra có thể lớn và có nhiều thông tin khác nhau, bao gồm các hoạt động khác trong hệ thống. Do đó, việc sử dụng lệnh `grep` để lọc ra các thông tin liên quan đến đăng nhập không thành công là một cách hiệu quả để kiểm tra log.