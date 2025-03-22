---

<h1 align="center">Emotion Recognition Using CNN</h1>

<div align="center">

<p align="center">
  <img src="https://github.com/manhlinh3011/Diem-danh-bang-ma-QRCode/raw/main/images/logoDaiNam.png" alt="DaiNam University Logo" width="200"/>
  <img src="https://github.com/manhlinh3011/Diem-danh-bang-ma-QRCode/raw/main/images/LogoAIoTLab.png" alt="AIoTLab Logo" width="170"/>
</p>

[![Made by AIoTLab](https://img.shields.io/badge/Made%20by%20AIoTLab-blue?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Fit DNU](https://img.shields.io/badge/Fit%20DNU-green?style=for-the-badge)](https://fitdnu.net/)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-red?style=for-the-badge)](https://dainam.edu.vn)

</div>

<h2 align="center">Hệ thống nhận diện biểu cảm khuôn mặt theo thời gian thực</h2>

<p align="left">
  Dự án xây dựng hệ thống nhận diện biểu cảm khuôn mặt theo thời gian thực dựa trên dữ liệu landmark hoặc ảnh grayscale 48x48, sử dụng mô hình CNN và MobileNetV2. Hệ thống hiển thị biểu cảm trên giao diện và phát âm thanh tương ứng với cảm xúc được nhận diện, hỗ trợ trực quan trong các ứng dụng chăm sóc sức khỏe tinh thần, tương tác người-máy...
</p>

---

## 🌟 Giới thiệu

- **📸 Nhận diện biểu cảm thời gian thực:** Qua webcam, hệ thống phát hiện khuôn mặt, dự đoán biểu cảm như *Angry, Fear, Happy, Sad, Surprise*.
- **🔊 Phát âm thanh tương ứng:** Khi nhận diện cảm xúc, hệ thống phát lời nhắc bằng giọng nói tiếng Việt phù hợp với biểu cảm.
- **📊 Đánh giá mô hình:** Hiển thị độ chính xác, confusion matrix của mô hình CNN và MobileNetV2 trên tập test.
- **🖼️ Xử lý ảnh:** Tiền xử lý bao gồm chuyển grayscale, cân bằng histogram, resize về 48x48 và chuẩn hóa.

---

## 🏗️ QUY TRÌNH HỆ THỐNG
<p align="center">
  <img src="https://github.com/user-attachments/assets/9cb5a4a5-7735-418e-9d3a-2b047a94fc02" alt="System Flow" width="800"/>
</p>

---

## 📂 Cấu trúc dự án

📦 Project  
├── 📂 data  # Dữ liệu ảnh biểu cảm (train/test)  
├── 📂 models  # Chứa các mô hình huấn luyện (.h5)  
├── accuracy.py  # Đánh giá mô hình CNN  
├── accuracy_mobilenet.py  # Đánh giá mô hình MobileNetV2  
├── cnn_model.py  # Huấn luyện mô hình CNN  
├── mobilenet_model.py  # Huấn luyện mô hình MobileNetV2  
├── collect_data.py  # Thu thập dữ liệu từ webcam  
├── predict.py  # Dự đoán biểu cảm từ 1 ảnh tĩnh  
├── realtime_prediction.py  # Nhận diện biểu cảm thời gian thực, phát âm thanh

---

## 🛠️ CÔNG NGHỆ SỬ DỤNG

<div align="center">

### 🧠 AI & Xử lý ảnh
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?style=for-the-badge&logo=tensorflow)]()
[![Keras](https://img.shields.io/badge/Keras-DeepLearning-red?style=for-the-badge&logo=keras)]()
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-blue?style=for-the-badge)]()
[![MobileNetV2](https://img.shields.io/badge/MobileNetV2-LightweightModel-green?style=for-the-badge)]()

### 🎵 Giao diện & Âm thanh
[![Tkinter](https://img.shields.io/badge/Tkinter-GUI-yellow?style=for-the-badge)]()
[![gTTS](https://img.shields.io/badge/gTTS-TextToSpeech-purple?style=for-the-badge)]()
[![pygame](https://img.shields.io/badge/Pygame-Audio-black?style=for-the-badge)]()

</div>

---

## 🧰 Yêu cầu hệ thống

- **Python 3.x**
- **Thư viện cần cài đặt:**

```bash
pip install tensorflow keras opencv-python pillow gtts pygame seaborn scikit-learn
```

- **Camera (Webcam)** để nhận diện biểu cảm thời gian thực.

---

## 🚀 Hướng dẫn cài đặt và chạy

### 1️⃣ Thu thập dữ liệu
Chạy file để thu thập dữ liệu từ webcam:

```bash
python collect_data.py
```
- Hệ thống lưu ảnh đã tiền xử lý vào `data/train` và `data/test`.

### 2️⃣ Huấn luyện mô hình
#### Huấn luyện CNN:

```bash
python cnn_model.py
```

#### Huấn luyện MobileNetV2:

```bash
python mobilenet_model.py
```

- Mô hình sẽ được lưu vào thư mục `models/`.

### 3️⃣ Đánh giá mô hình
Đánh giá độ chính xác và confusion matrix:

```bash
python accuracy.py  # cho CNN
python accuracy_mobilenet.py  # cho MobileNetV2
```

### 4️⃣ Dự đoán ảnh tĩnh

```bash
python predict.py
```

- Nhập đường dẫn ảnh cần dự đoán → Hiển thị biểu cảm.

### 5️⃣ Nhận diện biểu cảm thời gian thực

```bash
python realtime_prediction.py
```

- Hiển thị giao diện webcam.
- Tự động phát hiện khuôn mặt, dự đoán biểu cảm và phát âm thanh tương ứng.

---

## 🎙️ Ví dụ âm thanh phản hồi
| Biểu cảm    | Phát âm thanh                                                                 |
|-------------|------------------------------------------------------------------------------|
| Angry       | "Đừng giận dữ như vậy mà. Hãy ngồi xuống và hít thở thật sâu!"               |
| Fear        | "Bạn đang sợ điều gì à?"                                                     |
| Happy       | "Có vẻ bạn có một ngày tuyệt vời nhỉ. Hãy lan tỏa nó tới mọi người nào!"     |
| Sad         | "Đừng buồn nhé. Có mình đây rồi."                                            |
| Surprise    | "Ồ, có gì làm bạn ngạc nhiên vậy?"                                           |

---

## 📊 Kết quả huấn luyện

<p align="center">
  <img src="https://github.com/user-attachments/assets/006a34f4-03cb-4717-b88e-290eb42fee15" alt="Confusion Matrix CNN" width="400"/>
  <img src="https://github.com/user-attachments/assets/e251fb86-3372-470f-a066-e3a3952ce646" alt="Confusion Matrix MobileNet" width="400"/>
</p>

---

## 📰 Poster
<p align="center">
  <img src="https://github.com/user-attachments/assets/01065f83-eb94-4178-b335-517e3229f56c" alt="System Architecture" width="800"/>
</p>

---

## 🤝 Đóng góp
Dự án được phát triển bởi 4 thành viên:

| Họ và Tên         | Vai trò                   |
|-------------------|--------------------------|
| Nguyễn Quang Hiệp | Phát triển mã nguồn, thiết kế và huấn luyện mô hình, đánh giá, demo hệ thống.|
| Vũ Đức Anh        | Tài liệu, poster, slide, hỗ trợ triển khai và thuyết trình.|
| Nguyễn Xuân Thuận | Thiết kế slide, hỗ trợ tài liệu, test hệ thống, xử lý ảnh.  |
| Lê Đức Mạnh       | Hỗ trợ huấn luyện, kiểm thử, xử lý ảnh.       |

© 2025 NHÓM 7, CNTT16-01, TRƯỜNG ĐẠI HỌC ĐẠI NAM

---
