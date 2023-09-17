# Tìm hiểu phương pháp phân lớp phân cụm

## Phân cụm là gì?
Phân cụm hoặc phân tích cụm là phương pháp nhóm các thực thể dựa trên sự tương đồng. Được định nghĩa là một bài toán học không giám sát nhằm mục đích tạo ra dữ liệu huấn luyện với một tập hợp đầu vào nhất định nhưng không có bất kỳ giá trị mục tiêu nào. Đó là quá trình tìm kiếm các cấu trúc tương tự trong một tập hợp dữ liệu chưa được gắn nhãn để làm cho nó dễ hiểu và dễ thao tác hơn.

Nó tiết lộ các nhóm con trong các bộ dữ liệu không đồng nhất có sẵn sao cho mỗi cụm riêng lẻ có tính đồng nhất cao hơn toàn bộ. Nói một cách đơn giản hơn, các cụm này là các nhóm các đối tượng giống nhau và khác với các đối tượng trong các cụm khác.

Trong phân cụm, máy tự tìm hiểu các thuộc tính và xu hướng mà không cần bất kỳ ánh xạ đầu vào-đầu ra nào được cung cấp. Các thuật toán phân cụm trích xuất các mẫu và suy luận từ loại đối tượng dữ liệu và sau đó tạo ra các lớp phân cụm riêng biệt cho phù hợp.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/8ab1ecd7-a857-4d2b-93f4-acc8985eb0c5)

## Các loại phương pháp phân cụm
Phân cụm giúp thực hiện phân tích cấp độ bề mặt của dữ liệu phi cấu trúc. Việc hình thành cụm phụ thuộc vào các tham số khác nhau như khoảng cách ngắn nhất, đồ thị và mật độ của các điểm dữ liệu. Việc phân nhóm thành các cụm được thực hiện bằng cách tìm thước đo độ tương tự giữa các đối tượng dựa trên một số thước đo được gọi là thước đo độ tương tự. Sẽ dễ dàng hơn để tìm thấy các thước đo tương tự ở số lượng đặc điểm ít hơn. Việc tạo ra các thước đo tương tự trở thành một quá trình phức tạp khi số lượng đặc điểm tăng lên. Các loại phương pháp phân cụm khác nhau trong khai thác dữ liệu sử dụng các phương pháp khác nhau để nhóm dữ liệu từ các bộ dữ liệu. Phần này mô tả các phương pháp phân cụm.

Các loại phân cụm khác nhau là:
- Phân cụm dựa trên kết nối (Phân cụm theo cấp bậc)
- Phân cụm dựa trên Centroids (Phương pháp phân vùng)     
- Phân cụm dựa trên phân phối
- Phân cụm dựa trên mật độ (Phương pháp dựa trên mô hình)
- Phân cụm mờ
- Dựa trên ràng buộc (Phân cụm được giám sát)

### 1. Phân cụm dựa trên kết nối (Hierarchical Clustering)
Phân cụm theo cấp bậc, còn được gọi là phân cụm dựa trên kết nối, dựa trên nguyên tắc mọi đối tượng được kết nối với các đối tượng lân cận tùy thuộc vào khoảng cách gần (mức độ quan hệ) của chúng. Các cụm được thể hiện trong các cấu trúc phân cấp rộng rãi, cách nhau một khoảng cách tối đa cần thiết để kết nối các phần của cụm. Các cụm được biểu diễn dưới dạng Dendrogram, trong đó trục X biểu thị các đối tượng không hợp nhất trong khi trục Y là khoảng cách mà các cụm hợp nhất. Các đối tượng dữ liệu tương tự có khoảng cách tối thiểu nằm trong cùng một cụm và các đối tượng dữ liệu khác nhau được đặt xa hơn trong hệ thống phân cấp. Các đối tượng dữ liệu được ánh xạ tương ứng với một Cụm có các đặc tính riêng biệt liên quan đến tỷ lệ đa chiều, mối quan hệ định lượng giữa các biến dữ liệu hoặc lập bảng chéo ở một số khía cạnh.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/181db47a-d206-47a9-afcf-fcc5fc029351)

