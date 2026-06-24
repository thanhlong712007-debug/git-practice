# BÁO CÁO TIẾN ĐỘ KHÓA GIT FOUNDATIONS

## 1. Thông tin học viên & Dự án

* **Khóa học:** Git Foundations (Microsoft Learn - GitHub Foundations)
* **Học viên:** Phan Phú Thành Long
* **Mã sinh viên:** 25E1020031
* **Tên Repository:** github-practice
---

## 2. Quá trình học tập

Quá trình học tập được triển khai theo hai giai đoạn chính dựa trên lộ trình của Microsoft Learn:

### Giai đoạn 1: Kiến thức nền tảng về Git và GitHub

* Tìm hiểu các khái niệm cốt lõi của Git và hệ thống quản lý phiên bản.
* Thực hành quản lý mã nguồn trên môi trường cục bộ (Local Repository).
* Làm quen với GitHub và cách đồng bộ dữ liệu giữa Local Repository và Remote Repository.
* Nghiên cứu mô hình GitHub Flow bao gồm:

  * Branching
  * Committing
  * Pull Request
  * Merge

### Giai đoạn 2: Cộng tác và quản lý dự án nâng cao

* Tìm hiểu cơ chế cộng tác trong dự án phần mềm.
* Thực hành quản lý lịch sử commit.
* Thực hiện các thao tác Merge Branch.
* Xử lý tình huống xung đột mã nguồn (Merge Conflict).
* Thực hành hoàn tác thay đổi bằng Revert/Rollback.
* Nâng cao kỹ năng sử dụng Git thông qua các tình huống mô phỏng thực tế.

---

## 3. Nhật ký thực hành

### 3.1. Số lượng Commit

Trong quá trình thực hành, repository đã ghi nhận:

* **Tổng số commit:** 29 commits

Các commit phản ánh quá trình cập nhật, chỉnh sửa và hoàn thiện bài tập qua từng giai đoạn học tập.

### 3.2. Quản lý Branches

Dự án được tổ chức và quản lý trên 03 nhánh chính:

#### main

Nhánh chính của dự án, chứa phiên bản hoàn thiện và ổn định sau khi các thay đổi được kiểm tra và hợp nhất.

#### feature-1

Nhánh tính năng được sử dụng để thực hành các nội dung liên quan đến Pull Request, Merge, Conflict và Revert.

#### feature-2

Nhánh tính năng thứ hai được tạo nhằm mô phỏng môi trường làm việc nhóm và phục vụ các bài thực hành về Pull Request, Conflict và Revert.

---

### 3.3. Yêu cầu Pull Request

#### Pull Request #1 – Merge Branch

Thực hiện hợp nhất thành công hai nhánh:

* feature-1
* feature-2

vào nhánh chính theo đúng quy trình GitHub Flow.

#### Pull Request #2 – Merge Conflict

Tạo tình huống xung đột mã nguồn bằng cách chỉnh sửa cùng một khu vực nội dung trong file `main.py` trên các nhánh khác nhau.

Kết quả:

* Hệ thống phát hiện Merge Conflict.
* Thực hiện Resolve Conflict thủ công.
* Hoàn tất Merge thông qua Terminal.

#### Pull Request #3 – Revert/Rollback

Thực hiện hoàn tác một commit lỗi bằng lệnh `git revert` sử dụng mã hash của commit.

Kết quả:

* Hoàn tác thay đổi thành công.
* Không làm mất lịch sử commit.
* Tạo thêm một commit mới ghi nhận quá trình hoàn tác.

---

### 3.4. Xử lý Merge Conflict

#### Tình huống

Trong quá trình hợp nhất nhánh tại Pull Request #2, Git phát hiện hai nhánh cùng chỉnh sửa một vị trí trong file `main.py`, dẫn đến xung đột và không thể tự động merge.

#### Cách xử lý

* Mở trực tiếp file phát sinh xung đột.
* Xóa các ký hiệu:

  * `<<<<<<<`
  * `=======`
  * `>>>>>>>`
* Chỉnh sửa và giữ lại nội dung mong muốn.
* Lưu file.
* Thực hiện:

  * `git add`
  * `git commit`
* Hoàn tất quá trình merge thành công trên Terminal.

---

### 3.5. Xử lý Revert / Rollback

