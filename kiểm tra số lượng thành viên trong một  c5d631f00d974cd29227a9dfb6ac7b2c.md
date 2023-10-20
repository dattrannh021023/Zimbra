# kiểm tra số lượng thành viên trong một nhóm (group)

Để trong Zimbra Mail Server, bạn có thể sử dụng giao diện người dùng (UI) hoặc dòng lệnh (command line).

**Sử dụng Giao diện Người dùng (UI):**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Sau khi đăng nhập, tìm và chọn nhóm (group) mà bạn muốn kiểm tra.
3. Trong trang thông tin về nhóm đó, bạn sẽ thấy số lượng thành viên của nhóm được hiển thị.

**Sử dụng Command Line:**

Để kiểm tra số lượng thành viên trong một nhóm bằng dòng lệnh, bạn có thể sử dụng lệnh `zmprov`, công cụ quản lý dòng lệnh cho Zimbra. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra và sử dụng lệnh sau:

```
zmprov gdl <TênNhóm> | grep "zimbraMailForwardingAddress:" | wc -l

```

Thay `<TênNhóm>` bằng tên của nhóm bạn muốn kiểm tra. Lệnh này sẽ đếm số lượng thành viên trong nhóm và hiển thị nó trên màn hình.

Ví dụ, để kiểm tra số lượng thành viên trong một nhóm có tên "salesgroup," bạn có thể sử dụng lệnh sau:

```
zmprov gdl salesgroup | grep "zimbraMailForwardingAddress:" | wc -l

```

Lệnh này sẽ đếm số lượng thành viên trong nhóm "salesgroup" và hiển thị nó trên màn hình.

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện các lệnh này trên Zimbra Server.