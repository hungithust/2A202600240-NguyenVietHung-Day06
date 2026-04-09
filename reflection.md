# Individual reflection — Nguyễn Viết Hùng (AI20K240)

## 1. Role
Fullstack ts + voice agent. Phụ trách làm một phiên bản đối chọi với main để so sánh độ dễ hiểu code, khả năng mở rộng, bảo trì, sự chặt chẽ trong dự án cũng như so sánh tốc độ build của ai studio so với antigravity.

## 2. Đóng góp cụ thể
- Xây dựng hệ thống Backend tích hợp Gemini API (REST cho Text Chat và Live API cho Voice Chat).
- Phát triển giao diện Frontend (Dashboard, VehicleStatus, VehicleControls, AssistantChat) với React và Tailwind CSS.
- Quản lý trạng thái xe (Vehicle State) đồng bộ giữa Frontend và Backend thông qua Context API và API endpoints.
- Tích hợp tính năng cá nhân hóa (User Preferences) để AI tự động nhận biết sở thích người dùng (nhiệt độ, ứng dụng yêu thích).
- So sánh hiệu năng, độ trễ và kiến trúc giữa giải pháp dùng LangGraph/OpenAI và giải pháp dùng hệ sinh thái thuần Gemini (Gemini Live + Gemini REST).

## 3. SPEC mạnh/yếu
- **Mạnh nhất:** Xác định rõ ràng các Failure Modes (ảo giác, mất kết nối, xung đột lệnh) và có biện pháp giảm thiểu (Mitigation) cụ thể như "Locked Actions", Hybrid AI, Voice Biometrics. Phần User Stories bao phủ tốt các trường hợp thực tế (Happy, Low-confidence, Failure, Correction).
- **Yếu nhất:** Phần ROI & Kill Criteria còn khá chung chung ở mức độ định tính, chưa có các con số định lượng chi tiết về chi phí triển khai thực tế cho từng xe hoặc chi phí duy trì hạ tầng Cloud/Local.

## 4. Đóng góp khác
- Đánh giá được rất nhiều thông số, so sánh 2 công cụ (AI Studio vs Antigravity), so sánh 2 giải pháp trong code (LangGraph vs Gemini Native), 2 loại cấu trúc dự án, 2 loại giải pháp agent.
- Tối ưu hóa trải nghiệm người dùng với các hiệu ứng animation mượt mà (Framer Motion) và thiết kế UI/UX mang phong cách hiện đại (VinFast theme).

## 5. Điều học được
- Hiểu sâu hơn về cách hoạt động của WebSocket và Realtime API (Gemini Live) trong việc xử lý luồng âm thanh hai chiều và gọi hàm (Function Calling) với độ trễ thấp.
- Nhận ra rằng việc đồng bộ trạng thái (State Synchronization) giữa giao diện người dùng và hệ thống AI là cực kỳ quan trọng để tạo ra trải nghiệm liền mạch.
- Việc lựa chọn kiến trúc (ví dụ: bỏ LangGraph để dùng thuần Gemini) có thể giúp giảm độ phức tạp của code, dễ bảo trì hơn và tối ưu tốc độ phản hồi cho các tác vụ thời gian thực như trợ lý giọng nói trên xe hơi.

## 6. Nếu làm lại
- Sẽ thiết kế kiến trúc Hybrid AI ngay từ đầu (kết hợp Local LLM cho các lệnh cơ bản và Cloud LLM cho các tác vụ phức tạp) để giải quyết triệt để vấn đề mất kết nối mạng (Offline mode) như đã nêu trong SPEC.
- Bổ sung thêm các bài test tự động (Automated Tests) cho các luồng Function Calling để đảm bảo AI luôn gọi đúng tool với đúng tham số trong mọi tình huống.

## 7. AI giúp gì / AI sai gì
- **Giúp:** AI Studio hỗ trợ tạo khung dự án, viết các component React và thiết lập server Express rất nhanh chóng. Gemini giúp hoàn thiện logic Function Calling và xử lý âm thanh cho Live API một cách chính xác.
- **Sai/mislead:** Ban đầu AI (khi dùng LangGraph) có xu hướng làm phức tạp hóa luồng xử lý (Text -> Agent -> Tool -> Agent -> Text -> Voice), gây ra độ trễ lớn và code cồng kềnh. Sau đó phải refactor lại dùng thuần Gemini Live để tối ưu. Bài học: Không phải lúc nào dùng các framework Agent phức tạp cũng tốt, đôi khi giải pháp Native lại hiệu quả và gọn gàng hơn cho bài toán Realtime.
