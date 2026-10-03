## nội dung cho commit lần đầu - Upload tính năng quan trọng 1

**2.1. Sửa đổi commit gần nhất (git commit --amend)**
Tùy chọn --amend cho phép bạn ghi đè trực tiếp lên commit mới nhất của nhánh hiện tại. Lệnh này thường dùng để:

Sửa đổi nội dung tin nhắn của commit vừa tạo.
Bổ sung thêm các tệp tin bị quên vào commit vừa tạo mà không làm phát sinh thêm commit rác trong lịch sử.
(Lưu ý: Chỉ nên sử dụng --amend đối với các commit local chưa được push lên remote).

**2.2. Phục hồi lịch sử: Git Reset vs Git Revert**
Khi muốn hủy bỏ các thay đổi đã commit, Git cung cấp hai giải pháp với triết lý khác nhau:

**Git Reset (Xóa lịch sử): Di chuyển con trỏ nhánh hiện tại lùi lại về một commit chỉ định trong quá khứ. Có 3 chế độ hoạt động chính:**
--soft: Chỉ di chuyển con trỏ nhánh. Toàn bộ thay đổi của các commit bị hủy vẫn được giữ lại tại Staging Area.
--mixed (Mặc định): Di chuyển con trỏ nhánh và dọn dẹp Staging Area. Toàn bộ thay đổi của các commit bị hủy sẽ được giữ lại tại Working Directory dưới dạng tệp tin chưa được add.
--hard (Nguy hiểm): Di chuyển con trỏ nhánh, xóa sạch toàn bộ thay đổi ở cả Staging Area và Working Directory. Lịch sử và mã nguồn bị xóa bỏ triệt để.
Git Revert (Đảo ngược lịch sử): Không xóa bỏ commit cũ, mà tạo ra một commit mới có nội dung hoàn toàn đối lập/đảo ngược với commit được chỉ định. Lịch sử cũ được giữ nguyên, đảm bảo an toàn tuyệt đối khi làm việc nhóm trên các nhánh chung đã push lên remote.

## Nội dung bổ sung cho commit thứ 2 - upload nội dung quan trọng thứ 2
**Trạng thái Detached HEAD**
- Bình thường, con trỏ HEAD sẽ trỏ vào con trỏ của một nhánh (như main). 
Tuy nhiên, khi bạn checkout trực tiếp đến một commit hash cụ thể (git checkout <commit_hash>), 
HEAD sẽ trỏ trực tiếp đến commit đó thay vì con trỏ nhánh. Trạng thái này gọi là Detached HEAD (HEAD bị tách rời). 
Ở trạng thái này, bạn có thể chạy thử nghiệm hoặc sửa đổi code tạm thời, nhưng nếu bạn tạo commit mới tại đây, 
các commit đó sẽ không thuộc về nhánh nào và dễ bị Git tự động dọn dẹp khi bạn checkout sang nhánh khác.