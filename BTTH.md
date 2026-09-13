# ĐẶC TẢ YÊU CẦU DỰ ÁN CHUYỂN ĐỔI SỐ NỀN TẢNG QUICKBITE

## Vai trò thực hiện: System Analyst (SA)

### Nhiệm vụ 1: Phân tích Môi trường Hệ thống và Xác định Stakeholders

1. Môi trường Hệ thống tác động đến QuickBite

* Môi trường Kinh doanh: Chuỗi Cơm Tấm Sài Gòn có 15 chi nhánh vận hành theo quy trình truyền thống. Quy định về an toàn vệ sinh thực phẩm, hóa đơn thuế, và mô hình chia sẻ chiết khấu/doanh thu trực tiếp chi phối luồng tiền và quy trình xử lý đơn hàng trên hệ thống.
* Môi trường Kỹ thuật & Hạ tầng: Mạng 4G/5G và GPS di động toàn TP.HCM tác động đến độ chính xác của định vị tài xế. Môi trường gồm thiết bị phần cứng đa dạng: smartphone Android/iOS của Khách hàng/Tài xế, máy POS chuyên dụng tại nhà hàng, cùng các API tích hợp thanh toán (MoMo, ZaloPay, VNPay).
* Môi trường Con người: Mức độ thông thạo công nghệ khác nhau giữa các nhóm người dùng: Bác chủ nhà hàng và nhân viên bếp có thói quen quen dùng sổ sách giấy; Khách hàng yêu cầu trải nghiệm nhanh, tối giản; Tài xế cần giao diện trực quan, tương tác an toàn khi đang di chuyển trên đường.

**2. Danh sách Stakeholders & Nguồn Thu thập Yêu cầu**

| Stakeholder                        | Nguồn thu thập yêu cầu phù hợp                                                                | Nhu cầu cốt lõi đối với QuickBite                                                                                                |
| ---------------------------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Khách hàng                       | Nguồn con người và Nguồn thị trường (Phân tích ứng dụng GrabFood, ShopeeFood)         | Tìm món nhanh, đặt đồ ăn dễ dàng, thanh toán tiện lợi và theo dõi vị trí tài xế theo thời gian thực.               |
| Chủ nhà hàng                    | Nguồn con người và Nguồn tài liệu(Hóa đơn, sổ sách doanh thu hiện tại)               | Tiếp nhận đơn tức thì, quản lý thực đơn linh hoạt (bật/tắt món hết) và xem báo cáo doanh thu minh bạch.            |
| Tài xế                           | Nguồn con người (Khảo sát/Sự cố) và Nguồn hệ thống hiện tại(Dữ liệu định vị GPS) | Nhận đơn hợp lý theo tọa độ, ứng dụng chỉ đường chuẩn xác và đối soát tiền công/tiền tip tự động, rõ ràng. |
| **Quản trị viên (Admin)** | Nguồn tài liệu(Quy trình vận hành QuickBite) & Nguồn hệ thống(Log dữ liệu vận hành)   | Kiểm soát toàn bộ hệ thống, quản lý chiết khấu, phân quyền người dùng và xử lý khiếu nại giữa các bên.          |

### Nhiệm vụ 2: Lựa chọn Kỹ thuật Thu thập Yêu cầu phù hợp

1. Tình huống & Kỹ thuật lựa chọn

* Tìm hiểu cấu trúc danh mục món ăn từ hóa đơn giấy:  Phân tích tài liệu (Document Analysis)
  * Lý do*:* Hóa đơn giấy chứa sẵn dữ liệu cấu trúc chuẩn xác về tên món, giá tiền, combo, đồ kèm. Không cần tốn thời gian phỏng vấn hay khảo sát.
* Tìm hiểu quy trình phối hợp thực tế tại nhà bếp:  Quan sát thực tế (Observation)
  * Lý do*:* Nhân viên bếp khi thao tác cao điểm thường làm theo phản xạ thực tế và bỏ qua các chi tiết khi tự kể lại. Quan sát trực tiếp tại hiện trường giúp phát hiện chính xác các điểm nghẽn quy trình.
* Khai thác trăn thở và kỳ vọng của Bác chủ nhà hàng:  Phỏng vấn chuyên sâu (In-depth Interview)
  * Lý do*:* Chủ nhà hàng là người nắm quyền quyết định chiến lược. Phỏng vấn 1 - 1 giúp đào sâu lý do đằng sau các yêu cầu, tạo sự tin tưởng và khai thác trăn trở kinh doanh cốt lõi.
* Thu thập ý kiến cước phí của 1.000 tài xế:  Khảo sát diện rộng (Survey/Questionnaire)
  * Lý do*:* Lực lượng tài xế quy mô lớn, di chuyển rải rác. Dùng biểu mẫu khảo sát trực tuyến giúp thu thập số liệu thống kê định lượng nhanh chóng với chi phí tối ưu.

