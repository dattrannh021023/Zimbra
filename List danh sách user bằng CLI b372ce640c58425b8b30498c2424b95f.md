# List danh sách user bằng CLI

Để liệt kê danh sách người dùng trong Zimbra Mail Server bằng dòng lệnh (command line), bạn có thể sử dụng lệnh `zmprov`. Dưới đây là cách để liệt kê danh sách người dùng:

1. **Liệt kê tất cả người dùng:**
    
    Sử dụng lệnh sau để liệt kê tất cả các người dùng trong hệ thống Zimbra:
    
    ```
    zmprov -l gaa
    
    ```
    
    Lệnh này sẽ hiển thị danh sách địa chỉ email của tất cả người dùng.
    
2. **Liệt kê người dùng theo tên miền cụ thể:**
    
    Nếu bạn muốn liệt kê người dùng trong một tên miền cụ thể, bạn có thể sử dụng lệnh sau:
    
    ```
    zmprov -l gaa yourdomain.com
    
    ```
    
    Thay `yourdomain.com` bằng tên miền mà bạn muốn kiểm tra.
    
3. **Liệt kê tất cả người dùng và thông tin chi tiết:**
    
    Để liệt kê tất cả người dùng và thông tin chi tiết của họ, bao gồm cả UID (User ID) và các thuộc tính khác, bạn có thể sử dụng lệnh sau:
    
    ```
    zmprov -l getAllAccounts
    
    ```
    
    Lệnh này sẽ hiển thị thông tin chi tiết của tất cả người dùng trong hệ thống.
    

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện các lệnh này. Hãy đảm bảo bạn đã đăng nhập với quyền đủ cao để truy cập thông tin về người dùng Zimbra.