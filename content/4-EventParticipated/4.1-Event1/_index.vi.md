---
title: "Event 1"
date: 2026-05-30
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch Workshop "GenAI-powered App-DB Modernization"

## Tổng quan sự kiện

Workshop diễn ra vào ngày 30/05 với nội dung chính xoay quanh hiện đại hóa ứng dụng và cơ sở dữ liệu trong bối cảnh GenAI. Điểm đặc biệt của buổi chia sẻ là nội dung không chỉ dừng lại ở công cụ kỹ thuật, mà còn kết nối nhiều khía cạnh khác như tư duy hệ thống, văn hóa DevOps, cách học cloud an toàn, rào cản tâm lý và tinh thần xây dựng sản phẩm thực tế.

Điều tôi ghi nhớ nhất sau sự kiện là việc phát triển một sản phẩm công nghệ không chỉ phụ thuộc vào việc chọn đúng dịch vụ AWS hay dùng đúng công cụ tự động hóa. Một dự án muốn đi xa còn cần sự phối hợp giữa con người, quy trình làm việc, trách nhiệm chung và khả năng phản hồi nhanh khi có vấn đề.

## Diễn giả tham gia

- **Trần Minh Quân** - Sinh viên thực tập
- **Trần Hữu Nghĩa** - Sinh viên thực tập
- **The Baller** - Sinh viên thực tập
- **Phạm Quang Thái** - Sinh viên thực tập
- **Nguyễn Thị Quỳnh Như** - Sinh viên thực tập
- **Khắc Uy** - Sinh viên thực tập
- **Huỳnh Thái Linh** - Sinh viên thực tập

## Nội dung chính của workshop

### Kết hợp giữa tư duy, công nghệ và yếu tố con người

Một điểm nổi bật của sự kiện là các bài trình bày không tách riêng kỹ thuật khỏi yếu tố con người. Những vấn đề như trễ deadline, lỗi production, làm việc thiếu phối hợp hoặc trì hoãn cá nhân đều được nhìn theo hướng tìm nguyên nhân gốc rễ.

Trong quản lý dự án, phần nổi của vấn đề có thể là bug, chậm tiến độ hoặc áp lực công việc. Tuy nhiên, phần sâu hơn thường đến từ việc giao tiếp chưa tốt, các nhóm làm việc tách biệt, quy trình còn thủ công hoặc trách nhiệm chưa rõ ràng. Ở góc độ cá nhân, sự trì hoãn không phải lúc nào cũng do lười biếng, mà có thể đến từ nỗi sợ thất bại, sợ bị đánh giá hoặc thiếu tự tin.

### Văn hóa DevOps và quản lý dự án

Phần DevOps giúp tôi hiểu rõ hơn rằng DevOps không chỉ là tập hợp các công cụ triển khai. Cốt lõi của DevOps nằm ở sự kết hợp giữa **Con người, Quy trình và Công nghệ**.

Công cụ có thể giúp tự động hóa quá trình build, test hoặc deploy, nhưng không thể tự động hóa niềm tin, giao tiếp và tinh thần trách nhiệm trong đội nhóm. Đây là một góc nhìn quan trọng vì nhiều vấn đề kỹ thuật thực chất bắt nguồn từ cách làm việc và cách phối hợp giữa các thành viên.

### Học cloud an toàn và tối ưu chi phí

Sự kiện cũng đề cập đến khó khăn của người mới học AWS, đặc biệt là nỗi lo phát sinh chi phí khi quên xóa tài nguyên sau khi thực hành.

Để giảm rủi ro này, các diễn giả giới thiệu những cách học an toàn hơn như **AWS Cloud Quest** và công cụ giả lập local **Floci**. Floci là một công cụ mã nguồn mở nhẹ, hỗ trợ mô phỏng một số thành phần AWS trên máy cá nhân, từ đó giúp kiểm thử kiến trúc nhanh hơn và hạn chế chi phí khi học tập hoặc thử nghiệm.

### Tinh thần xây dựng sản phẩm thực tế

Một nội dung khác tôi thấy rất hữu ích là tinh thần "build fast, fail fast". Thông qua các ví dụ từ môi trường hackathon, tôi thấy được cách một nhóm có thể tập trung vào bài toán cốt lõi, xây dựng phiên bản chạy được trước, nhận phản hồi sớm và cải tiến dần.

