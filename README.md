<img width="200"  alt="38623778-c798-4a59-a875-03c6f2dd95fc" src="https://github.com/user-attachments/assets/543ec02c-d3e1-4eef-a826-d639d3b8c1f6" />
<img width="200"  alt="87de1594-afa9-4364-890e-2a623d9a70ef" src="https://github.com/user-attachments/assets/eade345d-4171-41a8-ab72-fe4182cafbd1" />
<img width="200"  alt="8ed1f2d6-30fc-4f1f-94c3-44fe1739ab7c" src="https://github.com/user-attachments/assets/094a8263-9ea3-4553-8d4c-850751fefcac" />
<img width="200"  alt="7839e93f-0402-43e0-ae35-701d4a85d58d" src="https://github.com/user-attachments/assets/0ccf1841-d2be-465a-b1f5-1bb39619a48b" />

# LAB 8: Firebase Authentication (SwiftUI) 🔐

Một ứng dụng iOS hoàn chỉnh minh họa luồng xác thực người dùng (Authentication Flow) đạt chuẩn Production, sử dụng **SwiftUI**, kiến trúc **MVVM** và **Firebase Authentication**.

## 🌟 Các tính năng nổi bật (Features)

- **Xác thực Cơ bản:** Đăng ký và Đăng nhập bằng Email/Mật khẩu.
- **Xác thực Mạng xã hội:** Tích hợp Đăng nhập bằng Google (Google Sign-In) an toàn.
- **Quản lý Phiên (Session Persistence):** Tự động duy trì trạng thái đăng nhập khi đóng/mở ứng dụng.
- **Quản lý Tài khoản:** Chức năng Đăng xuất và Khôi phục mật khẩu (Forgot Password).
- **Trải nghiệm Người dùng (UX):**
  - Hiệu ứng Tải (Loading Overlay) chặn tương tác khi gọi API.
  - Xử lý lỗi chuyên nghiệp (Error Banner) dịch mã lỗi Firebase sang Tiếng Việt.
  - Hỗ trợ giao diện Tối/Sáng (Dark/Light Mode) tự động theo hệ thống.
- **Bảo mật:** Không hardcode thông tin nhạy cảm, ẩn URL Scheme, phân tách hoàn toàn Logic và View.

## 🏗 Kiến trúc Hệ thống (Clean Architecture & MVVM)

Dự án được phân chia theo cấu trúc thư mục rõ ràng nhằm tối ưu hóa khả năng bảo trì và mở rộng:

```text
FirebaseAuthApp/
│
├── Models/          # Dữ liệu nguyên thủy (AppUser)
├── Services/        # Chịu trách nhiệm giao tiếp trực tiếp với Firebase SDK (AuthService)
├── ViewModels/      # Quản lý trạng thái UI, xử lý lỗi và điều phối dữ liệu (AuthViewModel)
├── Views/           # Giao diện người dùng (Splash, Login, Register, Home)
├── Components/      # Các UI Component tái sử dụng (AuthTextField, LoadingView, PrimaryButton...)
└── FirebaseAuthApp  # Root App & Cấu hình môi trường khởi tạo
```
🛠 Công nghệ sử dụng
Ngôn ngữ: Swift 5

Giao diện: SwiftUI

Kiến trúc: MVVM (Model-View-ViewModel)

Thư viện bên thứ 3 (SPM):

firebase-ios-sdk (FirebaseCore, FirebaseAuth)

GoogleSignIn-iOS

🚀 Hướng dẫn Cài đặt & Chạy dự án
Clone repository này về máy.

Cấu hình Firebase:

Tạo một project trên Firebase Console.

Bật phương thức đăng nhập Email/Password và Google trong phần Authentication.

Tải file GoogleService-Info.plist và kéo thả vào thư mục gốc của project Xcode (đảm bảo đã tích chọn Target FirebaseAuthApp).

Cấu hình Google Sign-In URL Scheme:

Mở file GoogleService-Info.plist, copy giá trị của REVERSED_CLIENT_ID.

Vào cài đặt Target FirebaseAuthApp > tab Info > URL Types.

Thêm một URL Type mới và dán giá trị vừa copy vào ô URL Schemes.

Phân giải thư viện: - Vào File > Packages > Resolve Package Versions để Xcode tải các SDK cần thiết.

Chạy ứng dụng: Nhấn Cmd + R để Build & Run trên Simulator hoặc thiết bị thật.
