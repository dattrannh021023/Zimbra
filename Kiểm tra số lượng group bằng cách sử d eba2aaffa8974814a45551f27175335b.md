# Kiểm tra số lượng group bằng cách sử dụng giao diện người dùng (UI) hoặc dòng lệnh (command line).

Trong Zimbra Mail Server, bạn có thể **Sử dụng Giao diện Người dùng (UI):**

1. Đăng nhập vào Zimbra Admin Console qua trình duyệt web bằng đường dẫn `https://your-zimbra-server:7071` và sử dụng tên người dùng và mật khẩu của bạn.
2. Sau khi đăng nhập, bạn có thể tìm kiếm danh sách các group bằng cách di chuyển đến mục "Distribution Lists" hoặc "Danh sách phân phối" trong giao diện. Ở đây, bạn sẽ thấy danh sách các group và số lượng group hiện có.

**Sử dụng Command Line:**

Để kiểm tra số lượng group bằng dòng lệnh, bạn có thể sử dụng lệnh `zmprov`, công cụ quản lý dòng lệnh cho Zimbra. Mở một cửa sổ dòng lệnh trên máy chủ Zimbra và sử dụng lệnh sau:

```
zmprov gadl

```

Lệnh trên sẽ liệt kê tất cả các danh sách phân phối (group) trong Zimbra và đếm chúng. Số lượng group sẽ được hiển thị dưới dạng danh sách.

Ví dụ, nếu bạn muốn đếm số lượng group bằng lệnh, bạn có thể sử dụng lệnh sau:

```
zmprov gadl | wc -l

```

Lệnh này sẽ đếm số lượng group và hiển thị nó trên màn hình.

Lưu ý rằng bạn cần quyền truy cập quản trị để thực hiện các lệnh này trên Zimbra Server.