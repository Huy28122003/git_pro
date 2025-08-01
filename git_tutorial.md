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
