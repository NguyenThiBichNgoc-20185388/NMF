# PHƯƠNG PHÁP NHÂN TỬ HÓA MA TRẬN KHÔNG ÂM (NMF) VÀ ỨNG DỤNG
## Phát biểu bài toán NMF
Cho ma trận dữ liệu $\mathbf{A} \in \mathbb{R}^{m \times n}$  với các phần tử không âm, tìm một phân rã sao cho: 
\begin{align}
   \mathbf{A} \approx \mathbf{UV} \label{point:1.1} \tag{1.1}
\end{align}
trong đó $\mathbf{U}$ và $\mathbf{V}$ là các ma trận không âm có kích thước lần lượt là $m \times r$ và $r \times n$ với với $r$ là số nguyên dương thỏa mãn $r < \min(m, n)$.

## Thuật toán
Một trong những thuật toán phổ biến nhất để giải bài toán NMF là quy tắc cập nhật nhân ([Multiplicative Update Rules](https://www.researchgate.net/publication/2538030_Algorithms_for_Non-negative_Matrix_Factorization) - MUR) được đưa ra bởi Lee và Seung vào năm 1999 và 2001.

![](Anh/ThuatToan.jpg)

## Ứng dụng của NMF trên bộ cơ sở dữ liệu [MovieLens 100K](https://grouplens.org/datasets/movielens/100k/) 
- Bộ cơ sở dữ liệu này bao gồm 100000 lượt đánh giá (1-5) từ 943 người dùng cho 1682 bộ phim:
    + *u.data*: chứa toàn bộ các đánh giá của 943 người dùng cho 1682 bộ phim.
    + *u.item*: chứa thông tin về 1682 bộ phim.
    + *u.user*: chứa thông tin về 943 người dùng.
      
- Gợi ý phim cho người dùng theo *user_ID*:
    + Xây dựng ma trận đánh giá **A**: hàng đại diện cho người dùng, cột đại diện cho phim và các giá trị là điểm đánh giá (1-5 hoặc 0 nếu người dùng không đánh giá hay chưa xem phim) => ma trận **A** có kích thước 943x1682.
    + Xây dựng mô hình NMF dựa trên Thuật toán MUR: tách ma trận **A** thành 2 ma trận **U** và **V** có kích thước lần lượt là 943xr và rx1682 với *r* là số lượng thành phần tiềm ẩn (đặc trưng)
    + Đánh giá mô hình tìm *r* tối ưu.
    + Tìm thể loại yêu thích của người dùng *user_ID* dựa trên điểm đánh giá các bộ phim mà người đó đã xem.
    + Sử dụng mô hình NMF để dự đoán điểm đánh giá cho các bộ phim mà người dùng *user_ID* chưa xem: các giá trị trong ma trận **UV** là các điểm đánh giá dự đoán cho các bộ phim mà người dùng đó chưa đánh giá. <br>
  => Đưa ra danh sách 10 bộ phim mà người dùng có khả năng thích dựa trên các điểm đánh giá đã được dự đoán. Nhận xét: các bộ phim gợi ý có phù hợp với thể loại yêu thích của người đó hay không? 
