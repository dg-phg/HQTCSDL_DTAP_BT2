# HQTCSDL_DTAP_BT2
## Thông tin sinh viên:
+ **Họ và tên:** Dương Thị Anh Phương 
+ **Mã sinh viên:** K235480106056
+ **Lớp:** K59.KMT.K01
+ **Trường:** Đại học Kỹ thuật Công nghiệp Thái Nguyên

---
## BÀI TẬP SỐ 2
### Phần 1: Thiết kế và khởi tạo Cấu trúc dữ liệu 
#### 1. Chọn chủ đề quản lý: _Quản lý khách sạn_
   
1.1 Khởi tạo Database với tên dự án và Mã Sinh Viên: `QuanLyKhachSan_K235480106056`
   
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6b42166e-1fc8-4757-af0d-2cd10915d173" />

   1.2 Tạo bảng Khách hàng 
   
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/79cc4800-92d6-4776-b2c8-3957976ac4b0" />

+ PK: [MaKhachHang]
  
=> Cấu trúc bảng `KhachHang` với các kiểu dữ liệu Unicode và Số thực

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bb34265d-3d78-425a-bea7-2995a7bdf3db" />

   1.3 Tạo bảng `Phong`
   
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/22a59b1e-6834-4a71-9a66-63f3cea9ec29" />

+ PK: [MaPhong]
  
+ CK: [GiaTheoNgay]
  
=>Cấu trúc bảng `Phong` với kiểu dữ liệu Tiền tệ và mã phòng kiểu Chuỗi

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9d4b8c29-b7d2-4a9f-847c-a89509eafe8f" />

   1.4 Tạo bảng `DatPhong`và thêm các khóa liên kết tới 2 bảng trên
   
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4f00099c-4381-4016-90b4-fe2302e0046a" />

PK: [MaDatPhong]

FK: [MaKhachHang] ; [MaPhong]

CK: [CK_ThoiGian]

=> Cấu trúc bảng [DatPhong] và thiết lập các mối liên kết

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5993ec3f-d46f-4b92-9b7f-e6cdeb97d093" />

#### Giải thích các ràng buộc dữ liệu:

+ Khóa chính (Primary Key - PK):

[MaKhachHang], [MaDatPhong]: Là các số nguyên tự động tăng (IDENTITY), giúp định danh duy nhất mỗi khách hàng và mỗi lượt đặt phòng.

[MaPhong]: Dùng mã định danh dạng chuỗi (ví dụ: 'P101') để quản lý phòng theo sơ đồ thực tế.

+ Khóa ngoại (Foreign Key - FK):

Bảng [DatPhong] chứa hai khóa ngoại là [MaKhachHang] và [MaPhong]. Điều này tạo ra mối quan hệ: "Một khách hàng có thể đặt nhiều phòng" và "Một phòng có thể được đặt bởi nhiều khách hàng tại các thời điểm khác nhau".

+ Ràng buộc kiểm tra (Check Constraint - CK):

[CK_GiaPhong]: Đảm bảo trường [GiaTheoNgay] luôn phải lớn hơn 0, tránh nhập liệu sai về tài chính.

[CK_ThoiGian]: Đảm bảo [NgayTraPhong] không được trước [NgayNhanPhong], logic nghiệp vụ bắt buộc trong quản lý khách sạn.

1.5 Sơ đồ `Database Diagram` của hệ thống _Quản lý Khách sạn_, thể hiện trực quan các `Khóa chính` (PK - Chìa khóa vàng) và các đường liên kết `Khóa ngoại` (FK) giữa 3 bảng.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb43b616-a0ab-4f44-9fe9-5efa1bbe34cf" />


  
