# An Intelligent Skin Cancer Classification System using YOLO26
### *Powered by YOLO26X & Streamlit*
📝 Giới thiệu dự án (Paraphrased)
Dự án tập trung nghiên cứu và phát triển giải pháp Deep Learning chuyên dụng cho việc phát hiện và phân cấp các bệnh lý ung thư da (BCC và Melanoma). Bằng cách khai thác sức mạnh của kiến trúc YOLO26X, hệ thống hướng tới mục tiêu tối ưu hóa quy trình sàng lọc lâm sàng, cung cấp công cụ hỗ trợ chẩn đoán sớm với tốc độ xử lý nhanh và độ tin cậy vượt trội cho đội ngũ y tế.

🌟 Điểm nhấn công nghệ
- Scale & Robustness: Mô hình được tinh chỉnh (fine-tuned) trên tập dữ liệu quy mô lớn với hơn 36.000 mẫu ảnh đã qua xử lý tăng cường (augmentation), đảm bảo khả năng nhận diện ổn định trong nhiều điều kiện thực tế.
- Next-Gen Architecture: Ứng dụng biến thể YOLO26X — thế hệ mới nhất của dòng YOLO — mang lại sự cân bằng hoàn hảo giữa hiệu suất tính toán và độ chính xác trong phân tích ảnh y tế.
- Interactive Deployment: Triển khai ứng dụng Web dưới dạng công cụ tương tác trực tiếp (Demo) thông qua framework Streamlit, cho phép người dùng nhận kết quả phân tích tức thì chỉ với một thao tác tải ảnh.
- Diagnostic Reliability: Không chỉ dừng lại ở việc gán nhãn, hệ thống cung cấp chỉ số tin cậy (Confidence Score) chi tiết cho từng dự đoán, giúp minh bạch hóa quá trình ra quyết định của AI.

---

## Công nghệ sử dụng  
* **Core:** Python, PyTorch, Ultralytics (YOLO26).  
* **Data Processing:** Roboflow, OpenCV, Pandas.  
* **Deployment:** Streamlit.  
* **Training:** Google Colab (L4 GPU).

## 📊 Kết quả huấn luyện  
Mô hình được huấn luyện trên GPU **NVIDIA L4** với cấu hình tối ưu:
* **Dataset Size:** 36,087 images (sau khi Augmentation).
* **Input Size:** 800x800 pixels.
* **Accuracy (Top-1):** **~93%**
* **Epochs:** 60.

### Result & Confusion Matrix  
**Result**  
<img width="695" height="694" alt="image" src="https://github.com/user-attachments/assets/78230c77-998f-4acb-8e6c-4d9f4b7b595a" />  

**Confusion Matrix**  
<img width="757" height="661" alt="image" src="https://github.com/user-attachments/assets/b29a74d9-1dea-47f1-b777-952c3011e1c4" />

---
 
## Demo Web  
### 1. Upload ảnh  
- Upload ảnh MEL, BCC hay others (ung thư khác).  
<img width="1421" height="736" alt="image" src="https://github.com/user-attachments/assets/9e0def64-554e-4b5a-9e06-4d902f33c1f1" />

### 2. Tiền xử lý ảnh  
- Ảnh được xử lý qua CLAHE và Sharpen.
<img width="1409" height="771" alt="image" src="https://github.com/user-attachments/assets/2539eb70-9360-4eb3-b4e0-414ddb0abdb2" />

### 3. Kết quả  
<img width="1419" height="245" alt="image" src="https://github.com/user-attachments/assets/0902c51b-83cb-43a6-8703-fccf954f3a93" />  

---

## 📂 Cấu trúc thư mục  
```text
├── web.py    # Code giao diện Streamlit
├── best.pt            # Trọng số mô hình tốt nhất sau khi train
└── README.md
```

---

### Hướng dẫn Cài đặt & Triển khai
1. Cài đặt môi trường
Đảm bảo bạn đã cài đặt Python 3.10+. Clone repository và cài đặt các thư viện cần thiết:
```
Bash
git clone https://github.com/TranNhuKhaY512/Skin_Cancer_Classification_System_using_YOLO26.git
cd Skin_Cancer_Classification_System_using_YOLO26
pip install -r requirements.txt
```
2. Hướng dẫn tải Mô hình (Model Weights)
- Do giới hạn về dung lượng lưu trữ của GitHub, các tệp trọng số (weights) của hệ thống Trợ lý AI Đa phương thức đã được lưu trữ trên nền tảng đám mây. Để chạy được dự án, vui lòng tải các mô hình dưới đây và đặt vào đúng thư mục cấu hình:
- Model Weights (YOLO26)
Để hệ thống có thể nhận diện chính xác, bạn cần tải xuống tệp trọng số đã được huấn luyện sẵn (Pre-trained weights).
  - Model: best.pt (YOLO26X Optimized)
  - Dung lượng: 55.4 MB
  - Link tải: [Tải model tại đây ](https://drive.google.com/file/d/1yLbzMxDqWGWNEat6IbV6xV9iGD8VIejb/view?usp=sharing)(#)
  - Vị trí lưu trữ: Sau khi tải về, vui lòng đặt file vào thư mục gốc của dự án

3. Khởi động hệ thống: 
- Sau khi hoàn tất cấu hình, khởi động Web Server:
```
Bash
streamlit run app/web.py
```