2. Lý do KHÔNG chọn Phỏng vấn chuyên sâu cho 1.000 tài xế

Phỏng vấn chuyên sâu tiêu tốn rất nhiều thời gian và nguồn lực nhân sự (không thể thực hiện 1.000 cuộc phỏng vấn cá nhân trong thời gian hạn định). Ngoài ra, tài xế thường xuyên di chuyển nên khó xếp lịch hẹn phỏng vấn cá nhân

### Nhiệm vụ 3: Phân loại và Chuẩn hóa Yêu cầu FR và NFR

1. Bảng Phân loại & Định lượng hóa NFR

| Phát biểu yêu cầu                                                                 | Phân loại | Chỉ số đo lường định lượng cụ thể (KPI/SLA)                                                                                          |
| ------------------------------------------------------------------------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Khách hàng có thể gõ từ khóa để tìm kiếm món ăn trên ứng dụng         | FR          | *(Yêu cầu Chức năng - không áp dụng)*                                                                                                  |
| Thời gian hiển thị kết quả tìm kiếm phải dưới 1.5 giây                     | NFR         | Thời gian phản hồi API tìm kiếm < 1.5s với truy vấn 100 ký tự dưới điều kiện mạng 4G tiêu chuẩn                               |
| Chủ nhà hàng có thể bấm xác nhận tiếp nhận đơn hàng trên màn hình POS | FR          | *(Yêu cầu Chức năng - không áp dụng)*                                                                                                  |
| Ứng dụng phải chịu tải 10.000 người dùng truy cập cùng lúc                 | NFR         | Hệ thống duy trì trạng thái hoạt động với 10.000 người dùng; tỷ lệ lỗi (Error Rate) < 0.1% và bộ xử lý của hệ thống < 80% |
| Giao dịch thanh toán thẻ phải được mã hóa truyền tải an toàn              | NFR         | Toàn bộ dữ liệu giao dịch phải được mã hóa chuẩn trên đường truyền và tuân thủ chứng chỉ bảo mật PCI-DSS               |
| Tài xế có thể bật/tắt chế độ sẵn sàng nhận đơn hàng mới               | FR          | *(Yêu cầu Chức năng - không áp dụng)*                                                                                                  |

### Nhiệm vụ 4: Xây dựng Bộ User Story căn bản cho QuickBite

### 1. Danh sách User Story

### Nhóm Khách hàng

* User Story 1: Là một Khách hàng, Tôi muốn gõ từ khóa tên món ăn trên thanh tìm kiếm của ứng dụng di động, Để tìm thấy món ăn yêu thích nhanh chóng mà không cần lướt qua toàn bộ thực đơn.
* User Story 2: Là một Khách hàng, Tôi muốn theo dõi vị trí tài xế theo thời gian thực trên bản đồ, Để chủ động canh thời gian nhận đồ ăn còn nóng hổi.

### Nhóm Chủ nhà hàng

* User Story 3: Là một Chủ nhà hàng, Tôi muốn bấm nút xác nhận tiếp nhận đơn hàng trực tiếp trên màn hình POS, Để báo cho nhà bếp bắt đầu chế biến và đồng bộ trạng thái đơn hàng tới khách hàng.
* User Story 4: Là một Chủ nhà hàng, Tôi muốn chuyển trạng thái món ăn sang "Hết hàng" ngay trên màn hình POS, Để ứng dụng tự động ẩn món đó, tránh trường hợp khách đặt phải món nhà hàng đã hết nguyên liệu.

### Nhóm Tài xế giao hàng

* User Story 5: Là một Tài xế, Tôi muốn bật/tắt chế độ sẵn sàng nhận đơn trên ứng dụng di động, Để chủ động kiểm soát thời gian làm việc và ngừng nhận đơn khi cần nghỉ ngơi.
* User Story 6: Là một Tài xế, Tôi muốn xem tổng thu nhập và tiền tip được đối soát theo từng ngày, Để theo dõi chi tiết hiệu quả công việc và minh bạch tài chính.

### 2. Lập luận: Tại sao thành phần 'Để [Giá trị]' lại quan trọng nhất?

Thành phần "Để [Giá trị]" quy định mục đích kinh doanh cốt lõi đằng sau mỗi tính năng. Xác định rõ "Giá trị" giúp đội ngũ kỹ thuật có không gian sáng tạo ra giải pháp tối ưu nhất, đồng thời hỗ trợ SA và Product Owner ưu tiên thứ tự phát triển (Backlog Prioritization) dựa trên giá trị mang lại cho doanh nghiệp.
