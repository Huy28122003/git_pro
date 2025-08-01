## 🎯 Quy ước đặt tên commit

### 📌 Cấu trúc

```
<Loại commit>/<Mã task>/<Mô tả task>
```

### 📋 Giải thích

- **<Tiêu đề>**: Loại commit (ví dụ: `feat`, `fix`, `docs`, `refactor`, v.v.)
- **<Mã task>**: Mã định danh task hoặc issue (ví dụ: `TASK-123`, `BUG-456`) được đặt trong các phần mềm quản lý task như JIRA
- **<Mô tả task>**: Mô tả ngắn gọn, rõ ràng về thay đổi

### 📍 Ví dụ

```bash
feat/TASK-101/thêm màn hình đăng nhập  
fix/BUG-202/sửa lỗi không load được dữ liệu  
docs/CHORE-999/cập nhật hướng dẫn cài đặt  
```

### ✅ Lưu ý

- Mô tả task nên viết bằng tiếng Việt không dấu hoặc tiếng Anh tùy theo team.
- Dùng chữ thường, phân cách bằng dấu `-` nếu cần.
- Không kết thúc bằng dấu chấm.


| Loại Commit | Tiêu Đề                 | Mô tả                                                                 | Emoji |
|-------------|-------------------------|-----------------------------------------------------------------------|--------|
| `feat`      | Features                | Một tính năng mới                                                    | ✨     |
| `fix`       | Bug Fixes               | Sửa một lỗi                                                          | 🐛     |
| `refactor`  | Code Refactoring        | Thay đổi mã không sửa lỗi hoặc thêm tính năng                       | 📦     |
| `test`      | Tests                   | Thêm hoặc sửa các kiểm thử                                           | 🚨     |
| `revert`    | Reverts                 | Quay lại một commit trước đó                                         | 🗑     |



### 1️⃣ Undo commit gần nhất nhưng **giữ lại thay đổi trong file (unstaged)**

#### Giữ lại thay đổi trong Staging Area:
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

### 2️⃣ Xóa Branch

### 🗑 Xóa branch ở local

```bash
git branch -D localBranchName
```

> Dùng để xóa một branch ở máy local.  
> Nếu bạn muốn xóa branch đã được merge rồi, có thể dùng `-d` thay vì `-D`.

---

### 🌐 Xóa branch ở remote

```bash
git push origin --delete remoteBranchName
```

> Cách đầy đủ để xóa một branch từ remote repository (ví dụ: GitHub, GitLab).

Hoặc dùng cú pháp rút gọn:

```bash
git push origin :remoteBranchName
```

> Cú pháp thay thế nhanh, tác dụng tương đương.

## 3️⃣ Git Merge

Gộp các commit của hai nhánh lại với nhau dựa trên thời gian, tạo ra một commit hợp nhất (**merge commit**).

#### 📌 Cách sử dụng:
```bash
git checkout <branch-bạn-muốn-gộp-vào>
git merge <branch-nguồn>
```

#### 📘 Ví dụ:

Giả sử có 3 nhánh:
- `main`
- `Alpha`: tạo từ `main`, thêm commit `D`, `E`
- `Beta`: tạo từ `main`, thêm commit `F`, `G`

Cấu trúc ban đầu:
```
(main)
A--B--C---D--E (Alpha)
       \
        -F--G (Beta)
```

Khi đang ở nhánh `Beta`, muốn nhận thay đổi từ `Alpha`:
```bash
git checkout Beta
git merge Alpha
```

Sau khi merge:
```
(main)
A--B--C---D--E (Alpha)
       \       \
        -F--G--M (Beta)
```

✅ Commit `M` là **merge commit**, chứa toàn bộ thay đổi từ `Alpha` và `Beta`.

---

#### ⚠️ Khi gặp conflict:

1. Xem file bị conflict và sửa thủ công
2. Dùng:
   ```bash
   git add .
   git merge --continue
   ```
   Hoặc nếu muốn sửa message:
   ```bash
   git commit -m "resolve conflict"
   ```

3. Đẩy thay đổi:
   ```bash
   git push
   ```

---

#### 🔄 Hủy merge:

Nếu muốn **hoàn tác merge** (chưa commit hoặc đã commit):

```bash
git reset --hard <commit-trước-khi-merge>
```

> 📍 Dùng `git log` để tìm `commit-trước-khi-merge`.

---

#### 📝 Lưu ý:

- `git pull` = `git fetch` + `git merge`
- Merge dùng phổ biến trong thực tế khi làm việc nhóm
- Sử dụng **Merge Request (MR)** hoặc **Pull Request (PR)** để review trước khi merge

---


