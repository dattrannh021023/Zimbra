# Check status, start , restart service zimbra

Trong Zimbra Mail Server, bạn có thể kiểm tra trạng thái (status) của dịch vụ Zimbra, khởi động (start) dịch vụ, và khởi động lại (restart) dịch vụ bằng cách sử dụng các lệnh dòng lệnh. Dưới đây là một số lệnh quan trọng để thực hiện các thao tác này:

1. **Kiểm tra trạng thái dịch vụ Zimbra:**
    
    Để kiểm tra trạng thái của các dịch vụ Zimbra, bạn có thể sử dụng lệnh sau:
    
    ```
    zmcontrol status
    
    ```
    
    Lệnh này sẽ liệt kê tất cả các dịch vụ Zimbra và trạng thái của chúng (đang hoạt động, ngừng hoạt động, v.v.).
    
2. **Khởi động dịch vụ Zimbra:**
    
    Để khởi động tất cả các dịch vụ Zimbra, bạn có thể sử dụng lệnh sau:
    
    ```
    zmcontrol start
    
    ```
    
    Để khởi động một dịch vụ cụ thể (ví dụ: LDAP), bạn có thể sử dụng lệnh sau:
    
    ```
    zmcontrol start ldap
    
    ```
    
3. **Khởi động lại dịch vụ Zimbra:**
    
    Để khởi động lại tất cả các dịch vụ Zimbra, bạn có thể sử dụng lệnh sau:
    
    ```
    zmcontrol restart
    
    ```
    
    Để khởi động lại một dịch vụ cụ thể (ví dụ: MTA), bạn có thể sử dụng lệnh sau:
    
    ```
    zmcontrol restart mta
    
    ```
    

Lưu ý rằng bạn cần có quyền truy cập quản trị hoặc quyền root để thực hiện các lệnh này trên máy chủ Zimbra. Đảm bảo rằng bạn đã đăng nhập với quyền đủ cao để thực hiện các thao tác kiểm tra và quản lý dịch vụ Zimbra.