
province = ['dn','cx','st','sx'] # tổng hợp tất cả item
pro_today = ['dn', 'cx'] # item xuất hiện mỗi ngày
cp = ['vt','dd', 'bl','tth'] # cú pháp
vd 1:
string = "dn90!# 221 bl200dn30bl100dn40dd100"

vd 2:
string = "dn9044 221zz bl 100 st10bly50x"

giải đáp vd1:
 Người dùng sẽ nhập string vào input
1. Loại bỏ hết tất cả các ký tự
2. Lọc 'dn' dò tìm trong province và today nếu có chạy tiếp ('dn' là 1 vd người dùng có thể nhập bất cứ thứ gì)
nếu none báo lỗi (ngay vị trí none vd: nhập 'cc') => báo 'cc' không tồn tại
 - case 1: nếu none báo error "không có trong provice"
 - case 2: có trong province nhưng ko có trong pro_today
3. Lọc 'bl' dò tìm trong cp nếu none báo lỗi (ngay vị trí none vd: nhập 'cc') => báo 'cc' không tồn tại => nhập lại

4. lấy độ dài len(vd:90) == 2 và len() == 3: nếu hơn báo lỗi  (ngay vị trí lỗi vd: phát hiện lỗi ở 9999)
5. Lọc cú pháp 'bl' dò tìm trong cp nếu none báo lỗi (ngay vị trí none vd: nhập 'cc') => báo 'cc' không tồn tại => nhập lại
6. Bắt buộc trước cú pháp vd:'bl' Cuối cùng trong string là số (mệnh giá thành tiền)

giải vd2:
- báo lỗi ngay 9044 (vì có 4 chữ số)
- báo lỗi ngay "zz"
- báo lỗi "y" ngay "bly" vì không có trong list cú pháp 'bl'
- báo lỗi "x" ngay "50x" vài không phải là số

Kết quả cuối cùng sau khi lọc và so sánh trong string 
là array hoặc dict hoặc json để insert vào odoo
KQ Vd1:
{'1key': ['90', '221', 'bl', '200'], '2key': ['30', 'bl', '100'], '3key': ['40', 'dd', '100']}
KQ Vd2:
{'1key': ['90', '221', 'bl', '100'], '2key': ['30', '10','bl','100']}
