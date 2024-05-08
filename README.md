# Hướng dẫn sử dụng Blynk-Gate

## I. Tổng quan
### 1. Giới thiệu về Blynk và phần cứng Blynk-gate

* Blynk là một nền tảng IoT cung cấp các công cụ để kết nối, quản lý và điều khiển các thiết bị IoT từ xa thông qua mạng Internet. Điểm nổi bật của Blynk là sự dễ dàng và nhanh chóng trong việc tạo và quản lý các ứng dụng IoT, phù hợp cho cả những người mới bắt đầu và những nhà phát triển chuyên nghiệp.
* Bằng cách sử dụng phần cứng **Blynk Gate** người dùng không cần phải code mà chỉ cần thao tác tùy chỉnh cơ bàn là đã có thể tạo ra 1 thiết bị điều khiển từ xa thông qua intermet.

### 2. Sơ đồ mạch Blynk-gate
![matduoi](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/1507de73-6f29-4fd8-aa7c-7b45e1d4090c) Mặt dưới
![mattren](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/5cc9af8d-e3fc-4ef9-b19e-165efc1bb5e4) Mặt trên

### 3. Chức năng các chân trên mạch
* 5V: Chân cấp nguồn dương 5V
* GND: Chân cấp nguồn âm 0VDC
* SDA: Chân truyền nhận tín hiệu I2C  
* SCL: Chân tín hiệu xung nhịp I2C
* P1 -> P4: Chân OUTPUT điều khiển thiết bị 
* *Lưu ý: Khi chân J1 không được hàn thì chân SDA, SCL có chức năng giao tiếp I2C, nếu chân J1 được hàn lại thì 2 chân SDA, SCL sẽ không còn chức năng giao tiếp I2C mà sẽ là 2 chân OUTPUT tín hiệu giống như các chân P1 -> P4.*
## II. Hướng dẫn tạo tài khoản Blynk
### 1. Tạo tài khoản trên trang web

#### **Bước 1**: PC/ Laptop: Truy cập link Blynk: <https://blynk.io/> 

#### **Bước 2**: Bấm vào nút 'LOGIN'
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/c41eea17-b07d-42d1-b303-017ccd42c7b3)

#### **Bước 3**: Chọn Create new acccount 
-	Tiến hành nhập Email và mật khẩu để tạo tài khoản mới ![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/2ca5597e-1ec6-4327-b934-72867b796e6e)

## III.	  Hướng dẫn sử dụng Blynk – gate để bật tắt đèn Led
### 1. Setup phần cứng Blynk-gate

### 2.	Setup trên Blynk

#### **Bước 1**: Tại giao diện chính của Blynk, chọn `For Makers`
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/28bdf82e-1111-42fc-ae09-bf5a5547dba1)

#### **Bước 2**: Thiết lập một template mới dùng để điều khiển dự án đèn Led tắt bật theo ý muốn, ấn chọn `New template`
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/793762ee-da51-447b-8f99-b2475433616a)

<img align="right" height="300" width="460" src="https://github.com/ainguyn/blynkgatetutorial/assets/167832348/f03f84b7-0b3a-42ca-922a-3c21b1469395">          

#### **Cách tạo một template mới**
* Name: Đặt tên bất kì cho template.
* Hardware: Chọn mặc định ESP8266.
* Connection Type: Wifi.
* Description: Phần mô tả chi tiết thêm cho template.

----------------------------------------------------------

#### Bước 3: Sau khi đã tạo một template mới, cần thiết lập các Datastreams (các chân Virtual Pin) 
 ![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/f3e1b0c3-c97b-4dba-8b21-193193ffa2bf)

Chọn New Datastream -> Virtual Pin
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/90384950-513b-409e-b34a-538b2af2fc1a)

Khai báo Datastrean Virtual Pin tương tự như ảnh cho chân P1 và làm tương tự với các chân kế tiếp (P2, P4)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/c0c53dd1-01d2-439c-b03c-30ff5d4e486f)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/c980fcd9-be5f-4b02-acad-cd0e18fa8e33)

Riêng chân P3 sẽ khai báo giống ảnh
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/7b6f0d7c-ead9-4512-99f0-240da37bdc12)


#### **Bước 4**: Sau khi đã tạo được các Datastreams, chúng ta sẽ kéo thả nó vào `Web Dashboard`, đây sẽ là nơi dùng để tùy chỉnh giao diện điều khiển các Virtual Pin Datastreams đã setup ở bước trước
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/dd740114-28c4-461a-b386-6277a3740a8c)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/5b238417-17f9-4fb4-9011-4284bb671b40)

