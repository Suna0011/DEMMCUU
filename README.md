<h2 align="center">
    <a href="https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin">
    🎓 Faculty of Information Technology (DaiNam University)
    </a>
</h2>
 
<h2 align="center">
    ỨNG DỤNG ĐẾM VÀ THEO DÕI CỪU SỬ DỤNG AI
</h2>

<div align="center">
    <p align="center">
        <img alt="AIoTLab Logo" width="170" src="https://github.com/user-attachments/assets/711a2cd8-7eb4-4dae-9d90-12c0a0a208a2" />
        <img alt="AIoTLab Logo" width="180" src="https://github.com/user-attachments/assets/dc2ef2b8-9a70-4cfa-9b4b-f6c2f25f1660" />
        <img alt="DaiNam University Logo" width="200" src="https://github.com/user-attachments/assets/77fe0fd1-2e55-4032-be3c-b1a705a1b574" />
    </p>

[![AIoTLab](https://img.shields.io/badge/AIoTLab-green?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Faculty of Information Technology](https://img.shields.io/badge/Faculty%20of%20Information%20Technology-blue?style=for-the-badge)](https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-orange?style=for-the-badge)](https://dainam.edu.vn)

</div>

---

# 1. Giới thiệu hệ thống

Hệ thống **Đếm Cừu** là ứng dụng sử dụng trí tuệ nhân tạo nhằm phát hiện, theo dõi và đếm số lượng cừu xuất hiện trong video theo thời gian thực.

Dự án được xây dựng bằng mô hình **YOLOv8 Segmentation** kết hợp với thư viện **OpenCV** để nhận diện đối tượng, tracking theo ID và hiển thị kết quả trực quan trên video.

Hệ thống gồm 2 thành phần chính:

1. **dem_cuu.py**
   - Thực hiện phát hiện và tracking cừu bằng YOLOv8.
   - Đếm số lượng cừu hiện tại trong vùng phát hiện.
   - Thống kê tổng số cừu xuất hiện trong video.
   - Hiển thị segmentation mask với màu sắc khác nhau cho từng cá thể.
   - Xuất video kết quả vào thư mục `results/`.

2. **ve_vung.py**
   - Hỗ trợ vẽ vùng phát hiện bằng đa giác.
   - Giới hạn khu vực xử lý nhằm tăng độ chính xác.
   - Dễ dàng tùy chỉnh vùng phát hiện theo từng video.

---

# 2. Công nghệ sử dụng

- **Python 3.8+**
- **YOLOv8 Segmentation**
- **OpenCV**
- **NumPy**
- **Torch / CUDA**
- **Ultralytics**

---

# 3. Hình ảnh các chức năng

## 1. Giao diện phát hiện và tracking cừu

<img width="705" height="894" alt="image" src="https://github.com/user-attachments/assets/63cde287-d00a-4cff-b919-7c2129170dc7" />

---

## 2. Hiển thị số lượng cừu hiện tại và tổng số

<img width="385" height="110" alt="image" src="https://github.com/user-attachments/assets/4c695d3c-b3db-4c2a-b635-c9d5f6263b38" />

---

## 3. Segmentation mask cho từng con cừu

<img width="566" height="354" alt="image" src="https://github.com/user-attachments/assets/ef7c0a4f-69ca-4380-9fdf-b348ccc281b9" />

---

<h2>4. Hướng dẫn cài đặt và sử dụng</h2>

<h3>Bước 1: Clone project</h3>

  ```bash
  git clone https://github.com/YourUsername/Demcuu.git
  cd Demcuu
   ```
<h3>Bước 2: Tạo môi trường ảo và cài thư viện</h3>

```bash
python -m venv venv
venv\Scripts\activate

pip install ultralytics opencv-python torch torchvision torchaudio tqdm numpy
```

<h3>Bước 3: Chuẩn bị model và video</h3>

<ul>
  <li>Đặt model YOLO đã train vào file <code>best.pt</code>.</li>
  <li>Đặt video cần xử lý vào thư mục <code>videos/</code>.</li>
</ul>

<h3>Bước 4: Chạy chương trình</h3>

```bash
python dem_cuu.py
```

<h3>Bước 5: Kiểm tra kết quả</h3>

<ul>
  <li>Cửa sổ <code>Counting Sheep</code> sẽ hiển thị video realtime.</li>
  <li>Thông tin số lượng cừu hiện tại và tổng số sẽ được cập nhật trực tiếp.</li>
  <li>Video kết quả sẽ được lưu trong thư mục <code>results/</code>.</li>
</ul>

<p>
<em>⚠ Lưu ý:</em> Nếu không có GPU NVIDIA, chương trình vẫn có thể chạy bằng CPU nhưng tốc độ sẽ chậm hơn.
</p>

---

# 5. Cấu trúc thư mục

```bash
Demcuu/
├── dem_cuu.py
├── ve_vung.py
├── best.pt
├── videos/
│   ├── cuu2.mp4
│   └── phan_loai_cuu.mp4
├── results/
└── venv/
```

---

# 6. Thông tin liên hệ

- Tác giả: Hoàng Thế Khải
- GitHub: https://github.com/YourUsername
- Email: khaihoang051103.email@example.com
