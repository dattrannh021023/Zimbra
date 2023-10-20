# Tìm kiếm thư mục cài đặt chứa data email, folder log

Thư mục chứa dữ liệu email và các folder log trong Zimbra Mail Server thường được cài đặt trong các vị trí mặc định. Dưới đây là các thư mục quan trọng mà bạn có thể tìm trong một cài đặt Zimbra tiêu chuẩn:

1. **Thư mục Data Email:** Thư mục này chứa dữ liệu email của người dùng. Thường thì nó sẽ có địa chỉ `/opt/zimbra/store`. Tất cả email của người dùng được lưu trữ trong thư mục này.

```bash
ls /opt/zimbra/store    # Kiểm tra thư mục chứa dữ liệu email
```

1. **Thư mục Log:** Thư mục này chứa các tệp nhật ký (logs) của Zimbra, bao gồm thông tin về hoạt động hệ thống, email, và nhiều thông tin khác. Thường thì nó sẽ có địa chỉ `/var/log/zimbra.log`

```bash
ls /var/log/zimbra.log      # Kiểm tra thư mục chứa tệp nhật ký
```

1. **Thư mục Config:** Thư mục này chứa tệp cấu hình của Zimbra. Thường thì nó sẽ có địa chỉ `/opt/zimbra/conf`.
2. **Thư mục Backup:** Nếu bạn thực hiện sao lưu (backup) dữ liệu của Zimbra, thư mục backup chứa các dữ liệu sao lưu. Thường thì nó sẽ có địa chỉ `/opt/zimbra/backup`.
3. **Thư mục Junk và Trash:** Thư mục này chứa thư rác (Junk) và thư đã xóa (Trash) của người dùng. Thường thì nó sẽ nằm trong thư mục của người dùng, ví dụ: `/opt/zimbra/store/<người_dùng>/Junk` và `/opt/zimbra/store/<người_dùng>/Trash`.

Lưu ý rằng các đường dẫn thư mục có thể thay đổi dựa trên phiên bản và cấu hình cụ thể của Zimbra Mail Server của bạn. Để tìm chính xác thư mục trong hệ thống của bạn, bạn có thể sử dụng lệnh dòng lệnh như `ls` hoặc `find`. Ví dụ:

```

```