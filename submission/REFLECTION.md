# Reflection — Lab 19

**Tên:** _Hoàng Quốc Hùng_
**Cohort:** _A20-K1_
**Path đã chạy:** _lite_

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên golden set 50 queries, `exact` thắng rõ với pure BM25 vì truy vấn mang tính từ khoa/keyword cao, cần match chính xác, và BM25 tận dụng tần suất từ tốt hơn. `paraphrase` thắng với pure vector vì câu hỏi được diễn đạt lại, ít trùng từ, cần hiểu ngữ nghĩa. `mixed` thường thắng với hybrid vì vừa có keyword vừa có biến thể diễn đạt, hybrid bù trừ điểm yếu của từng mode.

Tôi **không** dùng hybrid khi độ trễ/chi phí bị ràng buộc mạnh (chỉ cần một pipeline nhanh) hoặc khi dữ liệu có tính từ khoa tuyệt đối như tên hàm, mã lỗi, ID, tiêu đề ngắn - lúc đó pure BM25 đủ và ổn định hơn. Ngược lại, khi corpus là nội dung dài, đa nghĩa, hoặc câu hỏi giàu ngữ cảnh mà ít keyword, pure vector là lựa chọn đúng.

---

## Điều ngạc nhiên nhất khi làm lab này

Ngạc nhiên nhất là hybrid không luôn luôn thắng ở mọi loại query; với `exact` đôi khi hybrid lại tụt vì vector kéo lệch khỏi match từ khoa quan trọng.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
