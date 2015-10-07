# Thao-tac-voi-he-thong-trong-linux
Thao tác với hệ thống trong linux


#1 Đăng nhập.

- Sau khi hệ thống Linux khởi động xong, người dùng có thể đăng nhập vào hệ thống để bắt đầu làm việc. Tùy theo giao diện đồ họa hay giao diện văn bản, người sử dụng sẽ phải khai báo thông tin tài khoản(ở đây mình làm trên ubuntuserver nên chỉ có giao diện văn bản):

<img src="http://prntscr.com/8onjgv">

- Dòng thứ nhất cho biết loại phiên bản Linux, phiên bản của nhân và kiến trúc phần cứng có trên máy, dòng thứ hai là dấu nhắc lệnh đăng nhập, để người dùng thực hiện việc đăng nhập. Chú ý là dòng trên đây có thể thay đổi chút ít tùy thuộc vào phiên bản Linux.

- Tại dấu nhắc lệnh đăng nhập, nhập tên người dùng (còn gọi là tên đăng nhập): đây là tên ksi hiệu đã cung cấp cho Linux nhằm nhận diện một người dùng cụ thể. Tên đăng nhập ứng với mỗi người dùng trên hệ thống là duy nhất, kèm theo một mật khẩu đăng nhập.

<img src="http://prntscr.com/8onkxw">

- Khi đăng nhập xong tên đăng nhập hệ thống sẽ yêu cầu mật khẩu. Mật khẩu khi nhập sẽ không hiển thị trên màn hình và chính điều đó giúp chánh sự "nhòm ngó" của người khác.

#2. Thoát khỏi hệ thống

- Để kết thúc phiên làm việc người dùng cần thực hiện thủ tục sau khi ra khỏi hệ thống. Có rất nhiều cách cho phép thoát khỏi hệ thống, các đơn giản nhất để đảm bảo thoát khỏi hệ thống đúng đắn là ấn tổ hợp phím **CTRL+ALT+DEL**. Khi đó, trên màn hình sẽ hiển thị một số thông báo của hệ thống và cuối cùng là thông báo trước khi tắt máy. Cần chú ý là: Nếu đang làm trên môi trường X Window System, hãy ấn tổ hợp phím **CTRL+ALT+BACKSPACE** trước rồi sau đó hãy nhấn **CTRL+ALT+DEL**.
- Ngoài ra có thể sử dụng cú pháp sau:

**#shutdown [tùy_chọn] <time> [cảnh_báo]**

Lệnh này cho phép dừng tất cả các dịch vụ đang chạy trên hệ thống.
Các tùy chọn của lệnh này như sau:
<ul>
<li>-k: không thực sự shutdown mà chỉ cảnh báo.</li>
<li>-r: khởi động lại ngay khi shutdown.</li>
<li>-h: tắt máy thực sự ngay sau khi shutdown.</li>
<li>-f: khởi động lại nhanh và bỏ qua việc kiểm tra đĩa.</li>
<li>-F: khỏi động lại và thực hiện việc kiểm tra đĩa.</li>
<li>-c: bỏ qua không chạy lệnh shutdown. Trong tùy chọn này không thể đưa ra tham số thời gian nhưng có thể đưa ra thông báo giải thích trên dòng lệnh gửi cho tất cả các người dùng.</li>
<li>- t: quy định init(8) chờ khoảng thời gian số-giây tạm dừng giữa quá trình gửi và cảnh báo tính hiệu kill, trước khi chuyển sang một mức chạy khác, và hai tham số vị trí còn lại:
time: đặt thời điểm shutdown. Tham số time có hai dạng. Dang tuyệt đối là gg:pp(gg giờ trong ngày,pp: phút) thì hệ thống sẽ shutdown khi đồng hồ máy trùng với giá trị tham số. Dang tưng đối +<số> là hẹn sau khoảng <số> phút sẽ shutdown, coi shutdown lập tức tương đương với +0
cảnh báo: thông báo gửi đến tất cả người dùng trên hệ thống. Khi lệnh thực hiện tất cả các máy người dùng đều nhận được cảnh báo.</li>
</ul>

