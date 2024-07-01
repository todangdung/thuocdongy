**Định nghĩa git và github**

**Git**: (hệ thống quản lý phiên bản code)

- **Khái niệm**: Git là một hệ thống quản lý phiên bản code
- **Chức năng**: Theo dõi và quản lý các thay đổi trong code của dự án theo thời gian. Giúp chúng ta lưu lại các phiên bản của code, quay lại phiên bản trước đó, và làm việc song song với nhiều nhánh (branch).
- **Đặc điểm**: Hoạt động chủ yếu trên máy tính cá nhân của bƯạn. Mọi người có thể làm việc độc lập và sau đó hợp nhất các thay đổi của họ lại với nhau.

**GitHub**: (máy chủ lưu trữ code (giống google drive))

- **Khái niệm**: GitHub là một nền tảng dịch vụ trực tuyến để lưu trữ các repo (kho) Git.
- **Chức năng**: Cho phép ta lưu trữ, chia sẻ và quản lý mã nguồn của mình trên internet. Cung cấp các công cụ bổ trợ như issue tracking, pull requests, review code, và nhiều tính năng khác để hỗ trợ quá trình phát triển phần mềm.
- **Đặc điểm**: Tập trung vào làm việc nhóm, giúp các developers có thể cùng code trên một dự án.

**Định nghĩa repo remote và repo local (kho lưu trữ code trên server github và kho lưu trữ code trên máy tính cá nhân)**

**Repo Local**:

- **Khái niệm**: Là kho lưu trữ Git trên máy tính cá nhân của bạn.
- **Chức năng**: Bạn thực hiện các thao tác như commit, branch, merge, và các lệnh Git khác tại đây.
- **Đặc điểm**: Chỉ có bạn mới có quyền truy cập và thay đổi nội dung trong repo local của mình.

**Repo Remote**:

- **Khái niệm**: Là kho lưu trữ Git nằm trên một máy chủ hoặc dịch vụ lưu trữ trực tuyến (như GitHub).
- **Chức năng**: Được sử dụng để lưu trữ và chia sẻ code với người khác. Bạn có thể push (đẩy) các thay đổi từ repo local (repo code trên máy tính cá nhân) lên repo remote (repo code trên github), và pull (kéo) các thay đổi từ repo remote về repo local.
- **Đặc điểm**: Cho phép nhiều người cùng truy cập cùng code. Repo remote thường được sử dụng để lưu trữ code và làm việc nhóm.

**Một số trạng thái (states) của Git:**

1. **Untracked**:
   - **Khái niệm**: Các tệp mới được thêm vào thư mục dự án nhưng chưa được theo dõi bởi Git.
   - **Đặc điểm**: Chưa có trong hệ thống quản lý phiên bản của Git. Bạn cần thêm chúng vào vùng staged để bắt đầu theo dõi.
2. **Unmodified**:
   - **Khái niệm**: Các tệp đã được theo dõi bởi Git và không có thay đổi nào kể từ lần commit cuối cùng.
   - **Đặc điểm**: Không có sự khác biệt so với phiên bản đã được commit gần nhất.
3. **Modified**:
   - **Khái niệm**: Các tệp đã được thay đổi nhưng chưa được thêm vào vùng staged.
   - **Đặc điểm**: Có sự khác biệt so với phiên bản đã được commit gần nhất nhưng chưa được chuẩn bị để commit.
4. **Staged**:
   - **Khái niệm**: Các tệp đã được thay đổi và đã được thêm vào vùng staged (vùng chuẩn bị) để chuẩn bị cho việc commit.
   - **Đặc điểm**: Sẵn sàng để được commit vào repo. Bạn có thể thực hiện lệnh git add để thêm tệp vào trạng thái này.
5. **Committed**:
   - **Khái niệm**: Các thay đổi đã được lưu lại trong lịch sử của Git thông qua lệnh git commit.
   - **Đặc điểm**: Thay đổi này đã được lưu trữ trong repo local và trở thành một phần của lịch sử phiên bản.

### **Quy trình làm việc thông thường trong Git:**

1. **Thêm tệp mới hoặc chỉnh sửa tệp hiện có**: Tệp mới sẽ ở trạng thái "untracked", tệp chỉnh sửa sẽ ở trạng thái "modified".
2. **Thêm tệp vào vùng staged**: Sử dụng lệnh git add để đưa tệp vào trạng thái "staged".
3. **Commit các thay đổi**: Sử dụng lệnh git commit để lưu các thay đổi vào repo, tệp sẽ ở trạng thái "committed".
4. **Đẩy (push) commit lên repo remote**: Sử dụng lệnh git push để đẩy các commit từ repo local lên repo remote (ví dụ: GitHub).

**Các lệnh git thường dùng:**

- **git add**: Thêm thay đổi vào vùng staged.
- **git commit**: Lưu thay đổi vào lịch sử repo.
- **git status**: Kiểm tra trạng thái các tệp.
- **git push**: Đẩy commit lên repo remote.
- **git merge**: Hợp nhất các nhánh.
- **git reset**: Quay lại trạng thái trước đó của repo.

**Chi tiết:**

- **git add**:

**Chức năng**: Thêm tệp hoặc thay đổi vào vùng staged để chuẩn bị commit.

**Cú pháp**:  
git add .

- **git commit**:

**Chức năng**: Lưu các thay đổi đã staged vào lịch sử của repo.

**Cú pháp**:  
git commit -m "Thông điệp commit"

- **git status**:

**Chức năng**: Hiển thị trạng thái của các tệp trong thư mục làm việc, bao gồm các tệp đã được staged, các tệp đã thay đổi nhưng chưa staged, và các tệp untracked.

**Cú pháp**:  
git status

- **git push**:
- **Chức năng**: Đẩy các commit từ repo local lên repo remote.

**Cú pháp**:  
git push origin main

- **git merge**:

**Chức năng**: Hợp nhất các nhánh lại với nhau.

**Cú pháp**:  
git merge &lt;tên_nhánh&gt;

Ví dụ, hợp nhất nhánh feature vào nhánh hiện tại:  
git merge feature

- **git reset**:

**Chức năng**: Quay lại một trạng thái trước đó của repo, có thể thay đổi vùng staged và vùng làm việc.

**Cú pháp**:

Để reset vùng staged về commit trước đó:  
git reset HEAD~1

Để reset cả vùng làm việc (cẩn thận với lệnh này vì nó có thể làm mất thay đổi):  
git reset --hard HEAD~1

Để quay trở lại commit trước đó:  
git reset &lt;id_commmit&gt;
