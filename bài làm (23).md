# Vấn đề :
Bạn là Lead Developer của một dự án. Bạn vừa mất điện thoại (thiết bị chứa duy nhất mã Google Authenticator). Bạn không thể đăng nhập vào tài khoản AWS để bảo trì hệ thống.
# Yêu cầu :
Thiết kế quy trình sử dụng Backup Codes để lấy lại quyền truy cập mà không làm lộ thông tin cho kẻ nhặt được điện thoại.
# Cách làm :
## 1. Phân tích IPO

-   Input: Mã dự phòng một lần (Backup Code) được lưu trữ offline từ trước.
    
-  Process:
    
    1.  Xác thực: Nhập Backup Code để vượt qua yêu cầu 2FA khi bị mất điện thoại.
        
    2.  Hủy mã cũ (Revoke):Vô hiệu hóa ngay lập tức các Backup Codes cũ và gỡ thiết bị cũ ra khỏi tài khoản AWS.
        
    3.  Cấp mã mới (Regenerate): Cài đặt 2FA trên thiết bị mới và tạo bộ mã dự phòng mới an toàn.
        
-   Output: Khôi phục quyền Lead Developer và đảm bảo an toàn tuyệt đối cho hệ thống AWS.
    

## 2. Vì sao không được lưu Backup Codes dưới dạng ảnh trong điện thoại?

-   Rủi ro Cloud Sync: Thư viện ảnh thường tự động đồng bộ lên đám mây (Google Photos, iCloud), dễ bị lộ nếu tài khoản bị xâm nhập hoặc điện thoại rơi vào tay người khác.
    
-   Rủi ro quyền ứng dụng: Các ứng dụng chứa mã độc có thể quét và tự động trích xuất ảnh chứa thông tin bảo mật từ bộ nhớ thiết bị.

