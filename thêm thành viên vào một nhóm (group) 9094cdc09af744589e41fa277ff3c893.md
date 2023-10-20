# thêm thành viên vào một nhóm (group)

Để  trong Zimbra Mail Server, bạn có thể sử dụng giao diện người dùng (UI) hoặc dòng lệnh (command line).

**Sử dụng Giao diện Người dùng (UI):**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Sau khi đăng nhập, tìm và chọn nhóm (group) mà bạn muốn thêm thành viên.
3. Trong trang thông tin về nhóm đó, bạn sẽ thấy một tùy chọn để thêm thành viên. Thường là một nút hoặc biểu tượng có chú thích "Add Member" hoặc tương tự. Nhấn vào đó để mở giao diện thêm thành viên.
4. Nhập địa chỉ email của thành viên bạn muốn thêm và sau đó nhấn nút "Add" hoặc tương tự để xác nhận.

**Sử dụng Command Line:**

Để thêm thành viên vào một nhóm bằng dòng lệnh, bạn có thể sử dụng lệnh `zmprov`, công cụ quản lý dòng lệnh cho Zimbra. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra và sử dụng lệnh sau:

```
zmprov adlm <TênNhóm> <Địa chỉ email thành viên>

```

Thay `<TênNhóm>` bằng tên của nhóm bạn muốn thêm thành viên và `<Địa chỉ email thành viên>` bằng địa chỉ email của thành viên bạn muốn thêm.

Ví dụ, để thêm thành viên có địa chỉ email "[member@example.com](mailto:member@example.com)" vào một nhóm có tên "salesgroup," bạn có thể sử dụng lệnh sau:

```
zmprov adlm salesgroup member@example.com

```

Lệnh này sẽ thêm thành viên vào nhóm "salesgroup."

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện các lệnh này trên Zimbra Server.