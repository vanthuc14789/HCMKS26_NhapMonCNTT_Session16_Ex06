# BÀI TẬP SESSION 16 – EX06: PHÂN TÍCH HIỆU NĂNG NETWORK

## Phần 1. Phân tích

1. **Nút thắt cổ chai:**
   - Các file hình ảnh bản đồ có dung lượng lớn khiến thời gian tải lâu.
   - Request bị lỗi 404 làm tài nguyên không được tải.
   - CSS và JavaScript tải chậm khiến giao diện hiển thị muộn.

2. **Kiểm tra bằng DevTools:**
   - Nhấn `F12` → chọn tab **Network**.
   - Tích **Disable cache** rồi tải lại trang bằng `Ctrl + R`.
   - Quan sát cột Status, Size, Time và biểu đồ Waterfall.
   - Request màu đỏ, mã 404 là tài nguyên không tìm thấy.
   - File có dung lượng lớn và thời gian tải dài là nguyên nhân cần kiểm tra.

## Phần 2. Triển khai

Đề xuất quy trình tối ưu 3 bước:

1. **Sửa lỗi 404:** Kiểm tra và sửa lại đường dẫn CSS, JavaScript và hình ảnh bị sai.
2. **Nén hình ảnh:** Giảm dung lượng ảnh, sử dụng WebP hoặc AVIF để tải nhanh hơn.
3. **Bật Browser Cache:** Thiết lập thời gian lưu cache cho hình ảnh, CSS và JavaScript tĩnh để trình duyệt không phải tải lại toàn bộ.

Đảm bảo các file CSS và JavaScript quan trọng tải thành công với mã `200 OK` trước khi giao diện được hiển thị đầy đủ.

## Phần 3. Kiểm thử

Khi reload trang và nhận mã `304 Not Modified`, đây là tín hiệu tốt vì tài nguyên không thay đổi nên trình duyệt có thể sử dụng bản đã lưu trong Cache.

Nhờ đó, hệ thống giảm lượng dữ liệu phải tải lại, tiết kiệm băng thông và giúp trang web tải nhanh hơn.

## Kết luận

Sửa lỗi 404, nén hình ảnh và bật Browser Cache giúp giảm thời gian tải trang, tiết kiệm băng thông và cải thiện trải nghiệm sử dụng.