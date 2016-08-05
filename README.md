# Tìm hiểu về Beats

## Giới thiệu tổng quan

  The Beats are open source data shippers that you install as agents on your servers to send different types of operational data to [Elasticsearch](https://github.com/nguyenvulebinh/elasticsearch). Beats can send data directly to Elasticsearch or send it to Elasticsearch via [Logstas](http://learn.elastic.co/logstash-intro)
  
  ![alt tag](https://github.com/nguyenvulebinh/beats_elasticsearch/blob/master/beats-platform.png)
  
  Elastic cung cấp 3 bản tùy biến của Beats bao gồm
  - Packetbeat: is a network packet analyzer that ships information about the transactions exchanged between your application servers
  - Topbeat: is a server monitoring agent that periodically ships system-wide and per-process statistics from your servers
  - Filebeat: ships log files from your servers.

  Elastic cung cấp thư viện "libbeat" giúp tùy biến các chức năng của Beats theo miền ứng dụng nên ngoài 3 bản tùy biến trên, cộng đồng cũng đưa ra rất nhiều bản tùy biến khác nhau. Xem thêm ở link [1]
  
  
## Giới thiệu về Filebeat

  Filebeat là một chương trình mã nguồn mở, xây dựng dựa trên libbeat framework, đóng vai trò như một agent theo dõi những thư mục hoặc file log được chỉ định và gửi cho server mỗi khi có sự thay đổi trên file. Filebeat có thể gửi trự tiếp cho Elasticsearch để  index hoặc gửi cho Logstash để phân tích cú pháp sau đó mới gửi tới Elasticsearch để index

  ![alt tag](https://github.com/nguyenvulebinh/beats_elasticsearch/blob/master/filebeat.png)
  
  Trong kiến trúc của Filebeat, khi bắt đầu khởi động, mỗi thư mục sẽ được theo dõi bởi một prospectors, prospectors sẽ khởi tạo mỗi harvester tương ứng với một file. Prospectors sẽ tổng hợp lại các sự kiện và nỗi dung thay đổi sau đó chuyển cho spooler để gửi ra ngoài.
  
## Tài liệu tham khảo

[1] https://www.elastic.co/guide/en/beats/libbeat/current/community-beats.html