Sau khi hoàn thành Pull Request #2, em thực hiện kiểm tra lịch sử commit và sử dụng lệnh `git revert` trên Terminal trong VS Code để hoàn tác một commit cụ thể.

Phương pháp này giúp:

* Khôi phục trạng thái ổn định của dự án.
* Không làm mất lịch sử làm việc.
* Đảm bảo khả năng theo dõi và truy vết toàn bộ thay đổi trong repository.

---

## 4. Trả lời câu hỏi: "Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?"

Khi làm việc với các công cụ AI hỗ trợ lập trình như GitHub Copilot, Cursor hoặc Codex, tốc độ sinh mã nguồn sẽ nhanh hơn rất nhiều. Vì vậy, Git đóng vai trò quan trọng trong việc kiểm soát chất lượng và quản lý lịch sử phát triển dự án.

### 4.1. Chuẩn bị môi trường

* Tạo Repository trên GitHub.
* Kết nối dự án với các công cụ AI thông qua GitHub Integration.
* Đồng bộ mã nguồn giữa môi trường phát triển và GitHub.

### 4.2. Quy trình làm việc

**Prompt → Review → Commit**

#### Bước 1: Prompt

Yêu cầu AI tạo hoặc chỉnh sửa từng tính năng nhỏ thay vì thay đổi quá nhiều nội dung cùng lúc.

#### Bước 2: Review

Kiểm tra kỹ các file được AI chỉnh sửa:

* Logic chương trình
* Cấu trúc mã nguồn
* Hiệu năng
* Bảo mật

#### Bước 3: Commit

Sau khi kiểm tra và chạy thử thành công:

```bash
git diff
git add .
git commit -m "Feat: Add Google Auth (via Vibe Code)"
```

Tiến hành lưu lại thay đổi với thông điệp commit rõ ràng và dễ theo dõi.

### 4.3. Quy tắc an toàn

* Không làm việc trực tiếp trên nhánh `main`.
* Luôn tạo nhánh tính năng riêng (`feature/*`) cho từng yêu cầu.
* Kiểm thử đầy đủ trước khi merge.
* Sử dụng Pull Request để rà soát mã nguồn trước khi đưa vào nhánh chính.
* Dễ dàng rollback nếu AI sinh ra thay đổi không mong muốn.

Git giúp đảm bảo rằng dù AI có tăng tốc quá trình lập trình, mọi thay đổi vẫn được kiểm soát, theo dõi và khôi phục một cách an toàn khi cần thiết.

---

## 5. Danh sách các lệnh Git đã sử dụng

| Lệnh                       | Mục đích                                    |
| -------------------------- | ------------------------------------------- |
| `git init`                 | Khởi tạo repository Git cục bộ              |
| `git clone <url>`          | Sao chép repository từ GitHub về máy        |
| `git status`               | Kiểm tra trạng thái hiện tại của repository |
| `git add <file>`           | Đưa file vào Staging Area                   |
| `git commit -m "message"`  | Tạo commit và lưu lại thay đổi              |
| `git push origin <branch>` | Đẩy commit từ Local Repository lên GitHub   |
| `git pull origin <branch>` | Cập nhật thay đổi mới nhất từ GitHub        |
| `git log`                  | Xem lịch sử commit                          |
| `git branch`               | Xem danh sách branch                        |
| `git checkout <branch>`    | Chuyển đổi giữa các branch                  |
| `git merge <branch>`       | Hợp nhất branch                             |
| `git diff`                 | So sánh các thay đổi trong mã nguồn         |
| `git revert <commit_hash>` | Hoàn tác commit bằng cách tạo commit mới    |
| `git remote -v`            | Kiểm tra Remote Repository                  |

---

## 6. Kết luận

Em đã hoàn thành đầy đủ các yêu cầu của khóa học Git Foundations, bao gồm thực hành quản lý repository, commit, branch, merge, pull request, xử lý conflict và revert commit.

Toàn bộ minh chứng thực hiện được lưu trữ trong repository GitHub cá nhân và được trình bày chi tiết trong file README.md.

Thông qua khóa học, em đã nắm được quy trình làm việc cơ bản với Git/GitHub và sẵn sàng áp dụng các kỹ năng này trong giai đoạn học tập tiếp theo với Vibe Code và các công cụ AI hỗ trợ lập trình.
