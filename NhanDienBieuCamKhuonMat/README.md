# Emotion Recognition Using CNN

## Mô tả dự án
Dự án này triển khai hệ thống nhận diện biểu cảm khuôn mặt bằng mô hình CNN. Hệ thống bao gồm:
- Huấn luyện mô hình nhận diện biểu cảm từ tập dữ liệu ảnh grayscale (48x48).
- Đánh giá mô hình bằng dữ liệu kiểm tra.
- Nhận diện biểu cảm khuôn mặt theo thời gian thực từ webcam và phát âm thanh phản hồi phù hợp.

## Cấu trúc thư mục
```
├── models/               # Lưu mô hình đã huấn luyện
│   ├── emotion_cnn.h5
├── data/                 # Chứa dữ liệu huấn luyện và kiểm tra
│   ├── train/            # Dữ liệu huấn luyện
│   ├── test/             # Dữ liệu kiểm tra
├── cnn_model.py          # Huấn luyện mô hình CNN
├── accuracy.py           # Đánh giá mô hình
├── realtime_prediction.py # Nhận diện biểu cảm thời gian thực
├── collect_data.py       # Thu thập dữ liệu từ webcam
├── requirements.txt      # Danh sách thư viện cần cài đặt
├── README.md             # Tài liệu hướng dẫn
```

## Cài đặt
### 1. Cài đặt môi trường
Trước khi chạy code, cài đặt các thư viện cần thiết:
```bash
pip install -r requirements.txt
```

### 2. Thu thập dữ liệu
Chạy `collect_data.py` để thu thập dữ liệu từ webcam:
```bash
python collect_data.py
```
Nhập số lượng mẫu cho từng biểu cảm khi được yêu cầu.

### 3. Huấn luyện mô hình
Chạy script `cnn_model.py` để huấn luyện mô hình từ tập dữ liệu:
```bash
python cnn_model.py
```
Mô hình sau khi huấn luyện sẽ được lưu vào thư mục `models/` với tên `emotion_cnn.h5`.

### 4. Kiểm tra độ chính xác của mô hình
Sau khi huấn luyện xong, có thể đánh giá mô hình bằng script `accuracy.py`:
```bash
python accuracy.py
```
Kết quả sẽ bao gồm độ chính xác, báo cáo chi tiết và biểu đồ ma trận nhầm lẫn.

### 5. Nhận diện biểu cảm khuôn mặt thời gian thực
Chạy `realtime_prediction.py` để mở webcam và nhận diện biểu cảm:
```bash
python realtime_prediction.py
```
Nếu mô hình phát hiện một biểu cảm, hệ thống sẽ hiển thị nhãn và phát âm thanh phản hồi.

## Công nghệ sử dụng
- **TensorFlow/Keras**: Xây dựng và huấn luyện mô hình CNN
- **OpenCV**: Xử lý ảnh và nhận diện khuôn mặt
- **Matplotlib/Seaborn**: Vẽ biểu đồ và ma trận nhầm lẫn
- **gTTS & pygame**: Chuyển văn bản thành giọng nói và phát âm thanh
- **Tkinter**: Giao diện người dùng đơn giản

## Ghi chú
- Đảm bảo dữ liệu trong thư mục `data/train/` và `data/test/` đúng định dạng.
- Mô hình hỗ trợ nhận diện 5 biểu cảm: Angry, Happy, Sad, Surprise, Fear.
- Nếu gặp lỗi khi chạy webcam, hãy kiểm tra lại driver camera hoặc sử dụng camera USB.
