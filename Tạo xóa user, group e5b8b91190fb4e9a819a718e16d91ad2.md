# Tạo xóa user, group

**Giao diện Người dùng (UI):**

1. **Tạo Người Dùng:**
    - Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu.
    - Chọn mục "Manage" và sau đó chọn "Mailboxes"
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled.png)
    
    - Nhấn nút "New" để tạo một hộp thư mới. Sau đó, nhập thông tin cần thiết cho người dùng và nhấn "Finish" để tạo người dùng.
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%201.png)
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%202.png)
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%203.png)
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%204.png)
    
2. **Xóa Người Dùng:**
    - Để xóa người dùng, chọn người dùng cần xóa trong danh sách hộp thư.
    - Nhấn nút "Delete"

![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%205.png)

![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%206.png)

![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%207.png)

![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%208.png)

1. **Tạo Nhóm:**
    - Để tạo một nhóm, chọn mục "Distribution Lists"
    - Nhấn nút "New"  để tạo một danh sách phân phối mới. Sau đó, nhập thông tin cần thiết cho nhóm và thêm thành viên nếu cần.
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%209.png)
    
2. **Xóa Nhóm:**
    - Để xóa một nhóm, chọn nhóm cần xóa trong danh sách danh sách phân phối.
    - Nhấn nút "Delete"
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%2010.png)
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%2011.png)
    
    ![Untitled](Ta%CC%A3o%20xo%CC%81a%20user,%20group%20e5b8b91190fb4e9a819a718e16d91ad2/Untitled%2012.png)
    

**Dòng Lệnh (Command Line):**

1. **Tạo Người Dùng:**
    - Sử dụng lệnh `zmprov` để tạo người dùng. Ví dụ:
        
        ```
        zmprov ca trantiendat@tueminh.cc password
        
        ```
        
2. **Xóa Người Dùng:**
    - Sử dụng lệnh `zmprov` để xóa người dùng. Ví dụ:
        
        ```
        zmprov da trantiendat@tueminh.cc
        
        ```
        
3. **Tạo Nhóm:**
    - Sử dụng lệnh `zmprov` để tạo danh sách phân phối (nhóm). Ví dụ:
        
        ```
        zmprov cdl pns@tueminh.cc
        ```
        
4. **Xóa Nhóm:**
    - Sử dụng lệnh `zmprov` để xóa danh sách phân phối (nhóm). Ví dụ:
        
        ```
        zmprov ddl pns@tueminh.cc
        ```