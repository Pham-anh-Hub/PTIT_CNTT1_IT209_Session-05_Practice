# bài tập 2: Tái cấu trúc lịch sử commit bằng interactice rebase

**1. Tạo lần lượt 4 commit trên nhánh làm việc hiện tại:**
- Commit 1: Tạo auth.js -> feat: khoi tao module auth
- Commit 2: Sửa auth.js -> fix typo
- Commit 3: Sửa auth.js -> adds utility functions
- Commit 4: Tạo temp.txt -> add temp file for debug

**2. Chạy lệnh Interactive Rebase lùi về 4 commit trước:**
```bash
git rebase -i HEAD~4
```