#### a: Cách tiếp cận chia rẽ

Cách tiếp cận phân cụm theo cấp bậc này tuân theo cách tiếp cận từ trên xuống trong đó chúng tôi xem xét rằng tất cả các điểm dữ liệu thuộc về một cụm lớn và cố gắng chia dữ liệu thành các nhóm nhỏ hơn dựa trên logic kết thúc hoặc một điểm mà ngoài đó sẽ không có sự phân chia nào nữa điểm dữ liệu. Theo cách lặp đi lặp lại, chúng tôi sẽ chia dữ liệu, vốn từng được nhóm thành một cụm lớn, thành số “n” cụm nhỏ hơn mà các điểm dữ liệu hiện thuộc về.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/39e19040-21fa-48ae-8b5f-b93b528a1b28)

####  Phương pháp tích tụ
Tích tụ hoàn toàn trái ngược với Phân chia, trong đó tất cả các điểm dữ liệu “N” được coi là một thành viên duy nhất của cụm “N” mà dữ liệu được bao gồm. Chúng tôi lặp đi lặp lại kết hợp nhiều cụm “N” này với số lượng cụm ít hơn, giả sử cụm “k” và do đó chỉ định các điểm dữ liệu cho từng cụm này cho phù hợp. Cách tiếp cận này là cách tiếp cận từ dưới lên và cũng sử dụng logic kết thúc trong việc kết hợp các cụm. Logic này có thể là tiêu chí dựa trên số lượng (không còn cụm nào vượt quá điểm này) hoặc tiêu chí khoảng cách (các cụm không được cách nhau quá xa để có thể hợp nhất) hoặc tiêu chí phương sai (mức tăng phương sai của cụm được hợp nhất không được vượt quá một ngưỡng, Phương pháp Ward)

### 2: Phân cụm dựa trên Centroid hoặc phân vùng
Phân cụm dựa trên centroid là loại phân cụm dễ dàng nhất trong tất cả các loại phân cụm trong khai thác dữ liệu. Nó hoạt động dựa trên mức độ gần gũi của các điểm dữ liệu với giá trị trung tâm đã chọn. Các tập dữ liệu được chia thành một số cụm nhất định và một vectơ giá trị tham chiếu đến mỗi cụm. Biến dữ liệu đầu vào được so sánh với giá trị vectơ và đi vào cụm với độ chênh lệch tối thiểu.

Xác định trước số lượng cụm ở giai đoạn ban đầu là giai đoạn quan trọng nhất nhưng cũng phức tạp nhất đối với phương pháp phân cụm. Bất chấp nhược điểm, đây là một phương pháp phân cụm được sử dụng rộng rãi để hiển thị và tối ưu hóa các tập dữ liệu lớn. Thuật toán K-Means nằm trong danh mục này.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/cd66e250-8958-4cbb-93d1-f130f748ecfd)

Trở ngại lớn ở đây là chúng ta nên xác định số cụm, “k”, bằng trực giác hoặc khoa học (Phương pháp khuỷu tay), để bắt đầu lặp lại bất kỳ thuật toán học máy phân cụm nào nhằm bắt đầu gán các điểm dữ liệu.

### 3: Phân cụm dựa trên mật độ (Phương pháp dựa trên mô hình)

Các cụm được hình thành khác nhau về hình dạng và kích thước tùy ý và chứa mức độ đồng nhất tối đa do mật độ tương tự nhau. Cách tiếp cận phân cụm này bao gồm tiếng ồn và các giá trị ngoại lệ trong bộ dữ liệu một cách hiệu quả.

Khi thực hiện hầu hết việc phân cụm, chúng tôi lấy hai giả định chính: dữ liệu không có bất kỳ nhiễu nào và hình dạng của cụm được hình thành thuần túy là hình học (hình tròn hoặc hình elip).

Thực tế là dữ liệu luôn có mức độ không nhất quán (nhiễu) nhất định mà không thể bỏ qua. Thêm vào đó, chúng ta không được giới hạn bản thân trong một hình dạng thuộc tính cố định. Nên có hình dạng tùy ý để không bỏ qua bất kỳ điểm dữ liệu nào. Đây là những lĩnh vực mà các thuật toán dựa trên mật độ đã chứng minh được giá trị của chúng!

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/31914c63-4b62-42af-877b-0ba605871202)

