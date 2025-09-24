# 📘 React Project Coding Convention

## 📂 Cấu trúc thư mục

| **Thư mục / File** | **Vai trò chính** |
|---------------------|-------------------|
| **components/**    | Các UI components tái sử dụng, tổ chức theo **Atomic Design** (atoms, molecules, organisms, templates). |
| **config/**        | Cấu hình chung cho ứng dụng (env, constants, theme, router config,…). |
| **hook/**          | Custom React hooks để tái sử dụng logic (`useAuth`, `useFetch`, …). |
| **layout/**        | Layout tổng thể (Header, Sidebar, Footer, AppLayout,…). |
| **model/**         | Mock data / fake data phục vụ phát triển & prototype UI (không dùng cho production). |
| **page/**          | Các trang chính (Home, Login, Dashboard…), mapping trực tiếp với route. |
| **redux/**         | Quản lý state với **Redux Toolkit**: `store/`, `slice/`, `middleware/`, `persist/`. |
| **service/**       | Tầng service giao tiếp với API/backend: axios instance, API methods. |
| **utils/**         | Các hàm tiện ích (formatDate, validateEmail, debounce,…). |
| **App.jsx**        | File root chứa khung ứng dụng (routing, provider, layout). |
| **index.css**      | CSS global áp dụng cho toàn app (reset, global style, theme). |
| **main.jsx**       | Điểm khởi đầu, render React vào DOM root, khởi tạo provider (Redux, Router…). |
| **deploy.sh**      | Script tự động hóa **deploy** lên server. |
| **.env/**          | File môi trường (API_URL, TOKEN_KEY,…), không commit lên git (nếu chứa secret). |

---
## 🔤 2. Quy tắc đặt tên

- **Component (React)**: PascalCase  
  - Ví dụ: `UserProfile.tsx`, `LoginForm.tsx`

- **Hook (Custom hook)**: bắt đầu bằng `useXxx`  
  - Ví dụ: `useAuth.ts`, `useFetch.ts`

- **File TypeScript thường**: camelCase  
  - Ví dụ: `formatDate.ts`, `validateEmail.ts`

- **Folder**: lowercase hoặc kebab-case  
  - Ví dụ: `user-profile/`, `auth/`

- **Biến, hàm**: camelCase  
  - Ví dụ: `handleSubmit`, `userName`

- **Hằng số**: UPPER_CASE  
  - Ví dụ: `API_BASE_URL`, `DEFAULT_TIMEOUT`

- **Kiểu dữ liệu / Interface / Type**: PascalCase, có prefix rõ ràng  
  - Interface: `IUser`, `IProduct`  
  - Type: `UserRole`, `AuthResponse`  
  - Enum: PascalCase + giá trị UPPER_CASE  
    ```ts
    enum UserRole {
      ADMIN = "ADMIN",
      USER = "USER",
    }
    ```

- **Generic Type**: đặt tên ngắn gọn, chữ in hoa  
  - Ví dụ: `T`, `K`, `V`, hoặc có ý nghĩa hơn: `TUser`, `TResponse`
## 🎨 Biến màu chung

```css
--primary-color:   #627254;
--secondary-color: #76885b;
--default-color:   #24282b;
--neutral-color:   #dddddd;

---
# 🌿 GitHub Convention

## 1. Branch Naming Convention
- Dùng **kebab-case** (chữ thường, dấu `-` ngăn cách).
- Prefix theo loại nhánh:

| Loại nhánh | Cách đặt tên | Ví dụ |
|------------|--------------|-------|
| **Feature** (chức năng mới) | `feature/<tên>` | `feature/login-page` |
| **Fix** (sửa bug) | `fix/<tên>` | `fix/wrong-password-validation` |
| **Hotfix** (sửa gấp production) | `hotfix/<tên>` | `hotfix/payment-crash` |
| **Release** (chuẩn bị phát hành) | `release/<version>` | `release/1.0.0` |

👉 Khi bắt đầu làm:
```bash
git checkout -b feature/login-page
## 2. Commit Convention
- **feat**: Thêm tính năng mới.  
  Ví dụ: `feat: add login form validation`  
- **fix**: Sửa lỗi.  
  Ví dụ: `fix: resolve crash when user logs out`  
- **docs**: Thay đổi tài liệu (README, wiki, ...).  
  Ví dụ: `docs: update API usage guide`  
- **style**: Thay đổi liên quan đến format, convention, không ảnh hưởng logic.  
  Ví dụ: `style: reformat code with prettier`  
- **refactor**: Thay đổi code nhưng không thêm tính năng hoặc sửa lỗi.  
  Ví dụ: `refactor: simplify user profile component`  
- **test**: Thêm hoặc sửa test.  
  Ví dụ: `test: add unit test for login service`  
- **chore**: Cập nhật công cụ, cấu hình, không ảnh hưởng logic sản phẩm.  
  Ví dụ: `chore: update dependencies`