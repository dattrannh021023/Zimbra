# change password user bằng commandline

Để thay đổi mật khẩu của người dùng trong Zimbra Mail Server bằng dòng lệnh (command line), bạn có thể sử dụng lệnh `zmprov`. Dưới đây là cách để thay đổi mật khẩu của người dùng:

1. **Thay đổi mật khẩu người dùng:**
    
    Sử dụng lệnh sau để thay đổi mật khẩu của một người dùng cụ thể:
    
    ```
    zmprov sp <user@example.com> <new_password>
    
    ```
    
    Trong đó:
    
    - `<user@example.com>` là địa chỉ email của người dùng bạn muốn thay đổi mật khẩu.
    - `<new_password>` là mật khẩu mới mà bạn muốn đặt cho người dùng.
    
    Ví dụ:
    
    ```
    zmprov sp user@example.com new_password
    
    ```
    
    Lệnh này sẽ đặt mật khẩu mới cho người dùng.
    

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện lệnh này. Đảm bảo rằng bạn đã đăng nhập với quyền đủ cao để thay đổi mật khẩu của người dùng Zimbra.