### 4: Phân cụm dựa trên phân phối
Cho đến nay, các kỹ thuật phân cụm như chúng ta biết đều dựa trên độ gần (độ tương tự/khoảng cách) hoặc thành phần (mật độ). Có một nhóm thuật toán phân cụm xem xét một số liệu hoàn toàn khác - xác suất.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/594dd5ad-27f4-4096-bca6-2624b3b2dee5)

Hạn chế lớn của các phương pháp tiếp cận dựa trên mật độ và ranh giới là việc xác định các cụm trước một số thuật toán và chủ yếu là định nghĩa hình dạng của các cụm cho hầu hết các thuật toán. Có ít nhất một điều chỉnh hoặc siêu tham số cần được chọn và điều đó không chỉ là tầm thường mà còn bất kỳ sự không nhất quán nào trong đó sẽ dẫn đến kết quả không mong muốn.

Phân cụm dựa trên phân phối có lợi thế rõ ràng hơn so với các phương pháp phân cụm lân cận và dựa trên trọng tâm về tính linh hoạt, độ chính xác và hình dạng của các cụm được hình thành. Tuy nhiên, vấn đề chính là các phương pháp phân cụm này chỉ hoạt động tốt với dữ liệu tổng hợp hoặc mô phỏng hoặc với dữ liệu trong đó hầu hết các điểm dữ liệu chắc chắn thuộc về một phân bố được xác định trước, nếu không, kết quả sẽ quá khớp.

### 5: Phân cụm mờ
Phân cụm mờ tổng quát hóa phương pháp phân cụm dựa trên phân vùng bằng cách cho phép một đối tượng dữ liệu là một phần của nhiều cụm. Quá trình này sử dụng trọng tâm dựa trên xác suất không gian.

Các bước bao gồm khởi tạo, lặp lại và kết thúc, tạo ra các cụm được phân tích tối ưu dưới dạng phân phối xác suất thay vì gán nhãn cứng.

Thuật toán hoạt động bằng cách gán các giá trị thành viên cho tất cả các điểm dữ liệu được liên kết với mỗi trung tâm cụm. Nó được tính toán từ khoảng cách giữa trung tâm cụm và điểm dữ liệu. Nếu giá trị thành viên của đối tượng gần trung tâm cụm hơn thì có khả năng cao nằm trong cụm cụ thể.

Ở lần lặp cuối cùng, các giá trị liên quan của thành viên và trung tâm cụm được tổ chức lại. Phân cụm mờ xử lý các tình huống trong đó các điểm dữ liệu nằm ở giữa các trung tâm cụm hoặc không rõ ràng. Điều này được thực hiện bằng cách chọn xác suất thay vì khoảng cách.


### 6: Dựa trên ràng buộc (Phân cụm được giám sát)
Nói chung, quá trình phân cụm dựa trên cách tiếp cận mà dữ liệu có thể được chia thành một số nhóm “không xác định” tối ưu. Các giai đoạn cơ bản của tất cả các thuật toán phân cụm là tìm ra các mẫu và điểm tương đồng ẩn đó mà không cần can thiệp hoặc điều kiện được xác định trước. Tuy nhiên, trong một số trường hợp kinh doanh nhất định, chúng tôi có thể được yêu cầu phân vùng dữ liệu dựa trên các ràng buộc nhất định. Đây là lúc phiên bản có giám sát của kỹ thuật học máy phân cụm phát huy tác dụng.

Ràng buộc được định nghĩa là các thuộc tính mong muốn của kết quả phân cụm hoặc kỳ vọng của người dùng về các cụm được hình thành - điều này có thể dưới dạng số cụm cố định, kích thước cụm hoặc các thứ nguyên (biến) quan trọng được yêu cầu cho phân cụm quá trình.

![image](https://github.com/thangdtph27626/PhanCum/assets/109157942/bfd05697-c78e-4b11-ad52-98284ab18fdf)
