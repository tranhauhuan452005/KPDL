# KPDL
Buổi 4 
1. Mục tiêu bài phân tích
Tìm luật kết hợp: Sử dụng thuật toán Apriori để xác định mối quan hệ giữa các đặc điểm như tuổi, giới tính, loại đau ngực và khả năng mắc bệnh tim.

Phân cụm dữ liệu: Áp dụng thuật toán K-Means để nhóm các bệnh nhân có đặc điểm tương đồng vào các cụm riêng biệt nhằm hiểu rõ hơn về phân loại bệnh nhân.

Tập dữ liệu sử dụng: HeartDiseaseTrain-Test.csv với 1025 bản ghi và 14 thuộc tính.

2. Các bước thực hiện chính
A. Khai phá Luật Kết hợp (Apriori)
Tiền xử lý dữ liệu: * Phân nhóm (binning) các biến số liên tục như Tuổi (Age), Huyết áp (Resting Blood Pressure), Cholesterol, và Nhịp tim tối đa thành các nhóm định tính như "Thấp", "Trung bình", "Cao".

Chuyển đổi dữ liệu sang định dạng "Thuộc tính=Giá trị" (ví dụ: sex=Male, age_group=Trung niên) và thực hiện One-Hot Encoding để phù hợp với thuật toán Apriori.

Trích xuất luật: * Tìm các tập mục phổ biến (frequent itemsets) với mức hỗ trợ tối thiểu (min_support) là 0.2.

Sử dụng các chỉ số như confidence (độ tin cậy) và lift để đánh giá mức độ quan trọng của các quy luật. Ví dụ: Phân tích mối liên hệ giữa hiện tượng đau ngực khi tập thể dục (exercise_induced_angina=Yes) và mục tiêu bệnh lý (target=0).

B. Phân cụm dữ liệu (K-Means)
Chuẩn hóa: Chuyển đổi các biến phân loại sang dạng số (vessels_colored_by_flourosopy) và chuẩn bị dữ liệu cho quá trình tính toán khoảng cách.

Phân tích cụm: Sử dụng K-Means để chia dữ liệu thành các cụm (ví dụ: 3 cụm dựa trên kết quả hiển thị cuối file).

Đánh giá: Tính toán tỷ lệ phân bố của biến mục tiêu (target) trong từng cụm để xem các cụm có phản ánh đúng tình trạng bệnh hay không.

3. Công cụ và Thư viện
Pandas & Numpy: Xử lý và biến đổi dữ liệu.

Matplotlib & Seaborn: Trực quan hóa kết quả phân tích.

Mlxtend: Cung cấp thuật toán Apriori và association_rules.

Scikit-learn: Cung cấp KMeans, StandardScaler và các công cụ tiền xử lý khác.
