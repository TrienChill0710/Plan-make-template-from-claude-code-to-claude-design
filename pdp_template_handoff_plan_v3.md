# PLAN v3: PDP Template Mẹ & Bé trong 1 ngày (6 tiếng)

> Bản rút gọn của [plan v2](pdp_template_handoff_plan_v2.md) để làm xong trong 1 ngày. v2 giữ nguyên làm tài liệu chi tiết và lộ trình cho bản v1 đầy đủ sau này.
> **Nguyên tắc của v3:** AI làm research chính (không cắt research benchmark), PD chỉ chốt, kiểm chứng và sinh ảnh.

## 1. Mục tiêu

* **Đầu ra:** trang PDP Mẹ & Bé trên Claude Design (mobile bắt buộc, desktop nếu kịp) + **Input Pack** (file + ảnh + prompt) để dựng lại được.
* **Mức chất lượng:** bản **v0**, đủ đẹp và có cơ sở CRO từ research thật, chưa phải template đầy đủ như v2.
* **Cổng duyệt:** gộp còn **3 điểm dừng** (sau research, sau copy + brand, sau ảnh). PD nhắn "continue" mới đi tiếp.

## 2. Cần PD chốt trước khi bắt đầu (5 phút)

| Quyết định | Mặc định đề xuất |
|---|---|
| Thị trường & ngôn ngữ | US, tiếng Anh |
| Sản phẩm mẫu | Túi ngủ cho bé (sleep sack) |
| Tool sinh ảnh | PD cho biết tool đang dùng |
| PD tự chụp màn hình PDP, hay AI thử chụp bằng trình duyệt tự động | AI thử trước, không được thì PD chụp 3 trang |

## 3. Lịch 6 tiếng

| Giờ | Bước | AI làm | PD làm | Output |
|---|---|---|---|---|
| 0:00–0:15 | **0. Brief** | Soạn brief theo mặc định | Chốt 4 quyết định, duyệt brief | `01_brief.md` |
| 0:15–2:00 | **1. Research** (AI làm chính) | Xem mục 4 | Kiểm chứng ngẫu nhiên khoảng 20% nguồn, chụp màn hình nếu AI không chụp được | Xem mục 4 |
| | ⏸ **Điểm dừng 1** | | Duyệt research, layout, hướng thị giác | |
| 2:00–2:40 | **2. Copy + Brand** | Viết copy toàn trang, 3 tên brand, logo dạng chữ (SVG), tokens màu/font | Chọn tên brand, duyệt | `copy_doc.md`, `logo.svg`, `tokens.md` |
| | ⏸ **Điểm dừng 2** | | | |
| 2:40–3:50 | **3. Ảnh** | Viết prompt 5 ảnh, kiểm ảnh 1 vòng, sửa prompt ảnh lỗi | Sinh ảnh bằng tool ngoài | 5 ảnh + `image_prompts.md` |
| | ⏸ **Điểm dừng 3** | | | |
| 3:50–5:20 | **4. Claude Design** | Đóng pack, viết prompt P1 (tokens + component), P2 (mobile), P3 (desktop) | Chạy prompt trên Claude Design, báo lỗi để AI sửa prompt | Trang PDP mobile (+ desktop nếu kịp) |
| 5:20–6:00 | **5–6. Review + bàn giao** | Chấm rubric 1 vòng, liệt kê lỗi P0/P1, 3 giả thuyết A/B | Sửa lỗi P0 | PDP v0 + pack bản cuối |

## 4. Bước 1: Research do AI làm (giữ đủ 3 tầng benchmark)

**4a. Benchmark PDP theo 3 tầng.** AI tự truy cập từng store và thu thập:
* **Xác nhận Shopify** (mã nguồn, `/products.json`), app đang dùng (review, bundle, sticky ATC) qua script trong trang.
* **Dữ liệu sản phẩm** từ `/products.json`: giá, khoảng giá theo size, số variant, các bundle/gói đang bán.
* **Cấu trúc PDP** từ HTML: thứ tự section, nội dung màn đầu, vị trí giá/rating/CTA/trust, size guide, FAQ, cách trình bày an toàn.
* **Copy:** headline, 3 lợi ích, cách viết về an toàn và chứng nhận.

| Tầng | Mục đích | Store (đã kiểm tra sơ bộ, xem 4d) |
|---|---|---|
| **1. Cùng loại sản phẩm** | Khách mua túi ngủ cần thấy gì để dám mua | Kyte Baby, Halo, Nested Bean, Nanit (Breathing Wear Sleeping Bag) |
| **2. Cùng ngành, khác loại** | Cách xử lý trust, an toàn, tone | Coterie, Frida, Lovevery |
| **3. Ngoài ngành** | Pattern buy box và bundle | Brooklinen, Allbirds hoặc Ridge |

