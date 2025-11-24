# Intro to Machine Learning & Deep Learning

1. Trí tuệ nhân tạo : các kĩ thuật giúp máy móc có thể mô phỏng các hành vi trí tuệ của con người
VD: Nhận diện âm thanh, hình ảnh; Điều khiển xe tự lái , ...

2. Từ tập luật ban đầu -> Học từ dữ liệu : Học máy => Máy tính sẽ học các quy luật từ dữ liệu và cải thiện dần theo thời gian mà không cần được lập trình rõ ràng các quy luật
VD: Phân loại email (email có phải là email rác hay không ?)

3. Vai trò của con người trong học máy
- Học máy "nông" : con người đóng vai trò là chuyên gia biểu diễn dữ liệu, máy sẽ học bằng các mô hình phân loại cơ bản => Kết luận
- Học máy "sâu" : mạng nơ-ron học các mẫu, quy luật từ rất nhiều dữ liệu => Kết luận

4. Cở sở của việc Học từ dữ liệu
Có 2 vấn đề cần giải quyết:
- Ước lượng : Dữ liệu thu thập được chỉ là những quan sát có nhiễu phản ảnh giá trị mà ta muốn biết -> Làm thế nào để dùng những quan sát đó để ước lượng được giá trị gần đúng nhất?
- Khái quát hoá : Làm thế nào để dự đoán kết quả của một tình huống chưa từng xuất hiện trong tập dữ liệu?

5. Thành phần của Học máy
Mô tả bài toán:
- Loại bài toán : Loại nhiệm vụ? Dạng dữ liệu (có nhãn hay không?)
- Giả định : Ta biết gì về nguồn dữ liệu đầu vào, hay dạng lời giải?
- Tiêu chí đánh giá : Đánh giá hiệu quả hệ thống bằng cách nào?
Mô tả lời giải:
- Mô hình : 1 hàm toán học của dữ liệu đầu vào -> Lựa chọn như thế nào?
- Thuật toán : Quá trình tính toán nào sẽ được sử dụng để khớp mô hình với dữ liệu và đưa ra dự đoán


- Loại bài toán:
  - Học có giám sát:
    - Học từ dữ liệu huấn luyện. (x(1),y(1)),...,(x(n),y(n)) - Dữ liệu đã có nhãn
    - Ý tưởng: Mô hình sẽ học từ dữ liệu đã có nhãn - ta đã biết trước được đầu ra tương ứng cho từng đầu vào 
    - Mục tiêu: Huấn luyện từ tập dữ liệu có sẵn để dự đoán ra đầu ra cho dữ liệu mới
    - Dạng dữ liệu:
      - Đầu vào: x(n+1)
      - Đầu ra: y(n+1)

    - Có 2 bài toán chính:
      - Hồi quy (Regression) : y là số thực 
      -> Dự đoán giá trị cụ thể
      VD: dự đoán giá nhà dựa vào diện tích; dự đoán điểm thi dự vào số giờ học ...

      - Phân loại (Classification) : y là rời rạc
      -> Dự đoán nhãn/nhóm
      VD: phân loại email spam


  - Học không giám sát
    - Đầu vào: tập dữ liệu không nhãn -> chưa biết trước đầu ra đúng 
    - Đầu ra: quy luật, cấu trúc tiềm ẩn trong tập dữ liệu

    - Các bài toán phổ biến:
      - Phân cụm (Clustering)
      -> Gom các điểm dữ liệu tương đồng lại với nhau
      VD: phân nhóm khách hàng có hành vi mua sắm giống nhau
      -> Thuật toán tiêu biểu: K-Means, ...

      - Giảm chiều (Dimensionality Reduction): Nhiều chiều -> Ít chiều hơn
      -> Giảm số lượng đặc trưng (features) trong dữ liệu để dễ quan sát và xử lý
      VD: từ tập dữ liệu 100 chiều -> giảm còn 2-3 chiều là đặc trưng quan trọng để vẽ biểu đồ 
      -> Thuật toán tiêu biểu: PCA (Principal Component Analysis), ...

- Giả định:
  - Khi huấn luyện mô hình thuật toán -> có vô số cách để miêu tả mối quan hệ giữa dữ liệu đầu vào (x) và dữ liệu đầu ra (y) 
  - Tuy nhiên, ta không thể xem xét toàn bộ các mô hình có thể có -> vì điều này là bất khả thi
  - Vì vậy, ta sẽ đưa ra một số giả định nhằm:
     - Thu hẹp không gian giả thuyết (thu nhỏ tập hợp các mô hình mà thuật toán cần xem xét)
     - Giảm dữ liệu cần thiết để tìm ra mô hình phù hợp
     - Tăng độ tin cậy và khái quát hoá mô hình

    VD: Dữ liệu là độc lập và phân phối đồng nhất (IID - Independent and Identically Distributed)
    Trong bài toán phân cụm khách hàng, ta giả định mỗi khách hàng là độc lập 
    -> Không cần tính đến sự phụ thuộc giữa hành vi của người này và người khác 

  - Nếu giả định đúng, mô hình học sẽ được khái quát tốt hơn
  - Nếu giả định sai, mô hình có thể bị sai lệch (bias) hoặc quá khớp (overfitting)

- Tiêu chí đánh giá:
  - Sử dụng hàm mất mát L(g,a) -> Bị phạt bao nhiêu khi đưa ra dự đoán là g, câu trả lời thật là a


