Project Overview:
Dự án này xây dựng một hệ thống quản lý và phân tích dữ liệu đơn hàng, bao gồm nhiều bảng dữ liệu liên kết với nhau theo mô hình star schema. Bảng chính là fact_order lưu thông tin chi tiết về từng đơn hàng, trong khi các bảng chiều như dim_customer, dim_product, dim_payment và dim_shipping cung cấp thông tin bổ sung liên quan đến khách hàng, sản phẩm, thanh toán và vận chuyển. Mục tiêu của hệ thống là phục vụ việc phân tích kinh doanh, hiểu hành vi người tiêu dùng, đánh giá hiệu quả hoạt động và tối ưu hóa các chiến lược kinh doanh.
________________________________________
Mô tả các cột trong các file:
1.	File dim_customer.csv:
-	customer id: Mã định danh duy nhất cho mỗi khách hàng.
-	age: Tuổi của khách hàng.
-	gender: Giới tính của khách hàng (Male hoặc Female).
2.	File dim_payment.csv:
-	payment_id: Mã định danh cho phương thức thanh toán.
-	payment method: Loại hình thanh toán được sử dụng (ví dụ: Bank Transfer, Credit Card, Cash, v.v.).
-	payment type: Phân loại thanh toán theo hình thức Online hoặc Offline.
3.	File dim_product.csv:
Lưu ý: File này đang bị lỗi định dạng, toàn bộ dữ liệu đang nằm chung một cột và phân tách bằng dấu ;. Sau khi xử lý đúng định dạng, các cột sẽ bao gồm:
-	product id: Mã định danh của sản phẩm.
-	sku: Mã sản phẩm nội bộ (Stock Keeping Unit).
-	product type: Loại sản phẩm (ví dụ: Laptop, Headphones, v.v.).
-	unit price: Giá bán lẻ của từng đơn vị sản phẩm.
4.	File dim_shipping.csv:
-	shipping id: Mã định danh phương thức vận chuyển.
-	shipping type: Loại hình giao hàng (ví dụ: Standard, Express, Overnight, v.v.).
-	shipping category: Phân loại tốc độ hoặc dịch vụ vận chuyển (ví dụ: Standard, Fast Shipping, Same-Day).
-	shipping cost level: Mức chi phí vận chuyển (ví dụ: Low, Medium, High, Very High).
5.	File fact_order.csv:
Lưu ý: File này có hai cột bị định dạng sai cần tách ra từ dạng 'key':'value'. Dưới đây là mô tả nếu đã xử lý đúng định dạng:
-	order id: Mã định danh của đơn hàng.
-	customer id: Tham chiếu đến bảng khách hàng dim_customer.
-	product id: Tham chiếu đến bảng sản phẩm dim_product.
-	order status: Trạng thái đơn hàng (ví dụ: Completed, Cancelled).
-	payment id: Tham chiếu đến bảng thanh toán dim_payment.
-	purchase date: Ngày mua hàng.
-	shipping id: Tham chiếu đến bảng vận chuyển dim_shipping.
-	loyalty: Khách hàng có thuộc chương trình khách hàng thân thiết hay không (Yes/No).
-	rating: Mức độ đánh giá hoặc xếp hạng từ khách hàng (số).
-	quantity: Số lượng sản phẩm trong đơn hàng.
-	cost: Chi phí/tổng giá trị của đơn hàng.
________________________________________
Sales Performance Dashboard được thiết kế thân thiện người xem, nhắm đến cho quản lý xem xét đánh giá hiệu quả của bán hàng từ đó đưa ra đề xuất cải thiện
-	Overview: Trang tổng quan giúp quản lý xét xét tổng thể hiệu quả bán hàng từ số lượng order, tổng doanh thu, tổng chi phí, lợi nhuận và tỷ suất lợi nhuận (margin). Ngoài ra còn thể hiện tỷ lệ đơn hàng theo trạng thái (đã hoàn tất, bị hủy), phân bổ khách hàng theo chương trình khách hàng thân thiết (loyalty), và xu hướng lợi nhuận theo thời gian.
-	Product: Trang này cung cấp cái nhìn chi tiết về hiệu quả kinh doanh theo từng loại sản phẩm như Smartphone, Tablet, Laptop, Smartwatch, và Headphones. Các chỉ số thể hiện gồm doanh thu, lợi nhuận, số đơn hàng, tỷ lệ đơn bị hủy, và đánh giá trung bình từ khách hàng (rating).
-	Customer: Trang phân tích khách hàng theo độ tuổi (Young, Adult, Senior), giới tính, và tỷ lệ tham gia chương trình khách hàng thân thiết. Thống kê bao gồm: số lượng đơn hàng trung bình trên mỗi khách hàng, doanh thu theo nhóm tuổi, lợi nhuận trung bình và xu hướng giữ chân khách hàng theo thời gian.
-	Detail: Trang chi tiết theo từng khách hàng cá nhân, thể hiện rõ số lượng đơn hàng, số đơn bị hủy, tổng doanh thu, chi phí, lợi nhuận và tỷ suất lợi nhuận. Giúp theo dõi mức độ đóng góp của từng khách hàng và phát hiện các hành vi mua hàng nổi bật.

