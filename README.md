# web-crawler-and-search-engine
<br>

Design The Web Crawler

1. 1 Web crawler nên được triển khai thuật toán change-detection để phát hiện nội dung đã được update mà không phải craw toàn bộ về, có 1 số cách sau:
   + ETag (entity tag) là 1 HTTP response header duy nhất đại diện cho requested source và hash nội dung. ETag value có thể được sử dụng để xác định nếu reqeust web page đã thay đổi. Last-Modified HTTP response header chứa date và time của lần chỉnh sửa gần nhất một cách khác khi resource được update lần cuối.
   + Các nội dung có thể validate nội dung chỉnh sửa. Tuy nhiên thì ko thể so sánh từng từ, nó giống như là đọc toàn bộ page. 1 giải pháp hiệu quả là tìm ra các phần cần thay đổi đổi nội dung. 1 Giải pháp là Merkle tree. Nó thường được sử dụng bởi database giống như là DynamoDB để giải quyền vấn đề anti-entroy among trên nhiều replica. Google crawler sử dụng Simhash alogrithm để hỗ trợ việc tìm ra các nội dung duplication của web pages.
   -> Đầu tiên sẽ so sánh Entity Tag và Last modified nếu phát hiện có chỉnh sửa thì tiếp tục tải các nội dung về, nếu ko chỉnh sửa thì ko cần tải các nội dung về, tải các nội dung về tiếp tục sử dụng Merkle tree để phân tích đoạn nào thay đổi.
     
2. URL uniqueness and duplicate detection.
   + Cần cơ chế phát hiện duplicate URL

Designing The Search Engine
   + Người dùng sẽ thực hiện 1 input và nhận về phản hồi. Thông tin sẽ được search ở database do hệ thống web crawler data về lưu trong database.



