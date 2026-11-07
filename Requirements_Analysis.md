---
title: "Phân tích yêu cầu: Nền tảng HireUS Tools"
group: "Nhóm 02"
course: "Nhập môn Công nghệ Phần mềm (Introduction to Software Engineering)"
institution: "Khoa Công nghệ Thông tin - Trường ĐH Khoa học Tự nhiên, ĐHQG-HCM"
date: "07/11/2026"
version: "1.0"
---

# NHẬP MÔN CÔNG NGHỆ PHẦN MỀM

# PHÂN TÍCH YÊU CẦU — NỀN TẢNG HIREUS TOOLS

> **Môn:** Nhập môn Công nghệ Phần mềm (Introduction to Software Engineering)  
> **Trường:** Đại học Khoa học Tự nhiên, ĐHQG-HCM  
> **Giảng viên thực hành (GVTH):** Thầy Ngô Ngọc Đăng Khoa  
> **Giảng viên lý thuyết (GVLT):** Thầy Phạm Minh Tuấn  
> **Nhóm thực hiện:** Nhóm 02  
> **Đợt báo cáo:** Week02 — Phân tích yêu cầu

## MỤC LỤC

1. [Bảng đánh giá thành viên](#bang-danh-gia-thanh-vien)
2. [Mô tả bài toán](#mo-ta-bai-toan)
3. [Tổng quan yêu cầu](#tong-quan-yeu-cau)
   - [3.1. Danh sách các stakeholder](#stakeholder)
   - [3.2.1. Đặc tả yêu cầu chức năng](#yeu-cau-chuc-nang)
   - [3.2.2. Đặc tả yêu cầu phi chức năng](#yeu-cau-phi-chuc-nang)
4. [Đặc tả yêu cầu](#dac-ta-yeu-cau)
   - [4.1. Sơ đồ Use Case](#so-do-use-case)
   - [4.2. Đặc tả Use Case](#dac-ta-use-case)
5. [Bản mẫu (Prototype)](#prototype)

---

<a id="bang-danh-gia-thanh-vien"></a>

## 1. BẢNG ĐÁNH GIÁ THÀNH VIÊN

| STT | MSSV | Họ và Tên | % Đóng góp (Tối đa 100%) | Chữ ký |
| :---: | :---: | :--- | :---: | :---: |
| 1 | 24120194 | **Võ Minh Khoa** | 100% | <img src="./image/Khoa.jpg" height="40" alt="Chữ ký Võ Minh Khoa" /> |
| 2 | 24120249 | **Võ Nguyễn Việt Hoàng** | 100% | <img src="./image/Hoang.png" height="40" alt="Chữ ký Võ Nguyễn Việt Hoàng" /> |
| 3 | 24120270 | **Đỗ Chí Cao** | 100% | <img src="./image/Cao.png" height="40" alt="Chữ ký Đỗ Chí Cao" /> |
| 4 | 24120290 | **Lê Tấn Dũng** | 100% | <img src="./image/Dung.jpg" height="40" alt="Chữ ký Lê Tấn Dũng" /> |

---

<a id="mo-ta-bai-toan"></a>

## 2. MÔ TẢ BÀI TOÁN

Trong thời đại AI, sinh viên rất khó để tìm và xin được một công việc. Đặc biệt đối với ngành Công nghệ Thông tin khi AI lên ngôi, những bạn Intern hay Fresher trong mảng này thường phải cạnh tranh gay gắt và nhà tuyển dụng cũng đòi hỏi rất nhiều thứ ở ứng viên. Sau khi phân tích và làm rõ, nhóm em hiện thấy có 4 khó khăn mà các bạn sinh viên IT hay gặp phải:

* **Không biết viết CV và CV chưa đạt chuẩn:** Đa số CV sinh viên viết theo mẫu tự do, thiếu số liệu định lượng về dự án và dễ bị hệ thống tự động lọc hồ sơ ATS (Applicant Tracking System) loại bỏ rớt khỏi vòng CV.

* **Tâm lý thiếu tự tin khi tham gia phỏng vấn:** Mặc dù nắm vững kiến thức lý thuyết, nhiều sinh viên vẫn thiếu kinh nghiệm thực tế và cơ hội luyện tập với các câu hỏi phỏng vấn chuyên sâu theo hình thức 1:1, dẫn đến khả năng phản xạ và trình bày câu trả lời còn hạn chế. Bên cạnh đó, tại một số doanh nghiệp, phỏng vấn được thực hiện bằng tiếng Anh, khiến sinh viên gặp khó khăn trong việc diễn đạt ý tưởng, trình bày kiến thức chuyên môn và thể hiện năng lực của bản thân một cách rõ ràng, thuyết phục.

* **Khó tiếp cận thông tin tuyển dụng sớm:** Nhiều sinh viên mong muốn được thực tập và làm việc tại các doanh nghiệp mục tiêu nhưng lại gặp khó khăn trong việc cập nhật thông tin tuyển dụng. Các cơ hội thực tập thường được đăng tải phân tán trên nhiều nền tảng như: LinkedIn, Facebook, ITViec,... khiến thông tin dễ bị trôi hoặc bị lẫn giữa các bài đăng khác. Điều này khiến sinh viên có thể bỏ lỡ những vị trí phù hợp, các đợt tuyển dụng quan trọng hoặc những chương trình thực tập mà bản thân đang quan tâm.

* **Mơ hồ về độ phù hợp và khoảng cách kỹ năng so với thị trường việc làm:** Khi các bạn sinh viên rải hàng trăm CV và bị từ chối sau các cuộc phỏng vấn có thể là một cú sốc và các bạn không biết nguyên nhân từ đâu mà mình thất bại. Trên hết là, các bạn không biết rõ mình đang thiếu hụt kiến thức gì cụ thể để chủ động tự học và bù đắp đúng trọng tâm từ đó cải thiện mình khi đi phỏng vấn.

Để giải quyết trực diện 4 khó khăn thực tế đã nêu trên, nhóm đề xuất giải pháp hệ thống **HireUS Tools** gồm 4 phân hệ cốt lõi:

1. **Phân hệ 1 - Xây dựng CV chuẩn ATS & Trợ lý SeekerBot:** Cung cấp công cụ tạo và chỉnh sửa CV trực tuyến với các mẫu thiết kế chuyên nghiệp, hỗ trợ tối ưu hóa bố cục và nội dung theo tiêu chuẩn ATS nhằm tăng khả năng vượt qua vòng sàng lọc hồ sơ. Tích hợp trợ lý AI SeekerBot để hướng dẫn người dùng xây dựng nội dung CV, cải thiện cách mô tả kỹ năng, kinh nghiệm và dự án, đồng thời đưa ra các đề xuất điều chỉnh phù hợp với vị trí ứng tuyển.

2. **Phân hệ 2 - Mô phỏng phỏng vấn Kỹ thuật Giọng nói (Voice Mock Interview):** Thiết lập phòng phỏng vấn 1:1 tương tác giọng nói hai chiều thời gian thực với AI Tech Lead (hỗ trợ cả tiếng Việt và tiếng Anh), hỏi đáp linh hoạt theo ngữ cảnh và cung cấp báo cáo đánh giá chi tiết.

3. **Phân hệ 3 - Tổng hợp Việc làm & Đối sánh Năng lực (Job Matching & Skill Gap):** Bóc tách yêu cầu công việc từ Job, đối chiếu với CV của bản thân để tính điểm tương thích (%), chỉ ra chính xác các kỹ năng còn thiếu và gợi ý định hướng tự học bổ sung.

4. **Phân hệ 4 - Săn tin tuyển dụng từ mạng xã hội (Job Tracking System):** Định kỳ theo dõi các Fanpage, trang LinkedIn của các doanh nghiệp IT, tự động dùng AI sàng lọc tin phong trào để kịp thời thông báo các đợt mở đơn thực tập Intern và Fresher.

---

<a id="tong-quan-yeu-cau"></a>

## 3. TỔNG QUAN YÊU CẦU

<a id="stakeholder"></a>

### 3.1. Danh sách các stakeholder

#### a. Sơ đồ ngữ cảnh của hệ thống (Context Diagram)

![Sơ đồ ngữ cảnh toàn hệ thống HireUS Tools](./images/HireUS_System_Context.png)

#### b. Vai trò của các stakeholder

| STT | Stakeholder | Mô tả |
| :---: | --- | --- |
| 1 | **Sinh viên / người tìm việc IT Intern, Fresher** | Tạo CV, luyện phỏng vấn, đánh giá độ phù hợp với JD và theo dõi tin tuyển dụng. |
| 2 | **Nhóm phát triển** | Phân tích, thiết kế, xây dựng, kiểm thử và bảo trì hệ thống. |
| 3 | **Giảng viên hướng dẫn / đánh giá** | Góp ý và đánh giá tài liệu, mô hình, prototype và sản phẩm. |
| 4 | **Doanh nghiệp / nhà đăng tin** | Cung cấp tin tuyển dụng gián tiếp qua Fanpage hoặc LinkedIn. |
| 5 | **Nhà cung cấp dịch vụ và nền tảng bên ngoài** | Cung cấp dịch vụ AI, dữ liệu GitHub công khai và bài đăng mạng xã hội trong phạm vi được phép truy cập. |

### 3.2. Danh sách yêu cầu

Quy ước mã:

- **FR (Functional Requirement):** Yêu cầu chức năng.
- **NFR (Non-functional Requirement):** Yêu cầu phi chức năng.
- **BR (Business Rule):** Quy tắc nghiệp vụ.
- **CV (CV Builder & SeekerBot):** Phân hệ xây dựng CV và hỗ trợ cải thiện nội dung.
- **VMI (Voice Mock Interview):** Phân hệ phỏng vấn thử bằng giọng nói.
- **JM (Job Matching & Skill Gap):** Phân hệ đánh giá độ phù hợp CV với JD và xác định khoảng cách kỹ năng.
- **JT (Job Tracking):** Phân hệ theo dõi tin tuyển dụng.
- **UC (Use Case):** Trường hợp sử dụng.

<a id="yeu-cau-chuc-nang"></a>

#### 3.2.1. Đặc tả yêu cầu chức năng

##### a. CV Builder & SeekerBot

###### Tạo, chỉnh sửa, xem trước và lưu CV

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-01 | Cho phép tạo CV theo các mục và tự điền thông tin cơ bản. |
| FR-CV-02 | Cho phép thêm, sửa từng mục và cập nhật bản xem trước trực tiếp. |
| FR-CV-03 | Kiểm tra trường bắt buộc, định dạng và báo lỗi tại trường. |
| FR-CV-04 | Cho phép lưu CV và mở lại để tiếp tục chỉnh sửa. |
| FR-CV-05 | Cho phép chọn mẫu và xem trước mà không làm mất nội dung CV. |

###### SeekerBot và cải thiện nội dung CV

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-06 | Cho phép yêu cầu SeekerBot hướng dẫn viết từng mục CV. |
| FR-CV-07 | Cho phép chọn đoạn mô tả dự án hoặc kinh nghiệm để nhận gợi ý viết lại theo cấu trúc STAR (tình huống, nhiệm vụ, hành động, kết quả). |
| FR-CV-08 | Nhập JD để nhận gợi ý diễn đạt hoặc nhấn mạnh nội dung CV liên quan. |
| FR-CV-09 | Hiển thị gợi ý cạnh bản gốc để người dùng duyệt, sửa hoặc bỏ qua. |
| FR-CV-10 | Khi AI không phản hồi, thông báo lỗi và giữ nguyên CV. |

###### Hướng dẫn người mới sử dụng

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-11 | Cung cấp hướng dẫn tạo, mở, chọn mẫu, chỉnh sửa, xem trước và lưu CV. |
| FR-CV-12 | Cho phép mở lại hoặc bỏ qua hướng dẫn để vào trình chỉnh sửa; không nhập nội dung CV trong phần hướng dẫn. |

###### Ngân hàng thành tựu và nhập dự án GitHub

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-13 | Cho phép tạo, xem, sửa và xóa thành tựu cá nhân đã lưu. |
| FR-CV-14 | Cho phép sao chép thành tựu đã chọn vào CV để chỉnh sửa độc lập. |
| FR-CV-15 | Cho phép nhập đường dẫn kho mã nguồn GitHub công khai và lấy dữ liệu truy cập được. |
| FR-CV-16 | Cho phép xem, sửa dữ liệu GitHub và xác nhận đóng góp cá nhân trước khi thêm vào CV. |
| FR-CV-17 | Báo lỗi khi đường dẫn không hợp lệ, kho mã nguồn riêng tư, không tồn tại hoặc không truy xuất được. |

###### Nội dung CV song ngữ Việt – Anh

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-18 | Lưu và cho phép chuyển xem hai bản tiếng Việt, tiếng Anh của cùng một CV. |
| FR-CV-19 | Tạo bản nháp ngôn ngữ còn lại, chỉ áp dụng sau khi người dùng duyệt. |
| FR-CV-20 | Báo bản dịch cần kiểm tra lại khi nội dung nguồn thay đổi. |
| FR-CV-21 | Giữ cấu trúc mục và cập nhật bản xem trước theo ngôn ngữ chọn. |

###### Xem trước bố cục trang in

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-22 | Mở **bản xem trước khi in** để xem và kiểm tra bố cục trang in. |
| FR-CV-23 | Hiển thị nội dung, mẫu, ngôn ngữ và phân trang; cho phép quay lại trình chỉnh sửa. |
| FR-CV-24 | Bản xem trước khi in dùng CV hiện có, không dùng AI kiểm lỗi hoặc yêu cầu bổ sung. |

###### Tự điền thông tin cơ bản từ Profile/Account

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-CV-25 | Khi tạo CV, điền ô cơ bản còn trống từ Profile đúng tài khoản; cho phép kiểm tra và sửa. |
| FR-CV-26 | Khi mở CV đã lưu, chỉ điền ô cơ bản còn trống từ Profile, không ghi đè nội dung đã có. |

###### Các quy tắc nghiệp vụ áp dụng

###### BR-CV-01 — Quyền sở hữu CV và thành tựu

Người dùng chỉ được xem, sửa, xóa CV và thành tựu thuộc quyền truy cập của mình.

###### BR-CV-02 — AI chỉ đưa ra gợi ý

Mọi gợi ý SeekerBot/STAR/JD cần được duyệt trước khi áp dụng; không tạo dự án, vai trò, số liệu, chứng chỉ hoặc kinh nghiệm thiếu căn cứ.

###### BR-CV-03 — Phạm vi điều chỉnh theo JD

Điều chỉnh theo JD chỉ dùng **thông tin CV đã có** để cải thiện cách diễn đạt; không chấm điểm hoặc phân tích Skill Gap.

###### BR-CV-04 — Dữ liệu CV dùng chung

Trình chỉnh sửa, mẫu CV, bản xem trước trực tiếp và bản xem trước khi in dùng chung dữ liệu. Đổi mẫu giữ nội dung; lưu/mở lại giữ cả nội dung và mẫu. Hướng dẫn sử dụng không tạo CV.

###### BR-CV-05 — Tái sử dụng thành tựu

Thành tựu được sao chép tại thời điểm chọn; sửa thư viện không cập nhật CV đã có.

###### BR-CV-06 — Nhập nội dung GitHub

Chỉ lấy kho mã nguồn công khai; thông tin mô tả và tệp README không chứng minh đóng góp cá nhân. Người dùng kiểm tra, sửa và xác nhận trước khi thêm vào CV.

###### BR-CV-07 — Chuyển đổi ngôn ngữ

Bản Việt/Anh dùng chung cấu trúc, lưu nội dung riêng. Bản dịch không ghi đè nội dung đã duyệt và cần rà soát khi nguồn đổi.

###### BR-CV-08 — Phạm vi xem trước khi in

SCRUM-49 chỉ xem trước trang in theo nội dung và mẫu hiện tại, không kiểm lỗi bằng AI. In/xuất PDF thuộc SCRUM-16, chờ xác nhận phạm vi.

###### BR-CV-09 — Dữ liệu Profile và CV

Chỉ tự điền ô cơ bản còn trống khi tạo/mở CV từ **Profile tài khoản đang đăng nhập**; người dùng được sửa. Đổi Profile không ghi đè CV đã lưu. Ánh xạ trường chờ đối chiếu schema Profile.

##### b. Voice Mock Interview

###### Thiết lập buổi phỏng vấn

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-01 | Cho phép chọn chuyên môn (Frontend, Backend, Fullstack, Mobile, AI/Data) và cấp độ Intern/Fresher. |
| FR-VMI-02 | Cho phép chọn ngôn ngữ phỏng vấn tiếng Việt hoặc tiếng Anh. |
| FR-VMI-03 | Lấy danh sách CV từ phân hệ CV/Profile và cho phép chọn một CV làm ngữ cảnh phỏng vấn. |
| FR-VMI-04 | Cho phép phỏng vấn theo vị trí mà không cần CV khi tài khoản chưa có hồ sơ. |
| FR-VMI-05 | Gửi vị trí, cấp độ, ngôn ngữ và tóm tắt CV đến AI để khởi tạo ngữ cảnh phiên và khung câu hỏi. |
| FR-VMI-06 | Kiểm tra tính hợp lệ của thiết lập trước khi chuyển sang kiểm tra thiết bị. |

###### Kiểm tra microphone và âm thanh

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-07 | Yêu cầu quyền truy cập microphone từ trình duyệt và kiểm tra thiết bị thu âm trước khi phỏng vấn. |
| FR-VMI-08 | Hiển thị cường độ âm thanh đầu vào theo thời gian thực để kiểm tra microphone. |
| FR-VMI-09 | Báo lỗi và hướng dẫn cấp lại quyền hoặc đổi thiết bị khi microphone không khả dụng. |
| FR-VMI-10 | Cho phép bắt đầu khi kiểm tra thiết bị đạt yêu cầu hoặc người dùng xác nhận sẵn sàng, đồng thời phải có quyền microphone. |

###### Tham gia phỏng vấn bằng giọng nói

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-11 | Chuyển câu hỏi thành giọng nói (TTS) và phát theo ngôn ngữ đã chọn. |
| FR-VMI-12 | Thu câu trả lời qua microphone và gửi AI chuyển thành văn bản (STT). |
| FR-VMI-13 | Hiển thị văn bản nhận diện để người dùng theo dõi, xác nhận gửi hoặc nói lại. |
| FR-VMI-14 | Gửi AI phân tích câu trả lời theo ngữ cảnh CV và vị trí ứng tuyển. |
| FR-VMI-15 | Sinh câu hỏi tiếp theo theo diễn tiến phiên, gồm câu hỏi đào sâu kỹ thuật dựa trên câu trả lời trước. |
| FR-VMI-16 | Cho phép kết thúc bất kỳ lúc nào; tự chuyển sang đánh giá khi đủ số câu hỏi quy định. |

###### Tổng hợp, đánh giá buổi phỏng vấn

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-17 | Tổng hợp transcript gồm toàn bộ câu hỏi và câu trả lời khi phiên kết thúc. |
| FR-VMI-18 | Gửi transcript và cấu hình phiên đến AI để đánh giá kỹ thuật, tư duy giải quyết vấn đề và diễn đạt. |
| FR-VMI-19 | Chỉ rõ điểm mạnh, lỗ hổng kiến thức, hướng trả lời tốt hơn và chủ đề cần ôn tập. |
| FR-VMI-20 | Hiển thị báo cáo đầy đủ, nêu rõ kết quả phục vụ rèn luyện và không phải xác suất trúng tuyển. |

###### Xem lịch sử phỏng vấn

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-21 | Lưu thời điểm, vị trí, cấp độ, ngôn ngữ, CV đã dùng, transcript, điểm và toàn văn báo cáo từng phiên. |
| FR-VMI-22 | Liệt kê phiên mới nhất trước; cho xem lại transcript và báo cáo từng phiên. |
| FR-VMI-23 | Giữ nguyên lịch sử và kết quả khi CV gốc thay đổi. |

###### Xử lý sự cố và gián đoạn

| Mã | Yêu cầu chức năng |
|---|---|
| FR-VMI-27 | Khi mất kết nối hoặc AI lỗi, thông báo và lưu hỏi đáp đã hoàn tất; không tự hủy phiên hoặc trả điểm 0%. |
| FR-VMI-28 | Khi tạo báo cáo bị gián đoạn, giữ transcript và cho tạo lại báo cáo mà không cần phỏng vấn lại. |

###### Các quy tắc nghiệp vụ áp dụng

###### BR-VMI-01 — Cá nhân hóa câu hỏi theo ngữ cảnh và cấp độ

- **Có CV:** Ít nhất 40% câu hỏi chuyên môn dựa trực tiếp trên dự án, công nghệ và kinh nghiệm trong CV.
- **Cấp độ Intern:** Tập trung kiến thức nền tảng (OOP, cấu trúc dữ liệu, cú pháp ngôn ngữ, luồng hoạt động cơ bản của framework).
- **Cấp độ Fresher:** Mở rộng sang tư duy thiết kế kiến trúc, gỡ lỗi, kiểm thử, cơ sở dữ liệu, tối ưu hiệu năng và quy trình nhóm (Git, Agile/Scrum).

###### BR-VMI-02 — Điều kiện kiểm tra thiết bị âm thanh

Bắt buộc có quyền microphone. Nếu mức âm bằng 0 suốt bài thử, cảnh báo và yêu cầu kiểm tra lại thiết bị.

###### BR-VMI-03 — Cấu trúc và thời lượng phiên phỏng vấn

Một phiên chuẩn gồm 5–8 câu hỏi theo 3 giai đoạn:
1. **Mở đầu (1 câu):** Giới thiệu bản thân hoặc định hướng nghề nghiệp.
2. **Chuyên môn & tình huống (3–6 câu):** Câu hỏi kỹ thuật cốt lõi và đào sâu theo CV.
3. **Kết thúc (1 câu):** Tổng kết hoặc cơ hội ứng viên đặt câu hỏi.

Tối đa **3 phút/câu**; hết giờ, thông báo và đề nghị gửi câu trả lời để chuyển câu.

###### BR-VMI-04 — Tiêu chí và công thức tính điểm đánh giá

Tổng điểm theo thang 100, dựa trên 3 tiêu chí:

| Tiêu chí | Trọng số |
|---|:---:|
| Kiến thức kỹ thuật (Technical Knowledge) | 50% |
| Tư duy giải quyết vấn đề (Problem Solving) | 30% |
| Kỹ năng diễn đạt & Phản xạ (Communication & Fluency) | 20% |

```text
Điểm phỏng vấn = (Điểm kỹ thuật × 0.5) + (Điểm tư duy × 0.3) + (Điểm diễn đạt × 0.2)
```

Mỗi tiêu chí được chấm trên thang 100 dựa trên toàn bộ câu trả lời trong transcript.

###### BR-VMI-05 — Phân loại kết quả và định hướng ôn tập

| Mức | Điểm tổng hợp | Khuyến nghị |
|:---:|:---:|---|
| **Đỏ** | Dưới 50 | Ôn tập lại khái niệm kỹ thuật cốt lõi và luyện bộ câu hỏi cơ bản trước khi phỏng vấn thực tế. |
| **Vàng** | 50 đến dưới 75 | Rà soát chi tiết dự án trong CV và rèn luyện kỹ năng tóm tắt câu trả lời súc tích hơn. |
| **Xanh** | Từ 75 trở lên | Thể hiện kiến thức vững và phản xạ giao tiếp tốt; sẵn sàng tham gia phỏng vấn kỹ thuật tại doanh nghiệp. |

Điểm phản ánh phần thể hiện trong phiên phỏng vấn cụ thể, không bảo đảm kết quả tuyển dụng thực tế.

##### c. Job Matching & Skill Gap

###### Tiếp nhận dữ liệu và xác định hướng chuyên môn

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-01 | Cho phép chọn một CV hiện có trong tài khoản để phân tích. |
| FR-JM-02 | Cho phép nhập JD cần đối chiếu. |
| FR-JM-03 | Kiểm tra đầu vào và thông báo nội dung cần bổ sung khi thiếu CV, JD hoặc chưa đủ dữ liệu phân tích. |
| FR-JM-04 | Đề xuất hướng chuyên môn của CV và JD từ tên vị trí và nội dung; cho phép xác nhận hoặc sửa. |
| FR-JM-05 | Cho phép phân tích khi chuyên môn cùng hướng hoặc giao nhau; nếu khác hoàn toàn, giải thích và yêu cầu chọn lại CV hoặc JD. |
| FR-JM-06 | Khi chuyên môn giao nhau, đánh giá toàn bộ yêu cầu JD và chỉ rõ phần liên quan, phần yêu cầu mở rộng. |

###### Bóc tách và xác nhận thông tin

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-07 | Bóc tách yêu cầu JD về chuyên môn, kỹ năng mềm, kinh nghiệm, dự án, ngoại ngữ, học vấn và điều kiện liên quan. |
| FR-JM-08 | Phân loại yêu cầu thành bắt buộc, ưu tiên hoặc không nêu rõ theo JD. |
| FR-JM-09 | Nhận diện bằng chứng trong CV cho từng yêu cầu và lưu đoạn nguồn tương ứng. |
| FR-JM-10 | Chuẩn hóa cách viết đồng nghĩa; nhận diện quan hệ logic “và”, “hoặc”. |
| FR-JM-11 | Hiển thị dữ liệu bóc tách và đoạn nguồn để người dùng kiểm tra, xác nhận trước khi đánh giá. |
| FR-JM-12 | Cho phép sửa lỗi bóc tách theo CV và JD gốc; thông tin mới ngoài CV không làm tăng điểm hiện tại. |

###### Đánh giá mức độ phù hợp

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-13 | Đối chiếu từng yêu cầu JD với bằng chứng CV để xác định mức đáp ứng. |
| FR-JM-14 | Đánh giá năng lực thực hành qua công việc và đóng góp cá nhân trong dự án hoặc kinh nghiệm; chỉ liệt kê kỹ năng, tên dự án hoặc chức danh chưa đủ chứng minh đáp ứng đầy đủ. |
| FR-JM-15 | Tính điểm phần trăm theo trọng số và mức đáp ứng; áp dụng giới hạn nếu yêu cầu bắt buộc chưa được đáp ứng đầy đủ. |
| FR-JM-16 | Phân loại đỏ, vàng, xanh theo điểm cuối. |
| FR-JM-17 | Hiển thị bảng đối chiếu, mức đáp ứng, bằng chứng từng yêu cầu; giải thích điểm và giới hạn điểm nếu có. |
| FR-JM-18 | Khuyến nghị ứng tuyển theo mức phân loại; nêu rõ điểm không phải xác suất được tuyển. |

###### Xác định khoảng trống và hướng cải thiện

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-19 | Liệt kê yêu cầu chưa có đủ bằng chứng trong CV, ưu tiên yêu cầu bắt buộc. |
| FR-JM-20 | Tham chiếu hồ sơ cá nhân để tìm năng lực CV chưa thể hiện rõ; cho phép người dùng xác nhận hoặc bổ sung tình trạng năng lực. |
| FR-JM-21 | Dựa trên hồ sơ cá nhân và xác nhận của người dùng để phân biệt cần bổ sung CV hay học, thực hành thêm; ghi “Chưa xác định” nếu thiếu thông tin. |
| FR-JM-22 | Với năng lực đã có, chỉ rõ nội dung CV cần bổ sung và ví dụ trình bày từ thông tin đã xác nhận. |
| FR-JM-23 | Với năng lực còn thiếu, đề xuất nội dung học và thực hành theo JD. |
| FR-JM-24 | Cung cấp tài liệu liên quan kèm nguồn và đường dẫn đã kiểm chứng. |
| FR-JM-25 | Không tự sửa CV hoặc tạo kỹ năng, kinh nghiệm, chứng chỉ, thành tích thiếu căn cứ; thông tin ngoài CV chỉ phục vụ gợi ý, không đổi điểm hiện tại. |

###### Lưu lịch sử phân tích

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-26 | Lưu CV và JD tại thời điểm phân tích, dữ liệu bóc tách đã xác nhận, bảng đối chiếu, điểm ban đầu, điểm cuối, mức phân loại và gợi ý đã tạo. |
| FR-JM-27 | Cho phép xem danh sách và chi tiết các lần phân tích của mình. |
| FR-JM-29 | Giữ nguyên dữ liệu và kết quả lịch sử khi CV gốc thay đổi. |

###### Xử lý trường hợp không thể hoàn thành phân tích

| Mã | Yêu cầu chức năng |
|---|---|
| FR-JM-30 | Khi thiếu dữ liệu hoặc phân tích thất bại, nêu lý do chưa thể đánh giá và cho phép bổ sung dữ liệu hoặc thử lại; không trả điểm 0%. |
| FR-JM-31 | Nếu tạo gợi ý hoặc lấy tài liệu thất bại, giữ và hiển thị kết quả matching; cho phép thử lại phần lỗi. |

###### Các quy tắc nghiệp vụ áp dụng

###### BR-JM-01 — Xác định hướng chuyên môn

Xét chuyên môn từ tên vị trí và nội dung bóc tách, không yêu cầu tên vị trí trùng nhau. Ví dụ: React Developer/Angular Intern cùng hướng Frontend; Frontend/Fullstack giao nhau nhưng vẫn xét yêu cầu Backend; Frontend/Backend khác hướng nếu không có nội dung giao nhau.

###### BR-JM-02 — Diễn giải yêu cầu kết hợp

- **“Và”:** Đánh giá từng điều kiện; chỉ đạt đầy đủ khi đạt tất cả.
- **“Hoặc”:** Đạt đầy đủ một lựa chọn là đủ; không trừ điểm vì thiếu lựa chọn còn lại.

###### BR-JM-03 — Trọng số yêu cầu

| Loại yêu cầu | Trọng số |
|---|---:|
| Bắt buộc | 2 |
| Ưu tiên | 1 |
| Không nêu rõ | 1 |

Yêu cầu không nêu rõ mức độ không được tự xem là bắt buộc để áp dụng giới hạn điểm.

###### BR-JM-04 — Mức đáp ứng

| Mức đáp ứng | Căn cứ đánh giá |
|---|---|
| **0%** | Chưa có bằng chứng liên quan trong CV. |
| **25%** | Có nhắc đến nhưng chưa chứng minh đáp ứng yêu cầu. |
| **50%** | Có bằng chứng cụ thể nhưng chỉ đáp ứng một phần yêu cầu. |
| **100%** | Có bằng chứng cụ thể đáp ứng đầy đủ yêu cầu. |

Bằng chứng phải phù hợp yêu cầu; độ dài mô tả hoặc tên dự án không quyết định điểm. Học vấn, ngoại ngữ và điều kiện khác dùng thông tin tương ứng trong CV; năng lực thực hành ưu tiên mô tả việc đã làm và đóng góp cá nhân.

###### BR-JM-05 — Công thức điểm và giới hạn

```text
Điểm ban đầu =
Σ(trọng số yêu cầu × mức đáp ứng)
÷ Σ(trọng số yêu cầu)
× 100
```

Mức đáp ứng trong công thức sử dụng các giá trị `0`, `0.25`, `0.5` và `1`.

Nếu có bất kỳ yêu cầu bắt buộc nào chưa đáp ứng đầy đủ:

```text
Điểm cuối = min(Điểm ban đầu, 79%)
```

Nếu tất cả yêu cầu bắt buộc được đáp ứng đầy đủ, điểm cuối bằng điểm ban đầu.

###### BR-JM-06 — Phân loại và khuyến nghị

| Mức | Điểm cuối | Khuyến nghị |
|---|---|---|
| **Đỏ** | Dưới 50% | Ưu tiên cải thiện trước khi ứng tuyển. |
| **Vàng** | Từ 50% đến dưới 80% | Khuyến khích cân nhắc ứng tuyển, đồng thời cải thiện những điểm còn thiếu. |
| **Xanh** | Từ 80% trở lên | CV thể hiện mức đáp ứng tốt đối với các yêu cầu được đánh giá. |

Điểm chỉ phản ánh **bằng chứng trong CV tại thời điểm phân tích**, không đại diện toàn bộ năng lực. Trọng số và ngưỡng là quy tắc dự kiến, cần kiểm tra trên bộ CV và JD mẫu.

##### d. Job Tracking

###### Quản lý nguồn tuyển dụng cần theo dõi

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-JT-01 | Hiển thị nguồn của người dùng: tên, nền tảng, đường dẫn, trạng thái theo dõi và truy cập. |
| FR-JT-02 | Cho phép thêm nguồn bằng đường dẫn Fanpage hoặc LinkedIn được hỗ trợ; báo lỗi khi đường dẫn rỗng, sai định dạng hoặc không được hỗ trợ. |
| FR-JT-03 | Cho phép xóa quan hệ theo dõi của tài khoản hiện tại, giữ nguyên nguồn và quan hệ của người khác. |
| FR-JT-04 | Cho phép tạm dừng và tiếp tục theo dõi; ngừng phân phối tin và thông báo mới cho người tạm dừng. |
| FR-JT-05 | Kiểm tra nguồn khi thêm và định kỳ; hiển thị truy cập được, không truy cập được hoặc chưa kiểm tra, kèm lần kiểm tra gần nhất. |

###### Nhận và quản lý tin từ nguồn đang theo dõi

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-JT-06 | Kiểm tra nguồn đang bật theo chu kỳ cấu hình, không cần người dùng mở trang. |
| FR-JT-07 | Lưu bài nhận được cùng nội dung, nguồn, đường dẫn gốc, thời gian đăng (nếu có) và thời gian thu thập để sàng lọc, xem lại. |
| FR-JT-08 | Cho phép lưu và bỏ lưu tin quan tâm trong danh sách cá nhân. |
| FR-JT-09 | Cho phép xóa tin cá nhân sau khi xác nhận; không xóa dữ liệu chung hoặc tin của người khác. |
| FR-JT-10 | Lưu hạn ứng tuyển nếu xác định được; cập nhật Còn hạn, Hết hạn hoặc Chưa xác định. |

###### Sàng lọc và cá nhân hóa kết quả

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-JT-11 | Dùng AI phân biệt tin tuyển IT Intern/Fresher với tin không liên quan hoặc chỉ tuyển cấp độ khác; giữ Chưa xác định khi thiếu căn cứ. |
| FR-JT-12 | Lưu phân loại và thông tin từ nguồn: vị trí, doanh nghiệp, cấp độ, địa điểm, yêu cầu, hạn nộp và cách ứng tuyển. |
| FR-JT-13 | Hiển thị tin đã sàng lọc kèm nguồn và thời gian; sắp xếp mới nhất trước và cho phép mở chi tiết. |
| FR-JT-14 | Cá nhân hóa theo nguồn theo dõi và thông tin quan tâm của đúng tài khoản; nếu chưa có thông tin quan tâm, trả tin IT Intern/Fresher từ nguồn theo dõi. |
| FR-JT-15 | Phân biệt đang tải, chưa có nguồn, chưa có tin phù hợp và lỗi lấy kết quả; không coi bài chưa phân loại là tin phù hợp. |

###### Thông báo cơ hội tuyển dụng

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-JT-16 | Tạo thông báo cho người đang bật theo dõi khi có tin mới đã sàng lọc phù hợp và chưa được xác định hết hạn. |
| FR-JT-17 | Thông báo gồm vị trí hoặc tiêu đề, doanh nghiệp hoặc nguồn, thời điểm tạo và liên kết đến đúng tin chi tiết. |
| FR-JT-18 | Kiểm tra thời hạn khi tạo thông báo và khi mở danh sách, chi tiết thông báo; hiển thị “Hết hạn” hoặc “Chưa xác định” theo tin liên quan. |

###### Chi tiết tin và bài đăng gốc

| Mã | Yêu cầu chức năng |
| --- | --- |
| FR-JT-19 | Hiển thị nội dung đã lưu, thông tin trích xuất và trạng thái thời hạn; ghi Chưa có thông tin ở trường thiếu dữ liệu. |
| FR-JT-20 | Phân biệt nội dung nguồn với nội dung AI tóm tắt hoặc trích xuất; hiển thị nguồn và thời điểm cập nhật. |
| FR-JT-21 | Cho phép mở đúng bài gốc bằng đường dẫn hợp lệ; không tạo liên kết giả khi thiếu đường dẫn. |
| FR-JT-22 | Nếu bài gốc bị xóa hoặc yêu cầu đăng nhập, vẫn hiển thị nội dung đã lưu thuộc quyền truy cập và thời điểm cập nhật. |

###### Các quy tắc nghiệp vụ áp dụng

###### BR-JT-01 — Quyền sở hữu dữ liệu cá nhân

Nguồn theo dõi, tin cá nhân và thông báo gắn với đúng tài khoản. Backend phải kiểm tra quyền; ẩn nút giao diện không thay thế phân quyền.

###### BR-JT-02 — Nguồn và nhà đăng tin

Nhà đăng tin được đại diện bằng Fanpage/LinkedIn doanh nghiệp; thêm/xóa chỉ đổi quan hệ theo dõi, không đổi tài khoản doanh nghiệp. Trạng thái theo dõi độc lập với khả năng truy cập; lỗi truy cập không chứng minh ngừng tuyển hoặc đóng trang.

###### BR-JT-03 — Theo dõi theo chu kỳ

Phân phối tin mới theo chu kỳ; tạm dừng theo dõi giữ tin và thông báo cũ, tiếp tục theo dõi có hiệu lực từ lượt kiểm tra sau. Chu kỳ và mốc lấy bài lần đầu theo cấu hình thống nhất, không cam kết tức thời.

###### BR-JT-04 — Lưu và xóa tin

Phân biệt hệ thống lưu bài thu thập với người dùng lưu tin quan tâm. Xóa tin khỏi danh sách cá nhân không làm mất bài gốc trên hệ thống; tin đã xóa không tự xuất hiện lại khi tải lại. Phân phối lại bài nguồn cập nhật cần thống nhất riêng.

###### BR-JT-05 — Phân loại và dữ liệu AI

Chỉ giữ tin phù hợp khi có căn cứ đang tuyển IT Intern/Fresher, kể cả bài nhiều vị trí. Nhắc Intern/Fresher trong bài tổng kết chưa đủ căn cứ. Không tự tạo doanh nghiệp, lương, thời hạn hoặc yêu cầu ngoài nguồn.

###### BR-JT-06 — Cá nhân hóa kết quả

Cá nhân hóa theo thông tin quan tâm đã lưu của tài khoản, không mặc định đọc CV hoặc chấm điểm phù hợp. Thống nhất trường sở thích và cách ưu tiên với Profile/Account trước khi triển khai.

###### BR-JT-07 — Thời hạn tuyển dụng

Tin hết hạn khi đạt hoặc vượt mốc đóng tuyển; hạn chỉ có ngày tính đến hết ngày theo Asia/Ho_Chi_Minh. Thông báo đóng tuyển rõ ràng từ nguồn cũng xác định hết hạn. Hạn thiếu hoặc mơ hồ ghi Chưa xác định, không tự đặt thời hạn chung.

###### BR-JT-08 — Thời hạn của thông báo

Thông báo dùng thời hạn của tin, không có hạn riêng: tin hết hạn thì ghi Hết hạn, giữ thông báo cũ và không tạo thông báo mới. Chưa xác định không đồng nghĩa Còn hạn.

###### BR-JT-09 — Chi tiết và liên kết nguồn

Nội dung lưu phản ánh thời điểm thu thập/cập nhật, có thể khác bản mới nhất. Mở bài gốc điều hướng ra nền tảng ngoài; hệ thống không nộp hồ sơ thay hoặc xác nhận kết quả ứng tuyển.

<a id="yeu-cau-phi-chuc-nang"></a>

#### 3.2.2. Đặc tả yêu cầu phi chức năng

##### a. CV Builder & SeekerBot

| Mã | Nhóm | Yêu cầu phi chức năng |
| --- | --- | --- |
| <a id="nfr-cv-01"></a>NFR-CV-01 | Dễ sử dụng | Chỉ rõ mục đang chỉnh sửa, hiển thị bản xem trước dễ đọc và hướng dẫn sửa lỗi. |
| <a id="nfr-cv-02"></a>NFR-CV-02 | Bảo mật | Chỉ người có quyền được truy cập CV và thành tựu; khóa AI, GitHub được giữ ở máy chủ. |
| <a id="nfr-cv-03"></a>NFR-CV-03 | Tin cậy | Lỗi AI hoặc GitHub không làm mất CV, gián đoạn lưu và chỉnh sửa; gợi ý chỉ được áp dụng sau khi duyệt. |
| <a id="nfr-cv-05"></a>NFR-CV-05 | Khả năng đọc | Trang in không cắt hoặc chồng lấn nội dung quan trọng trong các mẫu được hỗ trợ. |

##### b. Voice Mock Interview

| Mã | Nhóm | Yêu cầu phi chức năng |
| --- | --- | --- |
| <a id="nfr-vmi-01"></a>NFR-VMI-01 | Hiệu năng | Khi mạng ổn định, thời gian từ khi trả lời xong đến khi phát câu hỏi tiếp theo không quá 5 giây. |
| <a id="nfr-vmi-02"></a>NFR-VMI-02 | Dễ sử dụng | Sóng âm thể hiện rõ trạng thái nghe, nói; câu hỏi, bản nhận diện giọng nói và báo cáo hỗ trợ tiếng Việt, tiếng Anh. |
| <a id="nfr-vmi-03"></a>NFR-VMI-03 | Bảo mật | Chỉ tài khoản sở hữu được truy cập âm thanh, bản ghi hội thoại và báo cáo; khóa AI được bảo vệ ở máy chủ. |
| <a id="nfr-vmi-04"></a>NFR-VMI-04 | Tin cậy | Giữ dữ liệu hỏi đáp khi phiên gián đoạn và cho phép tạo lại báo cáo mà không mất dữ liệu. |

##### c. Job Matching & Skill Gap

| Mã | Nhóm | Yêu cầu phi chức năng |
| --- | --- | --- |
| <a id="nfr-jm-01"></a>NFR-JM-01 | Dễ sử dụng | Giao diện dùng tiếng Việt dễ hiểu; điểm và mức đánh giá được giải thích bằng nhãn chữ và màu sắc. |
| <a id="nfr-jm-02"></a>NFR-JM-02 | Bảo mật | Chỉ người có quyền được truy cập CV, hồ sơ cá nhân và lịch sử; khóa AI được giữ ở máy chủ. |
| <a id="nfr-jm-03"></a>NFR-JM-03 | Nhất quán | Cùng dữ liệu đã xác nhận và phiên bản công thức phải cho cùng điểm và mức phân loại. |
| <a id="nfr-jm-04"></a>NFR-JM-04 | Tin cậy | Lỗi tạo gợi ý hoặc lấy tài liệu không làm mất kết quả matching đã hoàn thành và lưu thành công. |

##### d. Job Tracking

| Mã | Nhóm | Yêu cầu phi chức năng |
| --- | --- | --- |
| <a id="nfr-jt-01"></a>NFR-JT-01 | Dễ sử dụng | Trạng thái theo dõi, truy cập nguồn và thời hạn tin có nhãn chữ; nội dung tiếng Việt, nội dung dài và trường thiếu không che khuất nút trên thiết bị được hỗ trợ. |
| <a id="nfr-jt-02"></a>NFR-JT-02 | Bảo mật | Ngăn truy cập dữ liệu cá nhân của tài khoản khác, kể cả khi thay mã định danh trong yêu cầu; khóa dịch vụ chỉ nằm ở máy chủ. |
| <a id="nfr-jt-03"></a>NFR-JT-03 | Toàn vẹn dữ liệu | Tạm dừng hoặc xóa dữ liệu cá nhân không ảnh hưởng người khác; không báo thành công khi lưu thất bại. |
| <a id="nfr-jt-04"></a>NFR-JT-04 | Nhất quán | Danh sách, chi tiết và thông báo thống nhất kết quả phân loại, trạng thái thời hạn tại cùng thời điểm. |
| <a id="nfr-jt-05"></a>NFR-JT-05 | Khả năng đáp ứng | Thu thập dữ liệu và gọi AI không cản trở xem tin đã lưu; hiển thị trạng thái đang tải. Chu kỳ quét và thời gian phản hồi mục tiêu chờ đo trên cấu hình thử nghiệm. |
| <a id="nfr-jt-07"></a>NFR-JT-07 | Kiểm chứng được | Lưu nguồn, thời điểm thu thập, kiểm tra và căn cứ thời hạn; đánh giá AI trên bộ tin có nhãn phù hợp, không phù hợp và chưa rõ. |

---

<a id="dac-ta-yeu-cau"></a>

## 4. ĐẶC TẢ YÊU CẦU

<a id="so-do-use-case"></a>

### 4.1. Sơ đồ Use Case

#### a. CV Builder & SeekerBot

![Sơ đồ Use Case UML của CV Builder & SeekerBot](./images/CV_Builder_Use_Case.png)

#### b. Voice Mock Interview

![Sơ đồ Use Case](./images/Voice_Mock_Interview_Use_Case.png)

#### c. Job Matching & Skill Gap

![Sơ đồ Use Case](./images/Job_Matching_Use_Case.png)

#### d. Job Tracking

![Sơ đồ Use Case của Job Tracking](./images/Job_Tracking_Use_Case.png)

<a id="dac-ta-use-case"></a>

### 4.2. Đặc tả Use Case

#### a. CV Builder & SeekerBot

##### Tạo, chỉnh sửa và xem trước CV

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-01"></a>UC-CV-01 |
| **Tên Use Case** | Tạo, chỉnh sửa và xem trước CV |
| **Tóm tắt** | Tạo, sửa CV và xem trước trực tiếp. |
| **Tác nhân** | Sinh viên/người tìm việc; phân hệ Profile/Account. |
| **Điều kiện tiên quyết** | Người dùng đã đăng nhập. |
| **Kết quả** | Bản xem trước phản ánh dữ liệu chỉnh sửa hợp lệ. |
| **Kịch bản chính** | 1. Người dùng tạo hoặc mở CV.<br>2. Hệ thống điền ô cơ bản còn trống từ Profile đúng tài khoản, giữ dữ liệu đã lưu.<br>3. Người dùng chỉnh sửa; hệ thống cập nhật bản xem trước. |
| **Kịch bản phụ** | • Profile thiếu dữ liệu: cho nhập tay.<br>• Dữ liệu sai: chỉ rõ trường cần sửa.<br>• Rời trang chưa lưu: cảnh báo mất thay đổi. |
| **Ràng buộc phi chức năng** | [NFR-CV-01](#nfr-cv-01); đảm bảo toàn vẹn dữ liệu dùng chung giữa các phân hệ. |

##### Lưu và mở lại CV

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-02"></a>UC-CV-02 |
| **Tên Use Case** | Lưu và mở lại CV |
| **Tóm tắt** | Lưu CV và mở lại để chỉnh sửa. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Đã đăng nhập và có CV cần lưu hoặc mở. |
| **Kết quả** | Nội dung và mẫu CV được lưu, mở đúng tài khoản. |
| **Kịch bản chính** | 1. Người dùng chọn lưu CV.<br>2. Hệ thống lưu nội dung và mẫu.<br>3. Người dùng mở CV đã lưu; hệ thống hiển thị nội dung và bản xem trước. |
| **Kịch bản phụ** | • Lưu lỗi: thông báo chưa lưu, cho thử lại.<br>• Không có quyền: từ chối mở CV. |
| **Ràng buộc phi chức năng** | [NFR-CV-02](#nfr-cv-02), [NFR-CV-03](#nfr-cv-03). |

##### Chọn mẫu trình bày CV

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-03"></a>UC-CV-03 |
| **Tên Use Case** | Chọn mẫu trình bày CV |
| **Tóm tắt** | Đổi mẫu, giữ nguyên nội dung CV. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Đang chỉnh sửa CV. |
| **Kết quả** | Bản xem trước áp dụng mẫu đã chọn. |
| **Kịch bản chính** | 1. Người dùng mở danh sách mẫu.<br>2. Chọn mẫu; hệ thống cập nhật bản xem trước và giữ nội dung. |
| **Kịch bản phụ** | • Mẫu lỗi: giữ mẫu cũ và thông báo. |
| **Ràng buộc phi chức năng** | [NFR-CV-01](#nfr-cv-01); giữ nguyên dữ liệu nội dung khi chuyển đổi mẫu. |

##### Nhận và duyệt gợi ý từ SeekerBot

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-04"></a>UC-CV-04 |
| **Tên Use Case** | Nhận và duyệt gợi ý từ SeekerBot |
| **Tóm tắt** | Nhận gợi ý hướng dẫn, STAR hoặc điều chỉnh theo JD. |
| **Tác nhân** | Sinh viên/người tìm việc; dịch vụ AI. |
| **Điều kiện tiên quyết** | Có mục CV cần hỗ trợ; chế độ theo JD cần có JD. |
| **Kết quả** | CV chỉ cập nhật phần gợi ý được duyệt. |
| **Kịch bản chính** | 1. Người dùng chọn chế độ hỗ trợ.<br>2. Hệ thống gửi ngữ cảnh đến AI và hiển thị gợi ý cạnh bản gốc.<br>3. Người dùng duyệt, sửa hoặc bỏ qua; hệ thống chỉ áp dụng phần được duyệt. |
| **Kịch bản phụ** | • Thiếu dữ liệu hoặc JD: yêu cầu bổ sung.<br>• AI lỗi: giữ CV, cho thử lại.<br>• Gợi ý sai thực tế: cho sửa hoặc bỏ qua. |
| **Ràng buộc phi chức năng** | [NFR-CV-02](#nfr-cv-02), [NFR-CV-03](#nfr-cv-03). |

##### Xem hướng dẫn sử dụng CV Builder

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-05"></a>UC-CV-05 |
| **Tên Use Case** | Xem hướng dẫn sử dụng CV Builder |
| **Tóm tắt** | Giới thiệu thao tác sử dụng CV Builder. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Người dùng mở CV Builder. |
| **Kết quả** | Người dùng vào trình chỉnh sửa hoặc mở lại hướng dẫn sau. |
| **Kịch bản chính** | 1. Mở hướng dẫn ở lần đầu sử dụng hoặc từ mục trợ giúp.<br>2. Xem, chuyển tiếp hoặc quay lại các bước tạo, mở, chọn mẫu, sửa, xem trước và lưu CV.<br>3. Kết thúc để vào trình chỉnh sửa. |
| **Kịch bản phụ** | • Bỏ qua hoặc đóng: thoát, giữ nguyên CV; có thể mở lại từ trợ giúp. |
| **Ràng buộc phi chức năng** | [NFR-CV-01](#nfr-cv-01); giao diện hướng dẫn trực quan, không làm thay đổi dữ liệu CV. |

##### Quản lý ngân hàng thành tựu cá nhân

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-06"></a>UC-CV-06 |
| **Tên Use Case** | Quản lý ngân hàng thành tựu cá nhân |
| **Tóm tắt** | Quản lý và tái sử dụng thành tựu cá nhân. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Người dùng đã đăng nhập. |
| **Kết quả** | Thành tựu được cập nhật hoặc sao chép vào CV. |
| **Kịch bản chính** | 1. Người dùng mở thư viện thành tựu.<br>2. Tạo, sửa hoặc xóa mục.<br>3. Chọn mục để sao chép vào CV và chỉnh sửa độc lập. |
| **Kịch bản phụ** | • Thư viện trống: hướng dẫn tạo mục.<br>• Không có quyền: từ chối thao tác. |
| **Ràng buộc phi chức năng** | [NFR-CV-02](#nfr-cv-02); dữ liệu thành tựu cá nhân lưu trữ độc lập và bảo mật. |

##### Nhập dự án từ GitHub

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-07"></a>UC-CV-07 |
| **Tên Use Case** | Nhập dự án từ GitHub |
| **Tóm tắt** | Tạo bản nháp dự án từ kho mã nguồn công khai. |
| **Tác nhân** | Sinh viên/người tìm việc; GitHub API. |
| **Điều kiện tiên quyết** | Đã đăng nhập và có đường dẫn kho mã nguồn cần nhập. |
| **Kết quả** | Dự án được thêm vào CV sau khi xác nhận. |
| **Kịch bản chính** | 1. Người dùng nhập đường dẫn; hệ thống lấy thông tin mô tả và README khả dụng.<br>2. Người dùng kiểm tra bản nháp, xác nhận đóng góp và sửa mô tả.<br>3. Chọn thêm vào CV. |
| **Kịch bản phụ** | • Đường dẫn sai, kho riêng tư hoặc không tồn tại: báo lỗi.<br>• Thiếu README: dùng thông tin mô tả khả dụng.<br>• API lỗi: cho thử lại hoặc nhập tay. |
| **Ràng buộc phi chức năng** | [NFR-CV-02](#nfr-cv-02), [NFR-CV-03](#nfr-cv-03). |

##### Chuyển đổi nội dung CV Việt – Anh

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-08"></a>UC-CV-08 |
| **Tên Use Case** | Chuyển đổi nội dung CV Việt – Anh |
| **Tóm tắt** | Quản lý hai bản tiếng Việt và tiếng Anh của CV. |
| **Tác nhân** | Sinh viên/người tìm việc; dịch vụ AI. |
| **Điều kiện tiên quyết** | Đã có CV và chọn ngôn ngữ đích. |
| **Kết quả** | Bản xem trước dùng ngôn ngữ đã chọn; bản dịch chỉ lưu sau khi duyệt. |
| **Kịch bản chính** | 1. Người dùng chọn tiếng Việt hoặc tiếng Anh.<br>2. Hệ thống hiển thị bản đã có hoặc bản nháp dịch.<br>3. Người dùng kiểm tra, sửa và xác nhận lưu; hệ thống cập nhật bản xem trước. |
| **Kịch bản phụ** | • Dịch lỗi: giữ hai bản hiện có.<br>• Nguồn thay đổi: đánh dấu bản dịch cần rà soát. |
| **Ràng buộc phi chức năng** | [NFR-CV-03](#nfr-cv-03), [NFR-CV-05](#nfr-cv-05); đồng bộ và lưu trữ độc lập hai phiên bản ngôn ngữ. |

##### Xem trước bố cục trang in

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-cv-09"></a>UC-CV-09 |
| **Tên Use Case** | Xem trước bố cục trang in |
| **Tóm tắt** | Kiểm tra bố cục CV theo trang in. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Có CV đang mở trong trình chỉnh sửa. |
| **Kết quả** | Hiển thị bố cục theo nội dung, mẫu và ngôn ngữ hiện tại. |
| **Kịch bản chính** | 1. Người dùng chọn xem trước khi in.<br>2. Hệ thống hiển thị nội dung và phân trang.<br>3. Người dùng rà soát, quay lại chỉnh sửa nếu cần. |
| **Kịch bản phụ** | • CV trống: hướng dẫn quay lại chỉnh sửa.<br>• Dựng trang lỗi: thông báo, cho thử lại và giữ nguyên CV. |
| **Ràng buộc phi chức năng** | [NFR-CV-01](#nfr-cv-01), [NFR-CV-05](#nfr-cv-05); hiển thị trung thực định dạng in ấn chuẩn trang A4. |

#### b. Voice Mock Interview

##### Thiết lập buổi phỏng vấn

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-vmi-01"></a>UC-VMI-01 |
| **Tên Use Case** | Thiết lập buổi phỏng vấn |
| **Tóm tắt** | Cấu hình phiên phỏng vấn. |
| **Tác nhân** | Sinh viên; phân hệ CV/Profile; dịch vụ AI. |
| **Điều kiện tiên quyết** | Sinh viên đã đăng nhập. |
| **Kết quả** | Cấu hình hợp lệ, sẵn sàng kiểm tra thiết bị. |
| **Kịch bản chính** | 1. Sinh viên mở phỏng vấn thử; hệ thống tải danh sách CV.<br>2. Chọn vị trí, cấp độ, ngôn ngữ và CV, rồi xác nhận.<br>3. Hệ thống kiểm tra, gửi cấu hình đến AI để tạo ngữ cảnh và chuyển sang kiểm tra thiết bị. |
| **Kịch bản phụ** | • Chưa có CV: cho phỏng vấn theo vị trí.<br>• Thiếu dữ liệu: yêu cầu bổ sung.<br>• AI không phản hồi: thông báo, cho thử lại. |
| **Ràng buộc phi chức năng** | [NFR-VMI-02](#nfr-vmi-02), [NFR-VMI-03](#nfr-vmi-03). |

##### Tham gia phỏng vấn bằng giọng nói

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-vmi-02"></a>UC-VMI-02 |
| **Tên Use Case** | Tham gia phỏng vấn bằng giọng nói |
| **Tóm tắt** | Hỏi đáp bằng giọng nói với AI. |
| **Tác nhân** | Sinh viên; dịch vụ AI. |
| **Điều kiện tiên quyết** | Đã thiết lập phiên thành công ([UC-VMI-01](#uc-vmi-01)). |
| **Kết quả** | Phiên hoàn tất; bản ghi hội thoại và báo cáo được lưu. |
| **Kịch bản chính** | 1. Thực hiện [UC-VMI-03](#uc-vmi-03) — Kiểm tra microphone và âm thanh.<br>2. AI phát câu hỏi; sinh viên trả lời qua microphone.<br>3. Hệ thống hiển thị văn bản nhận diện để sinh viên xác nhận gửi.<br>4. AI phân tích và tạo câu hỏi tiếp theo; lặp đến khi đủ câu hoặc sinh viên kết thúc.<br>5. Thực hiện [UC-VMI-04](#uc-vmi-04) — Tổng hợp, đánh giá và hiển thị báo cáo. |
| **Kịch bản phụ** | • Nhận diện sai: cho nói lại; nghe chưa rõ: cho nhắc lại câu hỏi.<br>• Mất kết nối: giữ dữ liệu, cho kết nối lại hoặc kết thúc sớm.<br>• Hủy phiên: cảnh báo phiên chưa hoàn thành không được tính điểm. |
| **Ràng buộc phi chức năng** | [NFR-VMI-01](#nfr-vmi-01); hiển thị sóng âm trực quan và bảo mật đường truyền âm thanh. |

##### Kiểm tra microphone và âm thanh

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-vmi-03"></a>UC-VMI-03 |
| **Tên Use Case** | Kiểm tra microphone và âm thanh |
| **Tóm tắt** | Kiểm tra microphone và loa hoặc tai nghe. |
| **Tác nhân** | Sinh viên. |
| **Điều kiện tiên quyết** | Đã thiết lập phiên ([UC-VMI-01](#uc-vmi-01)). |
| **Kết quả** | Thiết bị được xác nhận để tiếp tục phỏng vấn. |
| **Kịch bản chính** | 1. Hệ thống yêu cầu quyền microphone; sinh viên cấp quyền và nói thử.<br>2. Hệ thống hiển thị âm lượng, phát âm thanh mẫu; sinh viên xác nhận nghe rõ.<br>3. Sinh viên chọn sẵn sàng để tiếp tục [UC-VMI-02](#uc-vmi-02). |
| **Kịch bản phụ** | • Chưa cấp quyền: hướng dẫn cấp lại.<br>• Không có tín hiệu: hướng dẫn kiểm tra hoặc đổi microphone.<br>• Không nghe âm mẫu: hướng dẫn kiểm tra âm lượng hoặc đổi thiết bị đầu ra. |
| **Ràng buộc phi chức năng** | [NFR-VMI-02](#nfr-vmi-02); phản hồi âm lượng theo thời gian thực. |

##### Tổng hợp, đánh giá buổi phỏng vấn

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-vmi-04"></a>UC-VMI-04 |
| **Tên Use Case** | Tổng hợp, đánh giá buổi phỏng vấn |
| **Tóm tắt** | Chấm điểm và đề xuất cải thiện từ bản ghi hội thoại. |
| **Tác nhân** | Sinh viên; dịch vụ AI. |
| **Điều kiện tiên quyết** | Phiên đã kết thúc do đủ câu hỏi hoặc sinh viên chủ động kết thúc. |
| **Kết quả** | Báo cáo được hiển thị và lưu. |
| **Kịch bản chính** | 1. Hệ thống gửi toàn bộ bản ghi hội thoại và cấu hình đến AI.<br>2. AI đánh giá ba tiêu chí, xác định điểm mạnh, điểm yếu và gợi ý ôn tập.<br>3. Hệ thống tính điểm và phân loại theo quy tắc đánh giá phỏng vấn, lưu và hiển thị báo cáo. |
| **Kịch bản phụ** | • AI lỗi: giữ bản ghi, cho tạo lại báo cáo.<br>• Chưa có câu trả lời: báo không đủ dữ liệu, không lưu kết quả đánh giá. |
| **Ràng buộc phi chức năng** | [NFR-VMI-02](#nfr-vmi-02), [NFR-VMI-04](#nfr-vmi-04); kết quả đánh giá nhất quán và minh bạch. |

##### Xem lịch sử phỏng vấn

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-vmi-05"></a>UC-VMI-05 |
| **Tên Use Case** | Xem lịch sử phỏng vấn |
| **Tóm tắt** | Xem lại các phiên phỏng vấn. |
| **Tác nhân** | Sinh viên. |
| **Điều kiện tiên quyết** | Sinh viên đã đăng nhập. |
| **Kết quả** | Hiển thị danh sách hoặc chi tiết phiên đã lưu. |
| **Kịch bản chính** | 1. Sinh viên mở lịch sử; hệ thống liệt kê ngày, vị trí, ngôn ngữ, điểm và mức phân loại.<br>2. Chọn phiên để xem cấu hình, CV, bản ghi hội thoại và báo cáo.<br>3. Có thể chọn phỏng vấn lại để tạo phiên mới với cấu hình cũ. |
| **Kịch bản phụ** | • Chưa có lịch sử: hướng dẫn tạo phiên mới.<br>• Không có quyền: từ chối truy cập. |
| **Ràng buộc phi chức năng** | [NFR-VMI-03](#nfr-vmi-03); ảnh chụp kết quả lịch sử được bảo toàn nguyên vẹn. |

#### c. Job Matching & Skill Gap

##### Đánh giá mức phù hợp CV–JD

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-jm-01"></a>UC-JM-01 |
| **Tên Use Case** | Đánh giá mức phù hợp CV–JD |
| **Tóm tắt** | Đối chiếu CV với JD, trả điểm và giải thích. |
| **Tác nhân** | Sinh viên; phân hệ CV/Profile; dịch vụ AI. |
| **Điều kiện tiên quyết** | Đã đăng nhập và có CV trong hệ thống. |
| **Kết quả** | Kết quả được hiển thị và lưu vào lịch sử. |
| **Kịch bản chính** | 1. Sinh viên chọn CV và nhập JD.<br>2. Hệ thống bóc tách thông tin, đề xuất chuyên môn và thực hiện [UC-JM-02](#uc-jm-02) để xác nhận.<br>3. Hệ thống kiểm tra chuyên môn, đối chiếu và tính điểm theo quy tắc đánh giá phù hợp.<br>4. Hiển thị điểm, mức phân loại, bằng chứng, giải thích và lưu kết quả. |
| **Kịch bản phụ** | • Thiếu dữ liệu: yêu cầu bổ sung.<br>• Khác hướng hoàn toàn: yêu cầu chọn lại CV hoặc JD.<br>• Phân tích lỗi: thông báo, cho thử lại; không trả điểm 0%. |
| **Ràng buộc phi chức năng** | [NFR-JM-01](#nfr-jm-01), [NFR-JM-02](#nfr-jm-02), [NFR-JM-03](#nfr-jm-03). |

##### Kiểm tra và xác nhận thông tin bóc tách

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-jm-02"></a>UC-JM-02 |
| **Tên Use Case** | Kiểm tra và xác nhận thông tin bóc tách |
| **Tóm tắt** | Kiểm tra dữ liệu bóc tách trước khi đánh giá. |
| **Tác nhân** | Sinh viên. |
| **Điều kiện tiên quyết** | Hệ thống đã bóc tách thông tin CV và JD. |
| **Kết quả** | Dữ liệu được xác nhận để tính điểm; CV gốc không bị thay đổi. |
| **Kịch bản chính** | 1. Hệ thống hiển thị chuyên môn, yêu cầu JD và bằng chứng CV kèm đoạn nguồn.<br>2. Sinh viên sửa lỗi đọc hiểu theo nội dung gốc, không thêm thông tin ngoài CV để tăng điểm.<br>3. Sinh viên xác nhận; hệ thống tiếp tục đánh giá. |
| **Kịch bản phụ** | • Thông tin chưa rõ: đối chiếu và điều chỉnh theo nguồn.<br>• Chưa xác nhận hoặc hủy: chưa tính điểm. |
| **Ràng buộc phi chức năng** | [NFR-JM-01](#nfr-jm-01), [NFR-JM-02](#nfr-jm-02). |

##### Xem hướng cải thiện CV và năng lực

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-jm-03"></a>UC-JM-03 |
| **Tên Use Case** | Xem hướng cải thiện CV và năng lực |
| **Tóm tắt** | Đề xuất cải thiện CV hoặc bổ sung năng lực. |
| **Tác nhân** | Sinh viên; phân hệ CV/Profile; dịch vụ AI. |
| **Điều kiện tiên quyết** | Đã có kết quả đánh giá CV–JD. |
| **Kết quả** | Gợi ý được hiển thị, lưu cùng lần phân tích; không tự sửa CV hoặc đổi điểm. |
| **Kịch bản chính** | 1. Sinh viên yêu cầu xem hướng cải thiện.<br>2. Hệ thống tìm yêu cầu chưa đáp ứng đầy đủ, tham chiếu hồ sơ cá nhân; sinh viên xác nhận năng lực.<br>3. Hệ thống ưu tiên yêu cầu bắt buộc, đề xuất cách bổ sung CV hoặc nội dung học, thực hành kèm nguồn đã kiểm chứng.<br>4. Hiển thị và lưu gợi ý. |
| **Kịch bản phụ** | • Thiếu thông tin năng lực: ghi “Chưa xác định”, không kết luận chưa biết.<br>• Không có khoảng trống: thông báo không có yêu cầu cần bổ sung.<br>• Lỗi gợi ý hoặc lấy nguồn: giữ kết quả matching, cho thử lại phần lỗi. |
| **Ràng buộc phi chức năng** | [NFR-JM-01](#nfr-jm-01), [NFR-JM-02](#nfr-jm-02), [NFR-JM-04](#nfr-jm-04). |

##### Xem lịch sử và chi tiết phân tích

| Thành phần | Đặc tả |
|---|---|
| **Use Case ID** | <a id="uc-jm-04"></a>UC-JM-04 |
| **Tên Use Case** | Xem lịch sử và chi tiết phân tích |
| **Tóm tắt** | Xem lại các lần phân tích đã lưu. |
| **Tác nhân** | Sinh viên. |
| **Điều kiện tiên quyết** | Sinh viên đã đăng nhập. |
| **Kết quả** | Hiển thị danh sách hoặc chi tiết phân tích. |
| **Kịch bản chính** | 1. Sinh viên mở lịch sử và chọn một lần phân tích.<br>2. Hệ thống hiển thị CV, JD, điểm, giải thích và gợi ý đã lưu. |
| **Kịch bản phụ** | • Chưa có lịch sử: thông báo danh sách trống.<br>• Không có quyền: từ chối hiển thị. |
| **Ràng buộc phi chức năng** | [NFR-JM-02](#nfr-jm-02); lưu trữ snapshot lịch sử phân tích độc lập với CV gốc. |

#### d. Job Tracking

##### Quản lý nguồn tuyển dụng theo dõi

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-01"></a>UC-JT-01 |
| **Tên Use Case** | Quản lý nguồn tuyển dụng theo dõi |
| **Tóm tắt** | Quản lý nguồn theo dõi và xem tình trạng truy cập. |
| **Tác nhân** | Sinh viên/người tìm việc; nền tảng mạng xã hội. |
| **Điều kiện tiên quyết** | Người dùng đã đăng nhập. |
| **Kết quả** | Nguồn và trạng thái theo dõi của đúng tài khoản được cập nhật. |
| **Kịch bản chính** | 1. Người dùng mở danh sách và chọn thêm nguồn.<br>2. Nhập đường dẫn Fanpage hoặc LinkedIn; hệ thống kiểm tra định dạng, phạm vi hỗ trợ và truy cập.<br>3. Hệ thống lưu quan hệ theo dõi, kết quả kiểm tra và hiển thị danh sách. |
| **Kịch bản phụ** | • Chọn tạm dừng hoặc tiếp tục: cập nhật trạng thái theo dõi.<br>• Chọn xóa: xác nhận rồi xóa quan hệ cá nhân.<br>• Đường dẫn rỗng, sai hoặc không hỗ trợ: báo lỗi, không lưu.<br>• Không truy cập được: cho giữ nguồn hoặc hủy, không kết luận nguồn đã đóng.<br>• Lưu lỗi: giữ dữ liệu nhập, không báo thành công. |
| **Ràng buộc phi chức năng** | [NFR-JT-01](#nfr-jt-01), [NFR-JT-02](#nfr-jt-02), [NFR-JT-03](#nfr-jt-03), [NFR-JT-07](#nfr-jt-07). |

##### Cập nhật tin tuyển dụng theo chu kỳ

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-02"></a>UC-JT-02 |
| **Tên Use Case** | Cập nhật tin tuyển dụng theo chu kỳ |
| **Tóm tắt** | Thu thập và lưu bài từ nguồn đang theo dõi. |
| **Tác nhân** | Nền tảng mạng xã hội; sinh viên/người tìm việc nhận tin. Bộ lập lịch nội bộ kích hoạt. |
| **Điều kiện tiên quyết** | Có nguồn bật theo dõi; đã cấu hình chu kỳ và phương thức truy cập. |
| **Kết quả** | Bài được lưu để sàng lọc, kèm thời điểm kiểm tra và căn cứ thời hạn. |
| **Kịch bản chính** | 1. Đến lịch, hệ thống lấy các nguồn đang có người bật theo dõi.<br>2. Kiểm tra truy cập và lấy bài trong khoảng thời gian đã cấu hình.<br>3. Lưu nội dung, nguồn, đường dẫn, các mốc thời gian và căn cứ thời hạn nếu có.<br>4. Chuyển bài sang sàng lọc, ghi kết quả kiểm tra. |
| **Kịch bản phụ** | • Không có nguồn: kết thúc lượt; không có bài mới: chỉ ghi nhận đã kiểm tra.<br>• Nguồn lỗi truy cập: cập nhật trạng thái, không báo thu thập thành công.<br>• Không rõ hạn: ghi “Chưa xác định”.<br>• Người dùng đã tạm dừng: không phân phối tin mới cho tài khoản đó. |
| **Ràng buộc phi chức năng** | [NFR-JT-03](#nfr-jt-03), [NFR-JT-04](#nfr-jt-04), [NFR-JT-05](#nfr-jt-05), [NFR-JT-07](#nfr-jt-07). |

##### Xem tin đã sàng lọc theo cá nhân hóa

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-03"></a>UC-JT-03 |
| **Tên Use Case** | Xem tin đã sàng lọc theo cá nhân hóa |
| **Tóm tắt** | Hiển thị tin IT Intern/Fresher phù hợp với người dùng. |
| **Tác nhân** | Sinh viên/người tìm việc; dịch vụ AI; phân hệ Profile/Account. |
| **Điều kiện tiên quyết** | Đã đăng nhập, có nguồn theo dõi; bài phải được sàng lọc trước khi hiển thị là phù hợp. |
| **Kết quả** | Danh sách phản ánh nguồn theo dõi và thông tin quan tâm của đúng tài khoản. |
| **Kịch bản chính** | 1. Hệ thống dùng AI phân loại, trích xuất bài mới và lưu kết quả có căn cứ.<br>2. Người dùng mở danh sách; hệ thống xác định nguồn và thông tin quan tâm.<br>3. Hiển thị tin phù hợp kèm nguồn, thời gian, thời hạn.<br>4. Người dùng mở chi tiết hoặc lưu tin. |
| **Kịch bản phụ** | • Tin không liên quan hoặc chỉ tuyển cấp độ khác: loại khỏi danh sách phù hợp.<br>• Bài nhiều vị trí: giữ phần IT Intern/Fresher có căn cứ, cho xem toàn bài ở chi tiết.<br>• Chưa rõ hoặc AI trả kết quả không hợp lệ: không coi là phù hợp, giữ dữ liệu gốc.<br>• Chưa có thông tin quan tâm: trả tin IT Intern/Fresher từ nguồn theo dõi.<br>• Chưa có nguồn hoặc tin phù hợp: hiển thị hướng dẫn tương ứng. |
| **Ràng buộc phi chức năng** | [NFR-JT-01](#nfr-jt-01), [NFR-JT-02](#nfr-jt-02), [NFR-JT-04](#nfr-jt-04), [NFR-JT-05](#nfr-jt-05), [NFR-JT-07](#nfr-jt-07). |

##### Lưu và xóa tin trong danh sách cá nhân

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-04"></a>UC-JT-04 |
| **Tên Use Case** | Lưu và xóa tin trong danh sách cá nhân |
| **Tóm tắt** | Lưu, bỏ lưu hoặc xóa tin cá nhân. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Đã đăng nhập và có quyền xem tin. |
| **Kết quả** | Danh sách cá nhân được cập nhật, không ảnh hưởng người khác. |
| **Kịch bản chính** | 1. Người dùng chọn lưu tin; hệ thống ghi nhận cho đúng tài khoản.<br>2. Người dùng mở danh sách đã lưu; hệ thống hiển thị tin và thời hạn hiện tại. |
| **Kịch bản phụ** | • Bỏ lưu: bỏ đánh dấu, không xóa tin đã nhận.<br>• Xóa: sau xác nhận, xóa khỏi danh sách và bỏ đánh dấu lưu của tài khoản; hủy thì giữ nguyên.<br>• Không có quyền hoặc lưu, xóa lỗi: thông báo, không thay đổi dữ liệu.<br>• Tin hết hạn: vẫn cho xem, lưu nhưng giữ nhãn “Hết hạn”. |
| **Ràng buộc phi chức năng** | [NFR-JT-01](#nfr-jt-01), [NFR-JT-02](#nfr-jt-02), [NFR-JT-03](#nfr-jt-03), [NFR-JT-04](#nfr-jt-04). |

##### Nhận và xem thông báo cơ hội mới

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-05"></a>UC-JT-05 |
| **Tên Use Case** | Nhận và xem thông báo cơ hội mới |
| **Tóm tắt** | Thông báo tin phù hợp và thời hạn liên quan. |
| **Tác nhân** | Sinh viên/người tìm việc. |
| **Điều kiện tiên quyết** | Có tin mới phù hợp, người nhận đang bật theo dõi; cần đăng nhập để xem thông báo. |
| **Kết quả** | Thông báo đúng tài khoản, đúng thời hạn tin và liên kết chi tiết. |
| **Kịch bản chính** | 1. Hệ thống nhận tin mới phù hợp, xác định người theo dõi và kiểm tra thời hạn.<br>2. Nếu chưa xác định hết hạn, tạo thông báo gồm tiêu đề, nguồn, thời gian và liên kết.<br>3. Người dùng mở thông báo; hệ thống cập nhật nhãn thời hạn.<br>4. Người dùng chọn xem chi tiết tin. |
| **Kịch bản phụ** | • Tin đã hết hạn hoặc người dùng dừng theo dõi: không tạo thông báo mới.<br>• Không rõ hạn: ghi “Chưa xác định”, không khẳng định còn tuyển.<br>• Tin hết hạn sau khi thông báo: giữ thông báo, đổi nhãn “Hết hạn”.<br>• Tin không khả dụng: báo không xem được, không chuyển sang tin khác. |
| **Ràng buộc phi chức năng** | [NFR-JT-01](#nfr-jt-01), [NFR-JT-02](#nfr-jt-02), [NFR-JT-04](#nfr-jt-04). |

##### Xem chi tiết và mở tin tuyển dụng gốc

| Thành phần | Đặc tả |
| --- | --- |
| **Use Case ID** | <a id="uc-jt-06"></a>UC-JT-06 |
| **Tên Use Case** | Xem chi tiết và mở tin tuyển dụng gốc |
| **Tóm tắt** | Xem tin đã lưu và đối chiếu bài gốc. |
| **Tác nhân** | Sinh viên/người tìm việc; nền tảng mạng xã hội. |
| **Điều kiện tiên quyết** | Đã đăng nhập và có quyền xem tin. |
| **Kết quả** | Chi tiết được hiển thị; mở bài gốc khi người dùng yêu cầu. |
| **Kịch bản chính** | 1. Người dùng chọn tin; hệ thống kiểm tra quyền truy cập.<br>2. Hiển thị nội dung nguồn, thông tin trích xuất, thời điểm cập nhật và thời hạn.<br>3. Người dùng chọn mở bài gốc; hệ thống điều hướng đến đúng đường dẫn ngoài. |
| **Kịch bản phụ** | • Tin không tồn tại hoặc không có quyền: thông báo, không tiết lộ dữ liệu khác.<br>• Thiếu trường: ghi “Chưa có thông tin”; thiếu đường dẫn: không cho mở bài gốc.<br>• Bài gốc bị xóa hoặc cần đăng nhập: vẫn cho xem bản đã lưu kèm thời điểm cập nhật.<br>• Tin hết hạn: vẫn cho xem nhưng giữ nhãn “Hết hạn”, không khẳng định còn tuyển. |
| **Ràng buộc phi chức năng** | [NFR-JT-02](#nfr-jt-02), [NFR-JT-04](#nfr-jt-04), [NFR-JT-07](#nfr-jt-07). |

---

<a id="prototype"></a>

## 5. BẢN MẪU (PROTOTYPE)

**Liên kết Figma thiết kế:** [HireUS Prototype](https://www.figma.com/design/bMbUlGzrU298Icu0HoERU3/HireUS?node-id=55-184&t=PSHtKrrGStMNBFOE-1).

*Lưu ý: Đây chỉ là các bản mẫu prototype nhằm demo khung của chức năng, giao diện có thể thay đổi trong tương lai.*

### 5.1. CV Builder & SeekerBot

| Mã frame | Tên màn hình | Mô tả chức năng |
| --- | --- | --- |
| F01 | CV Dashboard | Quản lý danh sách CV cá nhân, tạo mới và mở hướng dẫn sử dụng. |
| F02 | CV Editor + Live Preview | Chỉnh sửa nội dung CV, tự điền trường cơ bản từ Profile và xem trước trực tiếp. |
| F03 | CV Editor + AI Panel | Trợ lý SeekerBot hỗ trợ viết theo chuẩn STAR và đối chiếu từ khóa theo JD. |
| F04 | Tutorial CV Builder | Hướng dẫn 4 bước thao tác cơ bản (Next / Back / Skip / Help) cho người dùng mới. |
| F05 | Thành tựu & GitHub Import | Quản lý ngân hàng thành tựu cá nhân và trích xuất dữ liệu dự án từ GitHub. |
| F06 | CV Song ngữ & Print Preview | Chuyển đổi nội dung Việt – Anh, duyệt bản dịch và xem trước bố cục trang in chuẩn A4. |

#### F01 — CV Dashboard

![F01 — CV Dashboard](./images/F01_CV_Dashboard.png)

Màn hình tổng quan cho phép người dùng xem danh sách CV đã tạo, tạo CV mới hoặc kích hoạt hướng dẫn sử dụng (Tutorial).

#### F02 — CV Editor + Live Preview

![F02 — CV Editor + Live Preview](./images/F02_CV_Editor_Preview.png)

Giao diện soạn thảo kết hợp xem trước trực tiếp; tự động điền các trường thông tin cơ bản còn trống từ Profile người dùng và cho phép chọn mẫu hiển thị.

#### F03 — CV Editor + AI Panel

![F03 — CV Editor + AI Panel](./images/F03_SeekerBot_AI_Panel.png)

Bảng điều khiển trợ lý SeekerBot cung cấp gợi ý viết CV theo phương pháp STAR, kiểm tra chất lượng nội dung và căn chỉnh theo từ khóa JD.

#### F04 — Tutorial CV Builder

![F04 — Tutorial CV Builder](./images/F04_CV_Builder_Tutorial.png)

Quy trình hướng dẫn từng bước trực quan giúp người dùng làm quen nhanh với các công cụ tạo CV, hỗ trợ điều hướng Next, Back hoặc Skip.

#### F05 — Thành tựu & GitHub Import

![F05 — Thành tựu & GitHub Import](./images/F05_Achievement_GitHub.png)

Kho lưu trữ thành tựu cá nhân và tính năng nhập dự án tự động từ kho lưu trữ GitHub, cho phép duyệt bản nháp trước khi đưa vào CV.

#### F06 — CV Song ngữ & Print Preview

![F06 — CV Việt–Anh + Print Preview](./images/F06_Bilingual_Print_Preview.png)

Chế độ biên tập song ngữ hỗ trợ dịch nội dung, duyệt chỉnh sửa và xem trước trang in chuẩn trước khi xuất bản.

### 5.2. Voice Mock Interview

| Mã frame | Tên màn hình | Mô tả chức năng |
| --- | --- | --- |
| VMI-F01 | Thiết lập buổi phỏng vấn | Lựa chọn vị trí ứng tuyển, cấp độ kinh nghiệm, ngôn ngữ và CV ngữ cảnh. |
| VMI-F02 | Kiểm tra microphone và âm thanh | Kiểm tra quyền truy cập microphone, tín hiệu thu âm và âm lượng trước phiên. |
| VMI-F03 | Phòng phỏng vấn giọng nói | Giao diện hỏi đáp thời gian thực với AI, hiển thị câu hỏi, sóng âm và văn bản nhận diện. |
| VMI-F04 | Đang tạo báo cáo | Hiển thị tiến trình AI phân tích hội thoại và tổng hợp kết quả đánh giá. |
| VMI-F05 | Báo cáo đánh giá | Trình bày tổng điểm, phân tích chi tiết tiêu chí, điểm mạnh và nội dung cần ôn tập. |
| VMI-F06 | Lịch sử phỏng vấn | Danh sách các phiên phỏng vấn đã lưu, cho phép xem lại báo cáo hoặc tái sử dụng cấu hình. |

#### VMI-F01 — Thiết lập buổi phỏng vấn

![VMI-F01 — Thiết lập buổi phỏng vấn](./images/VMI-F01-Setup.png)

Người dùng lựa chọn vị trí ứng tuyển, cấp độ, ngôn ngữ và CV làm ngữ cảnh để AI thiết lập bộ câu hỏi phỏng vấn phù hợp.

#### VMI-F02 — Kiểm tra microphone và âm thanh

![VMI-F02 — Kiểm tra microphone và âm thanh](./images/VMI-F02-Mic-Check.png)

Hệ thống kiểm tra quyền thiết bị, đo tín hiệu thu âm theo thời gian thực và phát âm thanh mẫu để đảm bảo chất lượng trước khi vào phiên.

#### VMI-F03 — Phòng phỏng vấn giọng nói

![VMI-F03 — Phòng phỏng vấn](./images/VMI-F03-Interview.png)

Không gian phỏng vấn tương tác bằng giọng nói; hiển thị trạng thái AI đang nói, sóng âm giọng nói, văn bản nhận diện và các nút điều khiển phiên.

#### VMI-F04 — Đang tạo báo cáo

![VMI-F04 — Đang tạo báo cáo](./images/VMI-F04-Processing.png)

Màn hình hiển thị trạng thái xử lý sau khi kết thúc phỏng vấn trong lúc AI tiến hành phân tích toàn bộ bản ghi hội thoại.

#### VMI-F05 — Báo cáo đánh giá

![VMI-F05 — Báo cáo đánh giá](./images/VMI-F05-Report.png)

Báo cáo kết quả toàn diện với điểm số theo từng tiêu chí, nhận xét điểm mạnh, điểm yếu và các đề xuất ôn tập cải thiện cụ thể.

#### VMI-F06 — Lịch sử phỏng vấn

![VMI-F06 — Lịch sử phỏng vấn](./images/VMI-F06-History.png)

Quản lý danh sách các phiên phỏng vấn đã thực hiện, hỗ trợ mở lại báo cáo đánh giá cũ hoặc nhanh chóng tái sử dụng cấu hình cho phiên mới.

### 5.3. Job Matching & Skill Gap

| Mã frame | Tên màn hình | Mô tả chức năng |
| --- | --- | --- |
| JM-F01 | Chọn CV và nhập JD | Chọn CV đã có, dán nội dung JD tuyển dụng và xem tóm tắt thông tin đầu vào. |
| JM-F02 | Kiểm tra thông tin bóc tách | Xác nhận hướng chuyên môn, danh mục yêu cầu JD và bằng chứng trong CV. |
| JM-F03 | Kết quả đối chiếu (Matching) | Hiển thị điểm số phù hợp, mức cảnh báo màu và bảng phân tích bằng chứng chi tiết. |
| JM-F04 | Hướng cải thiện | Gợi ý bổ sung điểm còn thiếu trong CV và đề xuất tài liệu học tập, thực hành. |
| JM-F05 | Lịch sử phân tích | Danh sách các phiên đánh giá đã lưu, hỗ trợ xem lại chi tiết kết quả. |

#### JM-F01 — Chọn CV và nhập JD

![JM-F01 — Chọn CV và nhập JD](./images/JM-F01-Input.png)

Người dùng lựa chọn CV hiện có trong hệ thống, cung cấp nội dung JD cần đối chiếu và xem tóm tắt hồ sơ trước khi kích hoạt phân tích.

#### JM-F02 — Kiểm tra thông tin bóc tách

![JM-F02 — Kiểm tra thông tin bóc tách](./images/JM-F02-Confirm.png)

Cho phép người dùng kiểm tra và điều chỉnh hướng chuyên môn, danh sách yêu cầu bóc tách từ JD và các bằng chứng đối ứng từ CV gốc.

#### JM-F03 — Kết quả đối chiếu (Matching)

![JM-F03 — Kết quả matching](./images/JM-F03-Result.png)

Hiển thị điểm số phù hợp tổng thể kèm nhãn màu (Đỏ / Vàng / Xanh), giải thích căn cứ tính điểm và bảng đối chiếu từng tiêu chí.

#### JM-F04 — Hướng cải thiện

![JM-F04 — Hướng cải thiện](./images/JM-F04-Improve.png)

Phân loại hướng cải thiện thành hai nhóm rõ ràng: bổ sung thông tin đã có vào CV hoặc đề xuất tài liệu học tập, dự án thực hành cho kỹ năng còn thiếu.

#### JM-F05 — Lịch sử phân tích

![JM-F05 — Lịch sử phân tích](./images/JM-F05-History.png)

Lưu trữ snapshot các lần phân tích độc lập; cho phép người dùng mở lại và xem chi tiết kết quả các lần phân tích cũ.

**Luồng thao tác chính:** Chọn CV/JD → Kiểm tra thông tin bóc tách → Xem kết quả đối chiếu → Xem hướng cải thiện; mở Lịch sử để đối chiếu tiến bộ giữa các lần cập nhật CV.

### 5.4. Job Tracking

| Mã frame | Tên màn hình | Mô tả chức năng |
| --- | --- | --- |
| JT-F01 | Nguồn tuyển dụng theo dõi | Quản lý danh sách nguồn tin, kiểm tra trạng thái truy cập, tạm dừng hoặc xóa nguồn. |
| JT-F02 | Thêm nguồn tuyển dụng | Nhập URL Fanpage / LinkedIn, kiểm tra tính hợp lệ và thêm vào danh sách theo dõi. |
| JT-F03 | Danh sách tin tuyển dụng | Hiển thị các cơ hội việc làm IT Intern/Fresher đã sàng lọc và cá nhân hóa theo hồ sơ. |
| JT-F04 | Danh sách tin đã lưu | Quản lý tin tuyển dụng đã đánh dấu, hỗ trợ bỏ lưu hoặc xóa khỏi tài khoản. |
| JT-F05 | Thông báo cơ hội mới | Nhận thông báo cơ hội việc làm mới phù hợp và theo dõi trạng thái hạn nộp hồ sơ. |
| JT-F06 | Chi tiết tin và bài gốc | Hiển thị nội dung trích xuất, thông tin doanh nghiệp, thời hạn và liên kết mở bài gốc. |

#### JT-F01 — Nguồn tuyển dụng theo dõi

![JT-F01 — Nguồn theo dõi](./images/JT-F01-Sources.png)

Quản lý danh sách nguồn của cá nhân; phân biệt rõ trạng thái quan hệ người dùng (Đang theo dõi / Tạm dừng) và trạng thái kỹ thuật (Truy cập được / Không thể truy cập).

#### JT-F02 — Thêm nguồn tuyển dụng

![JT-F02 — Thêm nguồn](./images/JT-F02-Add-Source.png)

Người dùng nhập đường dẫn Fanpage hoặc LinkedIn; hệ thống kiểm tra tính khả dụng, hiển thị tên và nền tảng để người dùng xác nhận thêm nguồn.

#### JT-F03 — Danh sách tin tuyển dụng

![JT-F03 — Danh sách tin tuyển dụng](./images/JT-F03-Feed.png)

Hiển thị danh sách tin tuyển dụng Intern/Fresher được AI sàng lọc từ các nguồn đang theo dõi, căn cứ theo từ khóa quan tâm cá nhân hóa và nhãn thời hạn rõ ràng.

#### JT-F04 — Danh sách tin đã lưu

![JT-F04 — Tin đã lưu](./images/JT-F04-Saved.png)

Nơi người dùng quản lý các cơ hội đã đánh dấu quan tâm; hỗ trợ thao tác bỏ lưu hoặc xóa hẳn khỏi danh sách cá nhân với hộp thoại xác nhận an toàn.

#### JT-F05 — Thông báo cơ hội mới

![JT-F05 — Thông báo tuyển dụng](./images/JT-F05-Notifications.png)

Kênh cập nhật thông báo khi phát hiện tin tuyển dụng mới phù hợp; thể hiện trạng thái thời hạn tại thời điểm xem (Còn hạn, Hết hạn, hoặc Chưa xác định hạn).

#### JT-F06 — Chi tiết tin và bài gốc

![JT-F06 — Chi tiết và bài gốc](./images/JT-F06-Detail.png)

Trình bày đầy đủ nội dung bài đăng nguồn song song với các trường thông tin được AI tóm tắt; cung cấp nút mở trực tiếp bài viết gốc trên mạng xã hội.