**4b. Insight khách hàng:** 15–20 trích dẫn nguyên văn kèm link từ review 2–4 sao, mục Hỏi & Đáp và Reddit (r/NewParents, r/beyondthebump), gom thành 3–5 nỗi lo chính.

**4c. Layout & thị giác:** đọc nghiên cứu PDP công khai (Baymard, NN/g), chỉ ghi kết luận có link nguồn. Phân loại theo thang A–D như v2.

**Output Bước 1 (1 file `research.md`):**
1. Bảng benchmark 3 tầng (store, URL PDP, giá, bundle, thứ tự section, trust, app).
2. Bảng nỗi lo → câu giải tỏa → vị trí trên trang.
3. Danh sách pattern nên dùng, kèm nguồn.
4. 1 layout đề xuất kèm lý do + wireframe mobile.
5. 1 hướng thị giác (palette, font, phong cách ảnh).

**Giới hạn cần biết:**
* AI đọc được mã nguồn và dữ liệu sản phẩm, nhưng **chưa chắc chụp được màn hình** để thấy giao diện thật. Nếu không chụp được, PD chụp mobile 3 PDP Tầng 1 (khoảng 15 phút, làm song song lúc AI research).
* Không có dữ liệu CR của từng store. Store được chọn vì cùng ngành và chạy Shopify, không phải vì đã chứng minh chuyển đổi cao.
* Bỏ bước chấm điểm 5 store bằng traffic/quảng cáo của v2 (cần tài khoản trả phí). Để dành cho v1.

**4d. Kết quả kiểm tra sơ bộ (đã chạy trước khi viết plan này):**
* Cả 8 store đều chạy Shopify. Lovevery và Coterie là Shopify headless (giao diện tự xây).
* Halo dùng tên miền `halosleep.com`, không phải `hellohalo.com`.
* **Frida không bán túi ngủ** nên chuyển sang Tầng 2. **Nanit có Breathing Wear Sleeping Bag** ($34.99) nên đưa vào Tầng 1.
* Giá túi ngủ tham khảo:

| Store | Sản phẩm | Giá | Ghi chú cho bundle |
|---|---|---|---|
| Kyte Baby | Sleep Bag 1.0 / 2.5 TOG | $55–70 | Giá đổi theo độ ấm TOG và size |
| Halo | Easy Transition SleepSack TOG 1.5 | $39.99 | Có nhiều bundle (cotton, bamboo, swaddle) |
| Nested Bean | Zen Sack Classic | $49.99–52.99 | Có "Growth Pack" 2 chiếc khác size ($60–62) và set cho sơ sinh |
| Nanit | Breathing Wear Sleeping Bag | $34.99 | Bán kèm hệ thống camera theo dõi |

* Bundle phổ biến của ngành là **gói nhiều chiếc theo size tăng dần** (bé lớn nhanh). Đây là ý tưởng bundle cho template, cần xác nhận thêm ở 4a.

## 5. Những gì cắt so với v2 (để dành cho v1)

* Chấm điểm store bằng traffic/quảng cáo, visual audit đo mã màu thật.
* So sánh 2–3 phương án layout và 2 hướng thị giác (v3 chỉ đề xuất 1).
* Wireframe desktop, đầy đủ trạng thái UI (chỉ giữ chọn variant và đã thêm giỏ), 5-second test.
* Ảnh UGC, các vòng review thứ 2–3.

## 6. Giữ nguyên từ v2 (không cắt)

* Mọi kết luận research phải có link nguồn. Không bịa số liệu, review AI viết phải gắn nhãn sample.
* Không dùng claim y tế ("ngăn ngừa SIDS", "chữa đầy hơi"). Ảnh bé ngủ đúng tư thế an toàn.
* Component đặc thù ngành: size guide theo tháng tuổi/cân nặng, khối giá, bundle, trust row, sticky CTA.
* Ảnh có chữ (infographic, bảng size) dựng trên Claude Design, không sinh bằng tool ảnh.
* Kết quả lệch thì sửa prompt, để pack dùng lại được.

## 7. Rủi ro

* **Ảnh** là phần dễ vượt giờ nhất. Dự phòng: giữ 3 ảnh tốt nhất.
* **Research** có thể vượt 1 tiếng 45 nếu nhiều trang chặn truy cập. Dự phòng: ưu tiên Tầng 1, cắt Tầng 3.
* **Desktop** có thể không kịp. Bàn giao mobile trước.
