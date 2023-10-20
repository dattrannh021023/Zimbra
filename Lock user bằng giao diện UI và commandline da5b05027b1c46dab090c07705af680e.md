# Lock user bằng giao diện UI và commandline

Để khóa một người dùng (disable user) trong Zimbra Mail Server, bạn có thể sử dụng cả giao diện người dùng (UI) và dòng lệnh (command line). Dưới đây là cách để thực hiện cả hai:

**Khóa Người Dùng Bằng Giao Diện Người Dùng (UI):**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Sau khi đăng nhập, tìm và chọn người dùng mà bạn muốn khóa.
3. Trong trang thông tin người dùng đó, bạn sẽ thấy một tùy chọn để khóa người dùng. Thường là một tùy chọn như "Disable Account" hoặc "Lock Account." Nhấn vào đó để khóa người dùng.

**Khóa Người Dùng Bằng Dòng Lệnh (Command Line):**

Để khóa một người dùng bằng dòng lệnh, bạn có thể sử dụng lệnh `zmprov`, công cụ quản lý dòng lệnh cho Zimbra. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra và sử dụng lệnh sau:

```
zmprov modifyAccount <TênNgườiDùng> zimbraAccountStatus locked

```

Thay `<TênNgườiDùng>` bằng tên người dùng bạn muốn khóa. Lệnh này sẽ đặt trạng thái tài khoản của người dùng thành "locked," làm cho tài khoản không thể đăng nhập.

Ví dụ, để khóa tài khoản có tên người dùng "[user@example.com](mailto:user@example.com)," bạn có thể sử dụng lệnh sau:

```
zmprov modifyAccount user@example.com zimbraAccountStatus locked

```

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện các lệnh này trên Zimbra Server. Đảm bảo bạn đã đăng nhập với quyền đủ cao để khóa tài khoản của người dùng.