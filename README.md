# web-crawler-and-search-engine
<br>

1. 1 Web crawler nên được triển khai thuật toán change-detection để phát hiện nội dung đã được update mà không phải craw toàn bộ về, có 1 số cách sau:
   + ETag (entity tag) là 1 HTTP response header duy nhất đại diện cho requested source và hash nội dung. ETag value có thể được sử dụng để xác định nếu reqeust web page đã thay đổi. Last-Modified HTTP response header chứa date và time của lần chỉnh sửa gần nhất một cách khác khi resource được update lần cuối.
   + Các nội dung có thể validate nội dung chỉnh sửa. Tuy nhiên thì ko thể so sánh từng từ, nó giống như là đọc toàn bộ page. 1 giải pháp hiệu quả là tìm ra các phần cần thay đổi đổi nội dung. 1 Giải pháp là Merkle tree. Nó thường được sử dụng bởi database giống như là DynamoDB để giải quyền vấn đề anti-entroy among trên nhiều replica. Google crawler sử dụng Simhash alogrithm để hỗ trợ việc tìm ra các nội dung duplication của web pages.
