# Individual reflection — Nguyễn Viết Hùng (AI20K240)

## 1. Role
Fullstack ts + voice agent. Phụ trách làm một phiên bản đối chọi với main để so sánh độ dễ hiểu code, khả năng mở rộng, bảo trì, sự chặt chẽ trong dự án cũng như so sánh tốc độ build của ai studio so với antigravity

## 2. Đóng góp cụ thể
- So sánh được tất cả mọi thông số, tiêu chí giữa ai studio và antigravity, trong trường hợp 2 dự án có cùng chức năng, cùng requirements.md (không cùng prompt)

## 3. SPEC mạnh/yếu
- Mạnh nhất: 
- Yếu nhất: ROI — 3 kịch bản thực ra chỉ khác số user, assumption gần giống nhau.
  Nên tách assumption rõ hơn (VD: conservative = chỉ dùng ở 1 chi nhánh,
  optimistic = rollout toàn hệ thống)

## 4. Đóng góp khác
- Đánh giá được rất nhiều thông số, so sánh 2 công cụ, so sánh 2 giải pháp trong code, 2 loại cấu trúc dự án, 2 loại giải pháp agent.

## 5. Điều học được
Trước hackathon nghĩ precision và recall chỉ là metric kỹ thuật.
Sau khi thiết kế AI triage mới hiểu: chọn recall cao hơn cho khoa cấp cứu
(bỏ sót nguy hiểm hơn false alarm) nhưng precision cao hơn cho khoa chuyên sâu
(gợi ý sai gây lãng phí thời gian bệnh nhân). Metric là product decision,
không chỉ engineering decision.

## 6. Nếu làm lại
Sẽ test prompt sớm hơn — ngày đầu chỉ viết SPEC, đến trưa D6 mới bắt đầu test prompt.
Nếu test sớm từ tối D5 thì có thể iterate thêm 2-3 vòng, prompt sẽ tốt hơn nhiều.

## 7. AI giúp gì / AI sai gì
- **Giúp:** dùng Claude để brainstorm failure modes — nó gợi ý được "drug interaction"
  mà nhóm không nghĩ ra. Dùng Gemini để test prompt nhanh qua AI Studio.
- **Sai/mislead:** Claude gợi ý thêm feature "đặt lịch khám" vào chatbot —
  nghe hay nhưng scope quá lớn cho hackathon. Suýt bị scope creep nếu không dừng lại.
  Bài học: AI brainstorm tốt nhưng không biết giới hạn scope.