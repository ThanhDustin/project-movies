#  Movie Recommendation System

Hệ thống đề xuất phim được xây dựng bằng Python, kết hợp giữa hai phương pháp Content-Based Filtering và Collaborative Filtering nhằm gợi ý phim phù hợp dựa trên dữ liệu người dùng và nội dung phim.

---

##  Mục tiêu dự án

- Phân tích xu hướng thể loại phim theo thời gian.
- Xây dựng hệ thống đề xuất phim cá nhân hóa.
- Đưa ra nhận định về mối quan hệ giữa các yếu tố như ngân sách và độ phổ biến phim.

---

## 📁 Dữ liệu sử dụng

Nguồn dữ liệu từ Kaggle:
- **tmdb_5000_movies.csv**: chứa thông tin phim như `title`, `genres`, `budget`, `revenue`, `popularity`, `vote_average`, v.v.
- **tmdb_5000_credits.csv**: chứa thông tin về `cast` và `crew`.

Liên kết:  
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

---

## 🔍 Các bước phân tích và xây dựng hệ thống

### 1. Làm sạch và xử lý dữ liệu
- Loại bỏ dữ liệu null và trùng lặp.
- Chuyển đổi định dạng dữ liệu danh sách từ chuỗi JSON sang list Python.
- Chuẩn hóa các cột `release_date`, `genres`, `cast`, `crew`.

### 2. Phân tích dữ liệu (EDA)
- Phân tích phổ biến các thể loại phim từ năm 1916 đến 2017.
- Đánh giá độ phổ biến theo từng thể loại qua từng năm.
- Phân tích mối tương quan giữa ngân sách và độ phổ biến phim.

### 3. Trực quan hóa
- Biểu đồ tròn thể hiện phân bố thể loại.
- Biểu đồ cột top 10 phim theo ngân sách, doanh thu, độ phổ biến và đánh giá.
- Biểu đồ thời gian cho thể loại phổ biến (ví dụ: Drama).

---

##  Xây dựng hệ thống đề xuất phim

###  Content-Based Filtering
- Tạo đặc trưng (tags) cho mỗi phim từ `genres`, `keywords`, `cast`, `director`.
- Tính toán Cosine Similarity giữa các phim.
- Đề xuất phim tương tự phim người dùng đã thích.

### Collaborative Filtering (SVD)
- Sử dụng thư viện `Surprise` và thuật toán SVD.
- Học từ đánh giá người dùng để đưa ra dự đoán phim họ sẽ thích.

---

##  Kết quả nổi bật

- **Thể loại phổ biến nhất:** Drama
- **Mối tương quan giữa ngân sách và độ phổ biến:** Pearson ≈ 0.49 → Có tương quan trung bình.
- **Top đạo diễn có nhiều phim thành công nhất:**
  - Steven Spielberg (26 phim)
  - Woody Allen, Martin Scorsese, Clint Eastwood, Ridley Scott

---

##  Kết luận

- Kết hợp cả hai phương pháp giúp tăng độ chính xác đề xuất.
- Ngân sách ảnh hưởng đến độ phổ biến, nhưng không phải yếu tố quyết định.
- Dataset cần được mở rộng hoặc làm sạch kỹ hơn để cải thiện độ tin cậy.

---

##  Thư viện sử dụng
- Pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn
- Surprise (SVD)
- Jupyter Notebook

---

## 📎 Đề xuất mở rộng

- Tích hợp thêm mô tả nội dung phim (overview).
- Dùng word embedding hoặc deep learning để cải thiện đặc trưng phim.
- Triển khai trên web bằng Flask hoặc Streamlit.

