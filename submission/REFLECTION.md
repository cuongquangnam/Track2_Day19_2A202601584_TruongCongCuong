# Reflection — Lab 19

**Tên:** _Truong Cong Cuong_
**Cohort:** _<A20-K3B>_
**Path đã chạy:** _lite_

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên golden set (~50 query), **hybrid (RRF)** thắng rõ nhất ở nhóm **mixed** (hybrid đạt ~100% precision@10; semantic ~98.5%, keyword ~97%). Ở **exact**, **keyword (BM25)** và **hybrid** gần như ngang và đều cao (~96.7%), trong khi **semantic** thấp hơn (~88.7%). Ở **paraphrase**, **keyword (BM25)** nhỉnh hơn hybrid nhẹ (~33.3% vs ~32.0%), còn semantic thấp hơn (~24.0%).

Lý do dùng hybrid: embedding bắt được các biến thể/cách diễn đạt gần nhau, còn BM25 giữ lợi thế với từ khóa đặc trưng; RRF cân bằng 2 nguồn để giảm tình trạng “lệch cụm”. Khi **không** dùng hybrid: nếu query rất “đúng ngữ”/từ khóa rõ ràng (BM25 đã gần trần) hoặc budget/latency rất chặt và bạn muốn giảm chi phí tính embedding/vector.

---

## Điều ngạc nhiên nhất khi làm lab này

_(Optional, 1–2 câu)_

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
