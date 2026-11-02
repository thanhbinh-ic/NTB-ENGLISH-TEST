# NTB English Test

Trang web kiểm tra và ôn tập tiếng Anh theo loạt bài “13 thì tiếng Anh” của kênh I LOVE IELTS.
Trang tĩnh, không cần máy chủ, không cần lệnh build.

**AI Roleplay Simulator** is an interactive text adventure game where Artificial Intelligence acts as your personal "Dungeon Master." The system dynamically generates worlds, characters, and branching storylines based on your unique creative inputs, offering a limitless storytelling experience.

[![Vercel App](https://img.shields.io/badge/LIVE_DEMO-VERCEL_APP-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://ntbenglish.vercel.app)

## Trang chủ

Trang chủ có hai phần:

- **Ôn tập**: làm bài tập theo từng bài, không tính giờ, được chuyển tab.
- **Làm bài kiểm tra**: bài kiểm tra tổng hợp, 60 phút, 40 câu.

## Ôn tập

- **Bài 1 — Thì hiện tại đơn**: 32 câu (20 trắc nghiệm, 9 viết/sắp xếp câu, 3 đọc hiểu).
- **Bài 2 — Thì hiện tại tiếp diễn**: 20 câu (13 trắc nghiệm, 3 viết, 2 sắp xếp câu, 2 đọc hiểu).

Ôn tập dùng cùng giao diện làm bài với kiểm tra: chọn đáp án, viết câu,
chuyển câu bằng nút hoặc phím mũi tên, nộp bài rồi xem điểm và đáp án.
Ôn tập không tính giờ và được chuyển tab, nhưng vẫn chặn copy và xem mã nguồn.
Nộp bài ôn tập luôn hiện đáp án, kể cả khi chưa trả lời hết câu.

Nguồn học:

- Bài 1 — Thì hiện tại đơn: https://youtu.be/BmKkDuO_nkk
- Bài 2 — Thì hiện tại tiếp diễn: https://youtu.be/dIIG9m649-g

Câu hỏi do tôi soạn mới theo các điểm ngữ pháp của bài giảng,
không sao chép nguyên văn bài tập trong video.

## Kiểm tra

- 3 đề khác nhau, mỗi đề 40 câu: 20 câu hiện tại đơn + 20 câu hiện tại tiếp diễn.
- Mỗi bài trong một đề gồm 14 trắc nghiệm, 3 câu viết, 3 câu sắp xếp.
- Mỗi lần bấm làm kiểm tra, hệ thống chọn ngẫu nhiên một trong 3 đề,
  rồi xáo trộn thứ tự câu hỏi và thứ tự đáp án.
- Câu hỏi kiểm tra viết mới hoàn toàn, không trùng câu ôn tập.
- Thời gian 60 phút, đếm ngược, còn 10 phút chuyển vàng, còn 1 phút chuyển đỏ,
  hết giờ tự nộp bài.
- Nộp bài khi chưa trả lời hết câu thì chỉ hiện điểm và thời gian, không hiện
  đáp án và lý do sai. Ngoại lệ: tài khoản admin vẫn xem đủ đáp án.

## Cơ chế trong lúc làm kiểm tra

- Chống copy: chưa đăng nhập thì không chọn, copy, cắt văn bản và không mở
  menu chuột phải; vẫn gõ và sửa được trong ô trả lời.
- Chặn phím tắt xem mã nguồn trong lúc làm bài: F12, Ctrl+Shift+I/J/C,
  Ctrl+U, Ctrl+S.
- Chống gian lận dùng chung một bộ đếm: đổi tab, thu cửa sổ xuống nền,
  mất tiêu điểm, đổi kích thước cửa sổ (chỉ tính khi chiều rộng đổi trên 200px).
  Lần 1 cảnh báo, lần 2 nộp bài ngay. Tín hiệu cách nhau dưới 2 giây chỉ tính
  một lần. Admin được miễn cơ chế chống gian lận.
- Chuyển câu bằng phím mũi tên trái/phải, trừ khi đang gõ trong ô nhập,
  đang chọn đáp án hoặc đang mở hộp thoại.

## Đăng nhập

Nút “Đăng nhập” ở góc phải dùng để đăng nhập tài khoản admin. Khi đã đăng nhập, trong lúc làm bài sẽ hiện đáp án đúng của từng câu
để test hệ thống. Trạng thái đăng nhập chỉ lưu theo phiên trình duyệt.

Lưu ý: đây là trang tĩnh, repo công khai, đáp án nằm trong mã nguồn trang,
nên đăng nhập admin chỉ là lớp hiển thị để test, không phải bảo mật thật.
Đổi mật khẩu bằng cách thay mã băm SHA-256 trong `index.html` trước khi
chia sẻ rộng rãi. Chặn xem mã nguồn trên trang tĩnh cũng chỉ là lớp ngăn nhanh,
không chặn được menu trình duyệt, `view-source:` hay tải file về.

## Tải lại trang và kết quả

Tải lại trang giữa chừng sẽ mất bài và đồng hồ chạy lại từ đầu.
Kết quả chỉ tính trên trình duyệt đang dùng, không lưu lên máy chủ.

## Cấu trúc file

- `index.html`: giao diện, bộ máy làm bài, câu ôn tập Bài 1.
- `data.js`: câu ôn tập Bài 2 và 3 đề kiểm tra.

## Deploy lên Vercel

Import repo này trên Vercel, chọn dạng trang tĩnh, không cần lệnh build,
thư mục gốc để mặc định, bấm Deploy.