<img align="right" src="https://github.com/ainguyn/blynkgatetutorial/assets/167832348/bb6e79bd-177d-4e1f-bd3a-0f67fc3cc555">

+ Để bật tắt thiết bị, chúng ta chọn hộp lệnh `Switch` trong nhóm lệnh Control rồi kéo thả vào giao diện điều khiển hoặc click chuột trái 2 lần vào hộp lệnh.
+ Di chuyển con chuột tới hộp lệnh đã đặt trong phần giao diện và ấn vào biểu tượng bánh răng, khi đó sẽ hiện lên bảng `Switch Settings` dùng để thiết lập nút lệnh này với các Datastreams Virtual Pin đã tạo ở bước trước.


+ Tittle: Đặt tên tùy ý cho nút lệnh
+ Datastream: Chọn Datastream muốn điều khiển và ấn save
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/f86f2600-f099-41dd-b9c7-a8611a6b7fb9)

Bước 7: Quay về thẻ Home và nhấn `Add first device` để đặt tên cho thiết bị điều khiển và hoàn tất thiết lập.

 ![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/ca90f2de-159a-433e-b781-7003bdaa3542)

## 3. Thiết lập Blynk trên điện thoại:
IOS/Android: Truy cập “App Store” /” Google Play” và tải app “Blynk IoT”
- Sau khi tải app, chúng ta đăng nhập vào tài khoản đã tạo ở trang web, khi đó tên thiết bị đã tạo trên web sẽ hiển thị sẵn trên màn hình
- Ấn vào tên thiết bị để vào giao diện điều khiển, sau đó chọn vào biểu tượng cờ lê như hình
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/0e3bec24-8256-4d54-ac31-7ac54e77eb7c)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/8f9e8424-6cb7-419f-b2c1-e77f9a78ee90)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/90be3773-2c38-49ed-873d-77e9ef5f7c62)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/b87a0d3d-45ac-4cb3-aec8-474ad6bb883f)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/efa0ed59-2441-48b6-b963-b76f0b8538b8)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/296bd0d5-a690-47c8-906a-ad580c5c8758)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/21b996d4-2cf9-49ed-8366-f940bce88cea)

-	Chọn Button (Công tắc) để điều khiển đèn tắt mở và có thể kéo thả đến vị trí tùy ý

- Sau khi ấn button, màn hình sẽ hiện ra giao diện giống hình 5, ấn vào nút lệnh lần nữa để thiết lập nó với các Datastream Virtual Pin đã tạo trước đó

 
## IV.	 Hướng dẫn kết nối Blynk – gate với Blynk app (Demo)
	Note: Truy cập Wifi Blynk gate trước rồi mới vào địa chỉ IP, mạng Wifi khai báo là 2.4G
-	Sau khi hoàn tất setup Blynk app, chúng ta sẽ có được `Blynk_Auth_Token` dùng để kết nối với Blynk – gate

(Nếu không thấy `Blynk_Auth_Token`, tại giao diện chính dùng để điều khiển, ấn vào biểu tượng `Developer Tools` như hình)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/43c24c75-1ccb-4dc1-912e-6d7233fe04db)
![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/27b04478-f945-4917-9cca-d93a8ab0bc0f)

Ấn `Click to copy` như ảnh để copy `Blynk_Auth_Token`
-	 Ấn giữ nút `Set` trên Blynk – gate khoảng 10s cho tới khi thấy đèn xanh trên Blynk – gate chớp nhanh liên tục để reset toàn bộ dữ liệu.
- Truy cập vào wifi “Blynk gate” trên máy tính và vào địa chỉ IP: `192.168.4.1`
  ![image](https://github.com/ainguyn/blynkgatetutorial/assets/167832348/4d7d88fd-636b-4bd1-8f44-67c43f5ebb6c)
   + WiFi (2.4G) SSID:
   + Password:
   + Auth token: Paste `Blynk_Auth_Token` đã copy trước đó vào
- Sau khi đã khai báo như ảnh thì ấn `Apply`, máy tính sẽ kết nối với Blynk – gate (Để ý đèn xanh trên Blynk – gate chớp nhanh vài giây và sáng  sau kết nối nghĩa là kết nối thành công)
- Sau khi kết nối thành công, Blynk – gate sẽ tự động ngắt wifi trên máy tính. Vào lại wifi khác và truy cập Blynk web để tiến hành điều khiển

   

