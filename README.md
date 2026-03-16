## Giới thiệu
Ứng dụng này có thể được xây dựng bằng Xcode hoặc sử dụng Theos để tạo ứng dụng trên iOS.

## Cách sử dụng
Xây dựng ứng dụng với Theos
1. **Cài đặt Theos**: Đảm bảo rằng bạn đã cài đặt Theos trên máy tính của mình.
2. **Tạo dự án mới**: Sử dụng lệnh sau để tạo một dự án mới:
```bash
$THEOS/bin/nic.pl
```
3. **Chọn loại dự án**: `[3.] iphone/application`. (bằng cách nhập số 3)

4. **Nhập thông tin dự án**: Nhập các thông tin cần thiết như tên dự án, tác giả, v.v.

5. **Chỉnh sửa dự án**: Mở dự án và thêm các file cần thiết vào dự án.

6. **Cập nhật Makefile**: Khai báo các file cần thiết trong `Makefile`.

7. **Biên dịch dự án**: Sử dụng lệnh `make` để biên dịch dự án.

## AltStore — Hướng dẫn

Bước 1: Download file build

Vào: https://github.com/chidang26/testapp/actions/runs/23149919793
→ Tab Artifacts → Download ios-build

Bước 2: Cài AltStore trên Windows

1. Tải AltStore: https://altstore.io
2. Cài iTunes (từ Apple, không phải Microsoft Store)
3. Cài iCloud (từ Apple)
4. Cài AltStore → mở AltServer
5. Kết nối iPhone qua USB

Bước 3: Cài AltStore lên iPhone

1. Click AltServer icon (tray) → Install AltStore → chọn iPhone
2. Nhập Apple ID + password
3. Trên iPhone: Settings → General → VPN & Device Management → Trust Apple ID

Bước 4: Cài app

1. Mở AltStore trên iPhone
2. Tab My Apps → + → chọn file .ipa đã download
3. Nhập Apple ID → app được cài

Bước 5: Trust app

Settings → General → VPN & Device Management → Trust developer

───

⚠️ Lưu ý: File .ipa từ GitHub Actions là unsigned. Bạn cần convert .app → .ipa trước:

# Trên Linux server, tạo .ipa:
cd ~/HelloApp/testapp/xcodeapptesst
mkdir -p Payload
cp -r <đường_dẫn_đến_*.app> Payload/
zip -r MyApp.ipa Payload/