Ví dụ, khi người dùng gõ lệnh:

**#Shutdown +1 "He thong se tat sau 1 phut nua de bao tri"**

- Trên màn hình của tất cả người dùng xuất hiện thông báo "He thong se tat sau 1 phut nua de bao tri" và sau 1 phút toàn bộ hệ thống sẽ shutdown.

#halt [tùy_chọn]

- Lệnh này tắt hẳn máy, Tùy chọn:
<ul>
<li>-w: không thực sự tắt máy nhưng vẫn ghi các thông tin lên file /var/log/wtmp(đây là file lưu trữ danh sách người dùng đăng nhập thành công vào hệ thống).</li>
<li>-d: không ghi lưu thông tin lên file /var/log/wtmp. Tùy chọn -n có nghĩa tương tự song không tiến hành việc đồng bộ hóa.</li>
<li>-f: thực hiện tắt máy ngay mà không thực hiện lần lượt việc dừng các dịch vụ có trên hệ thống.</li>
<li>-i: chỉ thực hiện dừng tất cả các dịch vụ mạng trước khi tắt máy.</li>
</ul>

#1.3. Khở động lại hệ thống

- Ngoài việc thoát khỏi hệ thống nhờ cách thức trên đây (ấn tổ hợp ba phím **CTRL+ALT+DEL**, dùng lệnh **shutdown**, lệnh **halt**), khi cần thiết(chẳng hạn, gặp phải tình huống một trình ứng dụng chạy quẩn) có thể khởi động lại hệ thống nhờ lệnh reboot.
- Cú pháp lệnh **reboot**:

**#reboot [tùy_chọn]**

- Lệnh này cho phép khởi động lại hệ thống. Nói chung thì chỉ siêu người dùng (Super user) mới được phép sử dụng lệnh reboot, tuy nhiên, nếu hệ thống chỉ có duy nhất một người dùng đang làm việc thì lệnh reboot vẫn được thực hiện song hệ thống sẽ đòi hỏi việc xác nhận mật khẩu.
- Các tùy chọn của lệnh reboot tương tự như trong lệnh halt.

#1.4. Các chế độ khởi động

- Linux cho phép khởi động từ 6 chế độ khác nhau:

| Chế độ (Run Level) | Trường hợp sử dụng(Common Usages) |
|--------------------|-----------------------------------|
| 0 | Tắt máy - shutdown |
| 1 | Chế độ 1 người dùng - Single user |
| 2 | Chế độ đa người dùng - không hỗ trợ Network |
| 3 | Chế độ đa người dùng - có hỗ trợ Network |
| 4 | Chưa sử dụng  |
| 5 | Chế động đa người dùng, Network, Graphic |
| 6 | Restart |

- Cú pháp:

**#init [Run Level]**

Ví dụ:

- Để vào chế độ Graphic ta chọn: #init 5
- Để vào chết độ Text mode đã người dùng ta chọn: #init 3
- Trong quá trình khởi động, mặc định init sẽ chạy tập tin /etc/inittab ở chế độ 3. Bạn chó thể chỉnh sửa chế độ khỏi động trong tập tin này. Trong mỗi thư mục /etc/rc.d/rcX.d sẽ lưu trữ các file, mỗi file này là 1 script mà nếu tên file bắt đầu bằng chữ K có nghĩa là file này không được kích hoạt, nếu bắt đầu bằng chứ S thì file này sẽ được kích hoạt trong chế độ đó.

#1.5. Xem và thiết lập ngày, giờ

- Lệnh date cho phép có thể xem hoặc thiết lập đặt lại ngày giờ hệ thống:

- Cú pháp của lệnh gồm 2 dạng, dạng xem thông tin về ngày, giờ:

**#date [tùy_chọn] []**
