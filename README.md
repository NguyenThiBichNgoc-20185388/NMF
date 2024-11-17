# PHƯƠNG PHÁP NHÂN TỬ HÓA MA TRẬN KHÔNG ÂM (NMF) VÀ ỨNG DỤNG

Một trong những thuật toán phổ biến nhất để giải bài toán NMF là quy tắc cập nhật nhân ([Multiplicative Update Rules](https://www.researchgate.net/publication/2538030_Algorithms_for_Non-negative_Matrix_Factorization) - MUR) được đưa ra bởi Lee và Seung vào năm 1999 và 2001.

![](Anh/ThuatToan.jpg)


## Ứng dụng của NMF trên bộ cơ sở dữ liệu [MovieLens 100K](https://grouplens.org/datasets/movielens/100k/) 
- Bộ cơ sở dữ liệu này bao gồm 100000 lượt đánh giá (1-5) từ 943 người dùng cho 1682 bộ phim:<br>
  Tải bộ dữ liệu:
                  ```bash
                  python hello.py <br>
  Mô tả bộ dữ liệu:
                  ```bash
                  python hello.py
    + *u.data*: chứa toàn bộ các đánh giá của 943 người dùng cho 1682 bộ phim.
    + *u.item*: chứa thông tin về 1682 bộ phim.
    + *u.user*: chứa thông tin về 943 người dùng.