Workshop cũng nhắc đến các ý tưởng thực tế như **SynthHunter**, hệ thống hỗ trợ phân biệt giọng nói AI và giọng người thật để giảm rủi ro gian lận, và **Vortex**, ứng dụng hỗ trợ quy trình tuyển dụng. Các ví dụ này cho thấy những sản phẩm có giá trị thường bắt đầu từ việc giải quyết một vấn đề cụ thể trong thực tế.

## Kiến thức kỹ thuật học được

### Thiết kế và hiện đại hóa ứng dụng

Tôi được tìm hiểu thêm về cách phân tích và thiết kế lại hệ thống thông qua **event storming**. Cách tiếp cận này giúp mô hình hóa quy trình nghiệp vụ thành các domain event, từ đó dễ hình dung hơn cách các thành phần trong hệ thống tương tác với nhau.

Ngoài ra, workshop còn đề cập đến **bounded context**, cách tách microservices và các kiểu giao tiếp trong hệ thống phân tán. Tôi hiểu rõ hơn về sự đánh đổi giữa giao tiếp đồng bộ và bất đồng bộ, cũng như các mô hình tích hợp như pub/sub, point-to-point và streaming.

### GenAI trong vòng đời phát triển phần mềm

Sự kiện giới thiệu **Amazon Q Developer** như một công cụ AI có thể hỗ trợ nhiều giai đoạn trong vòng đời phát triển phần mềm, từ lên kế hoạch, viết mã, hiện đại hóa hệ thống cho đến bảo trì.

Tôi cũng có thêm góc nhìn về việc dùng AI để hỗ trợ chuyển đổi mã nguồn, đồng thời kết hợp các dịch vụ serverless như **AWS Lambda** để tăng tốc quá trình thử nghiệm và triển khai.

## Bài học cá nhân

### Vượt qua rào cản tâm lý

Một bài học đáng chú ý là 70-80% sự trì hoãn có thể xuất phát từ khó khăn trong việc quản lý cảm xúc, chứ không đơn giản là do lười biếng. Những nỗi sợ như sợ làm chưa đủ tốt, sợ bị đánh giá hoặc sợ thất bại có thể khiến bản thân chần chừ trước khi bắt đầu.

Hai phương pháp tôi thấy dễ áp dụng là **Quy tắc 5 phút** và **Quy tắc 5 giây**. Quy tắc 5 phút giúp bắt đầu một việc khó bằng cách chỉ cam kết làm trong thời gian rất ngắn để tạo đà. Quy tắc 5 giây giúp bản thân hành động ngay bằng cách đếm ngược 5-4-3-2-1 trước khi sự do dự xuất hiện.

### Cách áp dụng vào học tập và công việc

Sau workshop, tôi rút ra một số hướng có thể áp dụng vào quá trình học tập và làm dự án:

- Xây dựng quy trình làm việc nhóm rõ ràng hơn, đề cao trách nhiệm chung thay vì đổ lỗi.
- Tạo vòng phản hồi nhanh để phát hiện lỗi hoặc rủi ro từ sớm.
- Gọi tên cụ thể nỗi sợ của bản thân thay vì chỉ kết luận rằng mình đang lười.
- Ghi nhận các tiến bộ nhỏ mỗi ngày để tăng sự tự tin.
- Thực hành AWS bằng các phương pháp an toàn hơn như AWS Cloud Quest hoặc công cụ mô phỏng local.
- Duy trì tinh thần "go build": tạo phiên bản chạy được trước, sau đó cải tiến dựa trên phản hồi.

## Trải nghiệm sau khi tham gia

Nhìn chung, workshop giúp tôi có cái nhìn rộng hơn về mối liên hệ giữa kỹ thuật, quy trình làm việc và tâm lý con người. Tôi không chỉ học thêm về hiện đại hóa ứng dụng, microservices, GenAI, serverless và công cụ hỗ trợ phát triển phần mềm, mà còn hiểu rõ hơn vai trò của văn hóa làm việc trong thành công của một dự án.

Điều quan trọng nhất tôi rút ra là kỹ thuật tốt không chỉ nằm ở việc viết code. Nó còn đến từ khả năng giao tiếp rõ ràng, tinh thần trách nhiệm, sự chủ động thử nghiệm và dám bắt đầu trước khi mọi thứ hoàn hảo.

## Hình ảnh sự kiện

*Thêm hình ảnh tham gia sự kiện tại đây.*
