| Loại Commit | Tiêu Đề                 | Mô tả                                                                 | Emoji |
|-------------|-------------------------|-----------------------------------------------------------------------|--------|
| `feat`      | Features                | Một tính năng mới                                                    | ✨     |
| `fix`       | Bug Fixes               | Sửa một lỗi                                                          | 🐛     |
| `docs`      | Documentation           | Chỉ thay đổi tài liệu                                                | 📚     |
| `style`     | Styles                  | Thay đổi không ảnh hưởng đến ý nghĩa của mã (format, khoảng trắng…) | 💎     |
| `refactor`  | Code Refactoring        | Thay đổi mã không sửa lỗi hoặc thêm tính năng                       | 📦     |
| `perf`      | Performance Improvements| Thay đổi giúp cải thiện hiệu suất                                    | 🚀     |
| `test`      | Tests                   | Thêm hoặc sửa các kiểm thử                                           | 🚨     |
| `build`     | Builds                  | Thay đổi liên quan đến hệ thống build hoặc phụ thuộc ngoài           | 🛠     |
| `ci`        | Continuous Integrations | Thay đổi file cấu hình/kịch bản CI (Travis, Circle, v.v.)            | ⚙️     |
| `chore`     | Chores                  | Thay đổi khác, không liên quan đến source code hay test              | ♻️     |
| `revert`    | Reverts                 | Quay lại một commit trước đó                                         | 🗑     |



### ✅ 1. Undo commit gần nhất nhưng **giữ lại thay đổi trong file (unstaged)**

#### 🔁 Giữ lại thay đổi trong Staging Area:
```bash
git reset --soft HEAD~1
```
- `--soft`: Hủy commit **nhưng vẫn giữ thay đổi trong khu vực Staging**  
  → Bạn có thể commit lại sau.

---

#### 🧹 Nếu muốn **bỏ cả Staging** (chỉ giữ thay đổi ở Working Directory):
```bash
git reset --mixed HEAD~1
```
- `--mixed`: Hủy commit và **đưa thay đổi về Working Directory**  
  → Các file sẽ trở về trạng thái *unstaged*.
