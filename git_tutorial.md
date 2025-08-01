✅ 1. Undo commit vừa rồi nhưng giữ lại thay đổi trong file (unstaged)
      git reset --soft HEAD~1
      --soft: Hủy commit nhưng giữ lại các thay đổi trong Staging area (có thể commit lại sau).
      
      Nếu muốn bỏ cả staging (đưa về working directory):
        git reset --mixed HEAD~1
