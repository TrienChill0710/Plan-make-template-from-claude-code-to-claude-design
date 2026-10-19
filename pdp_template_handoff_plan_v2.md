# PLAN v2: Quy Trình PD Thiết Kế 1 Trang Product Detail (PDP) — UI Đẹp & CRO-Ready

## 1. Mục Tiêu

* **Vai trò:** Product Designer (PD).
* **Đầu ra cuối gồm 2 phần:**
  1. **Claude Design Input Pack:** bộ file + ảnh + prompt hoàn chỉnh để đưa lên Claude Design và dựng ra trang PDP (cấu trúc ở Bước 4b).
  2. **Trang PDP hoàn chỉnh trên Claude Design** (Mobile + Desktop) dựng từ pack đó, cùng gói bàn giao (Bước 6).
* **"Template" nghĩa là gì:** pack gồm 2 phần.
  * **Phần lõi (tái dùng nguyên cho mọi ngành):** quy trình 7 bước, rubric, cấu trúc thư mục pack, khung prompt P1–P5, danh sách component và quy tắc UI.
  * **Module theo ngành (làm lại khi đổi ngành):** brief, research Bước 1, copy, brand & tokens, ảnh. **Mẹ & Bé là module đầu tiên.** Đổi sang ngành khác thì phải chạy lại Bước 0–3, không chỉ đổi file.
* **Đầu ra phải đạt 2 tiêu chí:**
  1. **UI đẹp, hiện đại, Mobile-First:** nền sáng, ít box, trang cô đọng, Header/Logo/Icon chỉn chu, bộ ảnh đồng bộ.
  2. **CRO-ready:** đánh trúng nỗi đau người mua thật, đặt lợi ích + bundle + bằng chứng tin cậy sát nút mua.
* **Lưu ý về "CRO cao":** thiết kế không tự chứng minh được tỉ lệ chuyển đổi. Kết quả cuối là một trang **CRO-ready** kèm danh sách giả thuyết để A/B test (xem Bước 6).
* **Tiêu chí hoàn thành (Definition of Done):**
  * Rubric ở Bước 5 đạt ≥ 4/5 ở mọi tiêu chí và không còn lỗi P0/P1.
  * Qua 5-second test với 3–5 người (nếu thực hiện được).
  * Gói handoff Bước 6 đầy đủ.

### Cần PD chốt trước khi chạy Bước 0

| Quyết định | Lựa chọn | Ảnh hưởng tới |
|---|---|---|
| Thị trường & ngôn ngữ | US/quốc tế (tiếng Anh) hay Việt Nam | Benchmark, nguồn insight, đơn vị tiền tệ, copy |
| Sản phẩm mẫu | Đề xuất: túi ngủ cho bé. Khác: bình sữa, địu | Toàn bộ Bước 1–3 |
| Tool sinh ảnh | Midjourney, Imagen, Flux, GPT image... | Cú pháp prompt ảnh Bước 3 |
| Tool research PD có tài khoản | SimilarWeb, StoreLeads, BuiltWith, Wappalyzer (bản miễn phí hay trả phí) | Mức độ AI tự làm được ở 1a-0 |
| Công cụ chụp màn hình/đo màu | PD tự chụp, hay cài công cụ trình duyệt tự động cho AI | Ai làm bảng benchmark và visual audit |
| Chế độ chạy | Đầy đủ hay MVP (xem bảng timebox) | Khối lượng và thời gian |

### Timebox & đường tắt MVP

Mỗi bước có giới hạn thời gian. Hết timebox mà chưa xong thì AI báo cáo phần đã có và PD quyết định: chấp nhận, gia hạn, hay cắt phạm vi.

| Bước | Timebox đầy đủ | Đường tắt MVP |
|---|---|---|
| 0. Brief | 0,5 ngày | Giữ nguyên |
| 1. Research + chốt khung | 3 ngày | 1,5 ngày: 1a-0 chấm 5 store (giữ nguyên), benchmark 4 trang (bỏ Tầng 2), 1b chỉ 20 trích dẫn từ review Amazon + Q&A, 1c và 1c-bis chỉ lấy nguồn loại A/B, 1d chỉ 2 phương án layout |
| 2. Content + Brand & Tokens | 1,5 ngày | 1 ngày: 3 phương án headline thay vì 5, logo dạng wordmark chữ đơn giản |
| 3. Ảnh | 1,5 ngày (tùy tốc độ sinh ảnh) | 1 ngày: 5 ảnh (hero, mặt bên, chất liệu, lifestyle, bundle), bỏ ảnh UGC |
| 4. Pack + dựng trên Claude Design | 2 ngày | 1,5 ngày: chạy thử chỉ P2 |
| 5. Review | 1 ngày | 0,5 ngày: 2 vòng AI review |
| 6. Handoff | 0,5 ngày | Chỉ pack bản cuối + copy doc + danh sách giả thuyết A/B |
| **Tổng** | **khoảng 10 ngày** | **khoảng 6,5 ngày** |

*Các mốc thời gian là ước lượng ban đầu, điều chỉnh sau khi chạy thực tế Bước 0–1.*

### Quy tắc vận hành: duyệt từng bước (Approval Gate)

* AI chỉ chạy **một Bước (0 → 6) mỗi lượt**. Xong Bước nào thì **dừng lại**, không tự chạy sang Bước kế tiếp.
* Cuối mỗi Bước, AI báo cáo gồm:
  1. **Đã làm gì** và **file/đầu ra** tạo ra.
  2. **Các quyết định AI đã tự đưa ra** và giả định đang dùng.
  3. **Điểm cần PD kiểm chứng** (đặc biệt các nguồn, số liệu, link).
  4. **Câu hỏi cần PD chốt** để chạy Bước tiếp theo.
* PD đọc và duyệt (hoặc yêu cầu sửa). Chỉ khi PD nhắn **"continue"** (hoặc tương đương) AI mới chạy Bước tiếp theo.
* Nếu PD yêu cầu sửa, AI sửa trong cùng Bước rồi báo cáo lại, không đi tiếp.
* **Bước 3 có 2 điểm dừng:** (1) sau khi AI viết xong Image Prompt Pack, PD duyệt rồi tự sinh ảnh bằng tool ngoài; (2) sau khi PD đưa ảnh về và AI kiểm ảnh xong, PD duyệt bộ ảnh. Chỉ khi PD nhắn "continue" sau điểm dừng 2 mới sang Bước 4.
* Nếu một Bước phát hiện vấn đề làm thay đổi Bước trước (ví dụ wireframe ở Bước 1 không khớp brief ở Bước 0), AI nêu rõ và chờ PD quyết định, không tự quay lại sửa.
* Bước 1 là bước lớn (1a → 1e, gồm cả 1c-bis). Mặc định AI chạy hết rồi dừng một lần, và báo cáo gồm: bảng benchmark, bảng pain-point, research layout, Visual Direction Brief, wireframe và khung trang đề xuất. Nếu PD muốn duyệt giữa chừng thì nói rõ, ví dụ dừng sau 1b (insight khách hàng), sau 1c-bis (hướng thị giác) và sau 1d (wireframe layout).

---

## 2. Quy Trình 7 Bước (Bước 0 → Bước 6)

### Bước 0: Brief (chốt đầu vào trước khi làm bất cứ thứ gì)

Điền đủ bảng sau. Thiếu mục nào thì Bước 1 sẽ ra kết quả chung chung.

| Mục | Nội dung cần chốt |
|---|---|
| Ngành hàng & sản phẩm | Category thật (để đào Reddit được), sản phẩm hư cấu thuộc category đó |
| Tệp khách | Ai mua, mua để làm gì, mức hiểu biết về category |
| Thị trường & ngôn ngữ | Quốc gia, ngôn ngữ, đơn vị tiền tệ |
| Giá & AOV | Giá lẻ, giá bundle, AOV mục tiêu |
| Nguồn traffic | Ads cold (TikTok/FB), search, email... Quyết định mức độ cần trust |
| Mức nhận biết brand | Brand mới → cần mật độ bằng chứng cao hơn, không dùng phong cách tối giản kiểu Apple |
| Brand & tone | 3 tính từ mô tả brand, tone & voice ngắn (xưng hô, mức trang trọng) |

**Áp dụng cho template ngành Mẹ & Bé:**

* **Đặc thù ngành cần đưa vào brief:**
  * Người mua khác người dùng: bố mẹ mua cho bé. Ngoài ra còn người mua làm quà (ông bà, bạn bè, registry).
  * Nỗi sợ số 1 là **an toàn**: chất liệu, chứng nhận, nguy cơ cho bé. Tiếp theo là size/độ tuổi phù hợp, hiệu quả thật, dễ vệ sinh, dùng được bao lâu.
  * Ngữ cảnh mua: bố mẹ thiếu ngủ, lướt điện thoại bằng một tay, thường lúc nửa đêm. Mobile-first và vùng chạm ngón cái là bắt buộc.
  * Hàng đã mở thường không được đổi trả vì lý do vệ sinh. Chính sách đổi trả phải viết rõ ràng.
* **Chọn sản phẩm mẫu:** nên chọn sản phẩm có đủ các pattern PDP khó nhất: có variant (size theo tuổi/cân nặng, màu), có bundle hợp lý, có nỗi sợ an toàn rõ, giá trung bình (khoảng $40–120).
  * **Đề xuất: túi ngủ cho bé (sleep sack).** Có size theo tháng tuổi/cân nặng, độ ấm TOG, chứng nhận chất liệu, bundle 2–3 chiếc (bé lớn nhanh, cần thay giặt), và có nỗi sợ an toàn khi ngủ.
  * Phương án khác: bộ bình sữa chống sặc/đầy hơi, địu em bé.

### Bước 1: Research (Benchmark, Insight Khách Hàng, Layout) + Chốt Khung Trang

**Phân vai trong Bước 1**
* **AI:** thu thập, đọc, tổng hợp và đề xuất (benchmark, trích dẫn khách hàng, nghiên cứu layout, các phương án layout).
* **PD:** kiểm chứng và quyết định. Mở link kiểm tra ngẫu nhiên ≥ 20% nguồn AI đưa ra, kiểm tra 100% các con số "tăng X% CR". AI hay bịa số liệu và nguồn. Số nào không có link kiểm chứng được thì loại khỏi kết luận.
* **Ai làm việc gì (điền lại theo các quyết định PD đã chốt ở đầu plan):**

| Việc | AI tự làm | PD làm tay rồi đưa cho AI | Ghi chú |
|---|---|---|---|
| Tìm store ứng viên, kiểm tra có phải Shopify | Được (đọc trang, mã nguồn) | | Kiểm tra `cdn.shopify.com` |
| Số liệu traffic, StoreLeads, BuiltWith bản đầy đủ | | Có (cần tài khoản) | Thiếu tài khoản thì bỏ tín hiệu đó, không để AI đoán |
| Meta Ad Library, TikTok Creative Center | Một phần | Có (khi cần đăng nhập) | |
| Chụp màn hình PDP 390px và 1440px | Chỉ khi có công cụ trình duyệt tự động | Có | AI không được mô tả trang từ trí nhớ thay cho ảnh chụp |
| Lấy mã màu, tên font | Chỉ khi có công cụ trình duyệt | Có (DevTools, công cụ chọn màu) | |
| Đọc review, Q&A, Reddit, trích dẫn | Được (nếu trang cho đọc) | Bổ sung khi trang chặn | Mọi trích dẫn kèm link |
| Đọc nghiên cứu Baymard, NN/g, A/B case study | Được với nội dung công khai | Bổ sung nội dung trả phí nếu có | |
| Phân tích, tổng hợp, đề xuất | Được | | |
| Kiểm chứng nguồn, quyết định | | Có | |

* Bước 1 gồm 3 mảng research song song: **Content** (1a, 1b), **Layout** (1c) và **UI/Visual** (1c-bis: hierarchy, màu, font, phong cách thị giác). Cả ba cùng đổ vào 1d, 1e để chốt khung và hướng thị giác.

**1a-0. Sàng lọc store Shopify chuyển đổi tốt ngành Mẹ & Bé (chỉ lấy trang PDP)**

*Sự thật cần nắm trước:* Shopify công bố **dữ liệu tổng hợp** (CR trung bình theo ngành, ngưỡng top 10–20% store), **không công bố CR của từng store**, và các bên đo lường như Littledata cũng chỉ công bố số liệu gộp. Vì vậy không có "bảng xếp hạng store chuyển đổi cao" chính thức để tải về. Cách làm đúng là dùng nhiều **tín hiệu gián tiếp** để suy ra store nào có khả năng chuyển đổi tốt, và ghi rõ đó là suy luận.

*Bước 1: Lập danh sách ứng viên (5 store Mẹ & Bé chạy Shopify, ưu tiên store bán sản phẩm cùng loại với sản phẩm mẫu):*
* **Nhận diện store Shopify:** BuiltWith, Wappalyzer, StoreLeads, hoặc kiểm tra mã nguồn có `cdn.shopify.com`.
* **Nguồn tìm ứng viên:** danh mục store theo ngành của StoreLeads/BuiltWith, mục khách hàng Shopify Plus (shopify.com/plus/customers), bài case study của Shopify và agency CRO về brand Mẹ & Bé, danh sách DTC baby brand từ cộng đồng/báo ngành.

*Bước 2: Chấm điểm theo tín hiệu gián tiếp (mỗi tín hiệu 0–2 điểm, ghi nguồn và ngày):*

| Tín hiệu | Cách kiểm tra | Ý nghĩa và giới hạn |
|---|---|---|
| Tăng trưởng/traffic bền | SimilarWeb hoặc StoreLeads (ước tính lưu lượng, thứ hạng) | Chỉ là ước tính, sai số lớn |
| Quảng cáo chạy lâu | Meta Ad Library, TikTok Creative Center: mẫu quảng cáo của sản phẩm đó chạy nhiều tháng | Quảng cáo chạy lâu thường vì có lãi, nhưng không đo trực tiếp CR của trang |
| Lượng review lớn và đều | Số review, ngày review phân bố đều theo thời gian, có ảnh | Tín hiệu mạnh về doanh số thật. Cẩn thận review mua/bơm |
| Case study có số liệu | Shopify Plus, agency, bài của chính brand nói về CR hoặc uplift | Có thiên lệch tự quảng bá, ghi bối cảnh và nguồn |
| Sản phẩm bán chạy được ưu tiên | Trang chủ/menu đặt sản phẩm đó nổi bật, nhãn "Best seller" | Cho biết sản phẩm nào đáng lấy PDP |
| Tuổi store và độ ổn định | Store lâu năm mà vẫn giữ layout PDP ít đổi | Layout ổn định lâu thường đã qua tối ưu, nhưng cũng có thể do lười đổi |

*Bước 3: Chọn 3 store điểm cao nhất trong 5 store làm Tầng 1 (xem bảng bên dưới)* và ghi vào bảng chấm điểm kèm lý do loại 2 store còn lại. Nếu nhiều store không qua được bước nhận diện Shopify, thay bằng store khác cho đủ 5. Đây chỉ là xếp hạng **khả năng**, không được viết thành "store có CR cao nhất ngành".

*Quy tắc chỉ focus PDP:*
* Chỉ chụp và phân tích **PDP của sản phẩm bán chạy nhất** (hoặc sản phẩm tương đồng với sản phẩm mẫu ở Bước 0) của mỗi store. Không phân tích trang chủ, collection, giỏ hàng.
* Ghi đúng đường dẫn PDP và ngày chụp. Chụp ở 390px (mobile) và 1440px (desktop). Chụp cả **toàn trang cuộn**, màn đầu và từng section.
* Ghi thêm các chi tiết PDP: app/widget đang dùng (review app, bundle app, sticky ATC) nếu phát hiện được qua mã nguồn hoặc Wappalyzer. Điều này cho biết cơ chế chuyển đổi họ đang dùng.
* Ghi theme/layout Shopify nếu nhận diện được (ví dụ theme chuẩn hay tùy biến). Theme chuẩn dùng rộng rãi cho thấy pattern đã được thị trường chấp nhận.

**1a. Benchmark dựa trên trang thật, không dựa trí nhớ AI**
* Chọn 6–8 trang theo **3 tầng**. Tầng 1 lấy từ danh sách đã sàng lọc ở 1a-0. Các brand ghi trong bảng chỉ là **gợi ý ban đầu để tìm kiếm**, chưa được kiểm tra là Shopify hay chuyển đổi tốt. Mỗi tầng trả lời một câu hỏi khác nhau, đừng trộn lẫn:

| Tầng | Mục đích | Số trang | Gợi ý cho Mẹ & Bé (kiểm tra lại trang còn hoạt động trước khi dùng) |
|---|---|---|---|
| **1. Cùng ngành, cùng loại sản phẩm** (ưu tiên store Shopify điểm cao ở 1a-0) | Khách ngành này cần thấy gì để dám mua | 3–4 | Ứng viên để kiểm tra: Kyte Baby, Halo (túi ngủ), Nested Bean, Lovevery, Frida. Danh sách cuối do bảng chấm điểm 1a-0 quyết định, không do tên tuổi |
| **2. Cùng ngành, khác loại sản phẩm** | Cách các brand mẹ & bé xử lý trust, an toàn, tone | 2 | Nanit hoặc Owlet (an toàn, hàng giá cao), Coterie (subscription, hàng tiêu dùng lặp lại) |
| **3. Ngoài ngành, DTC tốt** | Mượn pattern thị giác & bố cục buy box | 1–2 | Brooklinen (bundle, chất liệu vải), Allbirds hoặc Ridge (buy box mobile) |

* Ưu tiên brand **DTC tầm trung** hơn brand khổng lồ. Brand lớn được tin sẵn nên trang của họ thường thiếu các yếu tố trust mà một brand mới bắt buộc phải có.
* **Đối chiếu với nghiên cứu có bằng chứng** (ví dụ Baymard Institute về PDP và mobile). Trang của brand thành công chưa chắc tối ưu, vì có thể họ bán tốt nhờ thương hiệu chứ không nhờ trang. Pattern nào vừa xuất hiện ở ≥ 3 trang benchmark vừa được nghiên cứu ủng hộ thì mới đưa vào khung.
* Ghi ngày chụp màn hình. Trang benchmark thay đổi liên tục.
* Mở từng trang ở viewport **390px**, chụp màn hình rồi mới phân tích.
* Điền cùng một bảng cho mỗi trang:

| Trang (URL PDP + ngày chụp) | Điểm 1a-0 | Thứ tự section | Nội dung màn đầu | Vị trí giá | Vị trí CTA | Vị trí trust/rating | Sticky CTA? | App/widget phát hiện được | Số màn cuộn |
|---|---|---|---|---|---|---|---|---|---|

* Thêm **bảng visual audit** cho cùng các trang (dùng cho mục 1c-bis):

| Trang (URL PDP) | Palette (nền/chữ/accent, mã màu) | Màu & kiểu nút CTA | Cặp font + cỡ body | Phong cách ảnh (studio/lifestyle/UGC/minh họa) | Kiểu icon | Bo góc, đổ bóng | Mật độ khoảng trắng | Cảm xúc tổng thể (3 tính từ) |
|---|---|---|---|---|---|---|---|---|

* Rút ra **pattern chung** (xuất hiện ở ≥ 3 trang) và **điểm khác biệt đáng mượn**.
* Mục chú ý theo nhóm:
  * **Buy Box:** gallery mobile, tiêu đề, lợi ích, chọn variant/bundle, cam kết đổi trả/giao hàng sát nút mua.
  * **Trình bày tính năng:** ảnh lớn + chữ ngắn thay vì nhiều box nhỏ.
  * **Bằng chứng xã hội & xử lý từ chối:** review có ảnh, rating, FAQ ngắn.
* Lưu ý: brand lạ không nên bắt chước nguyên văn trang của brand lớn. Brand lớn được tin sẵn nên có thể tối giản. Brand mới cần thêm trust.

**1b. Đào pain-point khách hàng (Reddit, review sàn, Q&A)**
* **Nguồn cho Mẹ & Bé**, xếp theo giá trị insight:
  1. **Review 2–4 sao trên Amazon/Target/Babylist** của sản phẩm đối thủ trực tiếp. Review 5 sao chỉ khen chung chung, review 1 sao thường là lỗi giao hàng. Review 2–4 sao mới chứa lý do thật khiến khách lưỡng lự.
  2. **Mục Hỏi & Đáp trên Amazon:** đây là các câu hỏi khách đặt *trước khi mua*, có thể dùng gần như nguyên văn cho FAQ.
  3. **Reddit:** r/NewParents, r/beyondthebump, r/BabyBumps, r/Mommit, r/daddit, r/ScienceBasedParenting. Tìm theo cụm như "worth it", "regret buying", "vs", "safe?".
  4. **Hướng dẫn chính thức** (ví dụ AAP về ngủ an toàn, CPSC về sản phẩm trẻ em) để biết claim nào được phép nói và nỗi lo nào khách đã được "dạy" phải hỏi.
* Thu thập **trích dẫn nguyên văn kèm link**. Không chấp nhận "insight" không có nguồn.
* Tối thiểu khoảng 30–50 trích dẫn rồi mới gom cụm. Ít hơn thì dễ chọn theo cảm tính.
* Gom thành **3–5 cụm nỗi sợ** khiến khách ngập ngừng không bấm mua.
* Ghi lại **cách khách diễn đạt** để dùng làm câu chữ cho headline và FAQ.
* Lập bảng map:

| Pain-point | Trích dẫn gốc | Câu giải tỏa | Đặt ở đâu (Buy Box / Review / FAQ) | Loại bằng chứng (số liệu, ảnh, chính sách) |
|---|---|---|---|---|

**1c. Research layout PDP: layout nào chuyển đổi tốt, và vì sao**

*Câu hỏi nghiên cứu:* (1) Layout/pattern nào có bằng chứng chuyển đổi tốt trên mobile? (2) Vì sao, cơ chế hành vi là gì? (3) Điều kiện áp dụng: mức giá, độ nhận biết brand, loại traffic, ngành.

*Lưu ý trung thực về dữ liệu CR:* tỉ lệ chuyển đổi của từng trang brand hầu như không công khai, và không thể suy ra từ việc nhìn trang. Trang trông đẹp và brand bán tốt không chứng minh layout đó hiệu quả. Vì vậy mỗi phát hiện phải gắn **loại nguồn**, xếp từ tin cậy cao xuống thấp:

| Loại | Nguồn | Độ tin cậy | Cách dùng |
|---|---|---|---|
| A | Nghiên cứu hành vi có phương pháp (Baymard về PDP và mobile checkout, NN/g) | Cao | Làm nền cho pattern chuẩn |
| B | Kết quả A/B test đã công bố (GoodUI, CXL, case study VWO/Convert/Optimizely, blog Shopify) | Vừa đến cao, tùy cỡ mẫu và bối cảnh | Dùng khi ghi rõ điều kiện test |
| C | Dữ liệu ngành (benchmark CR theo ngành/thiết bị) | Vừa | Chỉ để đặt kỳ vọng, không dùng để chọn layout |
| D | Pattern thấy ở trang benchmark (1a) | Thấp (chỉ cho biết họ làm gì, không chứng minh hiệu quả) | Làm giả thuyết, cần thêm bằng chứng |

*Mỗi phát hiện ghi theo mẫu:* Pattern | Nguồn + link | Loại (A–D) | Kết quả (nếu có số, kèm cỡ mẫu/bối cảnh) | Cơ chế hành vi (vì sao hiệu quả) | Điều kiện và giới hạn | Độ tin cậy (cao/vừa/thấp).
* Chỉ pattern có nguồn A/B hoặc ≥ 2 nguồn độc lập mới vào danh sách **"Pattern chuẩn"**. Còn lại xếp vào **"Giả thuyết"** (để dành cho A/B test ở Bước 6).

*Các câu hỏi layout cần có câu trả lời (mỗi câu một dòng kết luận kèm bằng chứng):*
1. Thứ tự section tối ưu cho mobile: Buy Box → bằng chứng → lợi ích, hay giải thích sản phẩm trước rồi mới tới bằng chứng?
2. Gallery: carousel hay xếp dọc? Bao nhiêu ảnh? Ảnh nào đứng đầu?
3. Rating/review: đặt ngay dưới tiêu đề, và khu review đầy đủ nên nằm ở đâu?
4. Mô tả lợi ích: ngắn trong Buy Box + chi tiết bên dưới, hay chỉ một nơi?
5. Bundle/variant: đặt trong Buy Box hay tách riêng? Mặc định chọn gì?
6. Sticky CTA: hiện từ lúc nào, nội dung gì?
7. Trust, đổi trả, giao hàng: đặt sát CTA hay ở cuối trang?
8. Specs/FAQ: accordion, tab hay trải dài? Ảnh hưởng đến tỉ lệ đọc và chuyển đổi ra sao?
9. Độ dài trang tối ưu theo mức giá và độ lo lắng của người mua.
10. Cách bố trí dành riêng cho ngành Mẹ & Bé (sản phẩm giá trung bình, nỗi sợ an toàn): có cần đưa nội dung an toàn/chứng nhận lên cao hơn mặc định không? *Đây là giả thuyết ban đầu, cần xác minh bằng nguồn A/B.*

**1c-bis. Research UI/Visual: hierarchy, màu, font, phong cách thị giác**

*Câu hỏi nghiên cứu:* Thị giác nào vừa tạo thứ bậc rõ để dẫn khách tới nút mua, vừa truyền được cảm giác an toàn và đáng tin cho ngành Mẹ & Bé?

*Nguồn và cách làm:*
* **Visual audit** trên chính ảnh chụp benchmark ở 1a, điền bảng visual audit. Lấy mã màu và tên font từ trang thật (công cụ chọn màu, DevTools), không để AI đoán bằng mắt.
* Dùng cùng thang nguồn **A–D** như 1c. Các claim kiểu "màu nút X tăng CR Y%" rất hay bị thổi phồng hoặc phụ thuộc bối cảnh. Chỉ coi là kết luận khi có nguồn A/B kèm điều kiện, còn lại ghi là giả thuyết.
* Mỗi phát hiện ghi theo mẫu giống 1c: Yếu tố | Nguồn + link | Loại (A–D) | Cơ chế vì sao hiệu quả | Điều kiện và giới hạn | Độ tin cậy.

*Các câu hỏi cần có câu trả lời (mỗi câu một dòng kết luận kèm bằng chứng):*
1. **Visual hierarchy:** ở màn đầu mobile, mắt khách đi theo thứ tự nào? Yếu tố nào đang được nhấn bằng kích thước, độ tương phản, vị trí, và nên nhấn gì (giá, tiêu đề, rating, CTA)?
2. **Màu:** palette nào của các brand Mẹ & Bé tốt truyền cảm giác an toàn, dịu nhẹ mà không sến (tránh mặc định pastel hồng/xanh) và không lạnh kiểu tech? Tỉ lệ màu nền, màu chữ, màu nhấn. Màu CTA cần nổi bật so với nền nhưng vẫn thuộc palette thương hiệu.
3. **Font:** loại chữ nào (serif/sans, độ tròn) truyền được sự đáng tin và ấm áp? Cỡ chữ, line-height và độ đậm nào đọc tốt trên mobile trong điều kiện mệt, thiếu sáng?
4. **Phong cách ảnh và minh họa:** studio sạch, lifestyle ấm, UGC, hay minh họa? Cách phối giữa các loại. Ảnh nền sáng có đủ ấm cho ngành này không?
5. **Icon, bo góc, đổ bóng, mật độ khoảng trắng:** mức nào tạo cảm giác "mềm, an toàn" nhưng vẫn chuyên nghiệp?
6. **Tương phản và khả năng đọc:** các brand benchmark có đạt WCAG AA không? Chỗ nào chữ nhạt khó đọc, rút ra bài học gì?
7. **Cảm xúc và niềm tin:** các yếu tố thị giác nào được nghiên cứu là tăng cảm nhận độ tin cậy (ví dụ nhất quán, chất lượng ảnh, khoảng trắng)? Có nguồn A/B hay nghiên cứu độ tin cậy web không?

*Đầu ra: Visual Direction Brief (1 trang)*
* 2 hướng thị giác khác nhau (ví dụ "Ấm & tự nhiên" và "Sạch & khoa học"). Mỗi hướng gồm: 3 tính từ cảm xúc, palette gợi ý (mã màu), cặp font, phong cách ảnh, kiểu icon/bo góc, lý do chọn dựa trên pain-point (1b) và bằng chứng (1c-bis), rủi ro.
* Chọn 1 hướng bằng ma trận chấm 1–5 (độ khớp pain-point và brand ở Bước 0, độ tin cậy cảm nhận, khả năng đọc, tính khả thi với bộ ảnh AI, độ khác biệt so với đối thủ). Hướng không chọn có thể thành giả thuyết A/B.
* Brief được duyệt cùng cổng duyệt của Bước 1 và là đầu vào trực tiếp cho brand & tokens ở Bước 2b, ảnh ở Bước 3 và rubric ở Bước 5.

**1d. Đề xuất layout (2–3 phương án) và chốt phương án chính**

* Dựa trên 1a–1c, AI đề xuất **2–3 phương án layout** khác nhau về triết lý. Ví dụ:

| Phương án | Triết lý | Phù hợp khi | Rủi ro |
|---|---|---|---|
| A. Buy-first | Buy Box đủ thông tin để mua ngay, phần dưới là chứng minh | Brand quen thuộc, giá thấp, traffic ấm | Người lo lắng thiếu thông tin an toàn sẽ rời đi |
| B. Proof/Education-first | Đưa bằng chứng và giải thích an toàn lên sớm, rồi mới tới bundle | Brand mới, giá trung bình-cao, nỗi sợ lớn | Trang dài, nút mua xuống thấp nếu không có sticky CTA |
| C. Hybrid | Buy Box gọn + thanh trust/lợi ích ngay sau đó, phần chi tiết bên dưới | Traffic ads cold, mobile | Dễ thành "cái gì cũng có", mất trọng tâm |

* Mỗi phương án phải có: thứ tự section, **giả thuyết vì sao tăng CR** (gắn với pain-point ở 1b và pattern ở 1c), phù hợp với ai, rủi ro, bằng chứng đi kèm (loại A–D).
* **Chốt bằng ma trận quyết định:** chấm 1–5 theo các tiêu chí độ khớp pain-point, mạnh của bằng chứng, độ dài mobile, phù hợp traffic/brand ở Bước 0, độ khó dựng. Ghi rõ lý do chọn.
* **Wireframe low-fi** (khung hộp, chưa có màu/ảnh) cho phương án đã chọn, **cả 2 kích thước: mobile 390px và desktop 1440px**.
  * Định dạng: AI viết wireframe dạng HTML đơn giản (khối xám, nhãn section, chữ mẫu theo giới hạn ký tự) rồi xuất ảnh PNG, hoặc PD dựng nháp nhanh trên Claude Design từ mô tả của AI. Chọn một cách và ghi vào báo cáo Bước 1.
  * Đầu ra: `wireframe_mobile_390.png`, `wireframe_desktop_1440.png`, kèm mô tả thứ tự section dạng chữ.
  * **PD duyệt wireframe trước khi sang Bước 2 và 4.** Sửa layout ở giai đoạn này rẻ hơn rất nhiều so với sửa sau khi đã viết content và dựng UI.
* Các phương án không chọn không bị bỏ: chuyển thành giả thuyết A/B cho Bước 6.

**1e. Chốt khung trang (Self-Critique có rubric)**
* Khung gợi ý (điều chỉnh theo 1a–1d, cắt hoặc thêm đều phải ghi lý do; thứ tự chính thức theo phương án layout đã chốt ở 1d):
  1. Header
  2. Buy Box: gallery, tiêu đề, rating, giá, 3 lợi ích, chọn variant/bundle, CTA, trust row
  3. Lợi ích dạng thị giác (2–3 khối ảnh lớn + chữ ngắn)
  4. Review & bằng chứng xã hội
  5. Specs & FAQ (accordion)
  6. Upsell/CTA cuối trang
* Chấm khung theo thang 1–5, ghi lỗi theo P0/P1/P2:
  1. Độ dài: lên mobile có quá dài hoặc quá nhiều box không? (mục tiêu ≤ 6–8 chiều cao viewport)
  2. Màn đầu có trả lời đủ: cho ai → giải quyết gì → trông ra sao → giá → nút mua & cam kết không?
  3. Mỗi pain-point ở bảng map đã có chỗ giải tỏa chưa?
  4. Đã có cơ chế tăng CR (sticky CTA, trust, giảm rủi ro) và AOV (bundle, upsell, ngưỡng free ship) chưa?
* **Truy nguồn từng section:** mỗi section trong khung phải ghi rõ nó phục vụ pattern benchmark nào hoặc pain-point nào trong bảng map. Section không truy được nguồn thì cắt.
* Để tránh tự chấm dễ dãi, cho AI phản biện lần lượt bằng 3–4 persona thật của ngành, thay vì một "reviewer" chung chung. Mỗi persona phải chỉ ra ít nhất 2 lý do khiến họ *không* mua:
  * **Mẹ lần đầu, 3 giờ sáng, cầm máy một tay:** có hiểu ngay sản phẩm và chọn đúng size không?
  * **Bố hay nghiên cứu kỹ:** thông số, chứng nhận, so sánh có đủ không?
  * **Ông bà/người mua quà:** có biết chọn size theo tuổi bé, có tùy chọn quà tặng không?
  * **Người kiểm duyệt an toàn & pháp lý:** có claim y tế nào vượt quá căn cứ, ảnh nào thể hiện tư thế ngủ không an toàn không?
* Nếu có điều kiện, chạy phần chấm này ở một phiên/model khác với phiên đã viết khung.

### Bước 2: Content + Brand & Tokens

**2a. Viết full content thực tế**

* Tạo thương hiệu & sản phẩm độc lập (sạch bản quyền).
* Viết đủ chữ cho các component đặc thù ở 4a: size guide (bảng size theo tháng tuổi/cân nặng, hướng dẫn chọn TOG theo nhiệt độ phòng), tùy chọn quà tặng, thông tin giao hàng/tồn kho, dòng trả góp/BNPL, nhãn lọc review theo tuổi bé.
* Viết 3–5 phương án Headline/Buy Box rồi chọn phương án sắc bén nhất. Mỗi phương án phải bám 1 pain-point hoặc 1 lợi ích cụ thể.
* Viết 100% câu chữ thật cho toàn trang (Header, Buy Box, Bundle, Feature, Specs, Reviews, FAQ). Không dùng lorem ipsum.
* **Giới hạn ký tự cho mobile:** headline ≤ 8–10 từ, mỗi lợi ích ≤ 6–8 từ, mỗi đoạn mô tả ≤ 2–3 dòng ở 390px.
* **Quy tắc an toàn nội dung:**
  * Không bịa số liệu thống kê ("98% hài lòng", "10.000 khách") và không để review do AI viết trông như thật. Gắn nhãn *placeholder/sample* trong file copy.
  * Không đưa claim y tế, tài chính hoặc claim tuyệt đối mà không có căn cứ.
  * Riêng Mẹ & Bé: không dùng các claim như "ngăn ngừa SIDS", "chữa đầy hơi", "an toàn 100%". Thay bằng mô tả cụ thể, kiểm chứng được (chất liệu, chứng nhận, thiết kế theo hướng dẫn nào). Chứng nhận trong template chỉ là ví dụ minh họa, ghi rõ trong copy doc là merchant phải thay bằng chứng nhận thật.
* Xuất file **copy doc** (toàn bộ chữ theo từng section) để dùng cho handoff.

**2b. Brand & Tokens** (tạo các file `05_tokens/` và `07_brand/` cho pack)

* **Tên brand:** 3–5 phương án, kiểm tra nhanh không trùng brand Mẹ & Bé đã có (tìm Google, Shopify, sàn TMĐT). PD chọn 1.
* **Logo:** wordmark vector đơn giản (chữ + tối đa 1 ký hiệu nhỏ), xuất `logo.svg`. AI viết SVG hoặc mô tả để PD dựng trên Claude Design. Không dùng tool ảnh AI vì chữ dễ méo.
* **Design tokens:** chuyển Visual Direction Brief (1c-bis) thành giá trị cụ thể:
  * Màu: nền, chữ, chữ phụ, accent, CTA, đường kẻ, trạng thái (lỗi, thành công, hết hàng), mã hex, và **kiểm tra tương phản đạt WCAG AA** cho từng cặp chữ/nền.
  * Font: tối đa 2 font (nguồn miễn phí như Google Fonts), thang chữ cho mobile và desktop, line-height, độ đậm.
  * Spacing theo lưới 8pt, bo góc, độ dày đường kẻ, đổ bóng (nếu có).
  * Xuất `tokens.md` (để người đọc) và `tokens.json` (để máy đọc).
* **Bộ icon:** chọn một bộ (Lucide hoặc Phosphor, không trộn), một độ dày nét. Liệt kê icon cần dùng (giao hàng, đổi trả, an toàn, chất liệu, quà tặng...) và đưa vào `07_brand/icons/`.
* Cổng duyệt Bước 2: PD duyệt cả copy doc lẫn brand & tokens cùng lúc.

### Bước 3: Prompt Sinh Ảnh → PD Sinh Ảnh Bằng Tool Ngoài → AI Kiểm Ảnh

Claude Design không tạo ảnh, nên ảnh được sinh bằng **tool ảnh AI bên ngoài** (PD tự chọn tool). Bước này đặt **sau khi Bước 0–2 đã được duyệt** (brief, research, hướng thị giác, wireframe, copy), vì prompt ảnh chỉ chuẩn khi mọi thứ trên đã chốt. Bước 3 có **2 điểm dừng để PD duyệt**.

**3a. AI viết Image Prompt Pack (điểm dừng 1: PD duyệt prompt)**
1. **Product Visual Spec Sheet:** mô tả cố định sản phẩm hư cấu để mọi prompt dùng chung: hình dáng, kích thước, màu (mã màu), chất liệu, chi tiết (khóa kéo, đường may, nhãn), vị trí và dạng logo. Đây là "nguồn sự thật" chống lệch sản phẩm giữa các ảnh.
2. **Shot list:** liệt kê từng ảnh cần có, mỗi ảnh gắn với **vị trí trên trang** (từ wireframe), mục đích, tỉ lệ, nội dung copy đi kèm.
3. **Prompt cho từng ảnh**, viết tool-agnostic (không phụ thuộc một tool) gồm: chủ thể (chép từ Spec Sheet), bối cảnh, ánh sáng, góc máy, phong cách (lấy từ Visual Direction Brief), tỉ lệ, **negative** (chữ méo, tay/ngón sai, tư thế ngủ không an toàn, sản phẩm lệch, logo sai), tên file đầu ra. Ảnh hero có prompt riêng và đi trước.
4. **Hướng dẫn sinh theo thứ tự:** hero trước → PD duyệt hero → dùng hero làm ảnh tham chiếu (image reference) cho các ảnh còn lại. Nếu tool không hỗ trợ ảnh tham chiếu, ghi rõ cách xử lý (lặp lại Spec Sheet nguyên văn trong mỗi prompt, cố định seed/style nếu tool cho phép).
5. **Biến thể theo tool:** PD cho biết tool đang dùng (ví dụ Midjourney, Imagen, Flux, GPT image...) thì AI điều chỉnh cú pháp (tham số tỉ lệ, reference, negative). Chưa biết tool thì giữ bản tool-agnostic.
6. **Ảnh có chữ (infographic, bảng size, ảnh bundle có nhãn giá):** tool ảnh AI hay làm méo chữ. Mặc định **không sinh bằng tool ảnh**, mà dựng trực tiếp trên Claude Design bằng chữ thật từ copy doc. Tool ảnh chỉ sinh phần nền/ảnh sản phẩm không chữ.

**3b. PD sinh ảnh bằng tool ngoài và đưa ảnh về**
* PD copy prompt, sinh ảnh, chọn bản tốt nhất cho từng vị trí, đặt đúng tên file theo shot list và đưa vào `06_images/`.
* Mỗi ảnh nên sinh nhiều bản (ít nhất 3–4) để có chỗ chọn.

**3c. AI kiểm ảnh (điểm dừng 2: PD duyệt bộ ảnh)**
* AI xem từng ảnh PD đưa lên, đối chiếu với Spec Sheet và checklist (mục "Soi lỗi" bên dưới), chấm đạt/không đạt kèm lý do.
* Ảnh không đạt: AI **sửa prompt** (không chỉ nói "sinh lại"), PD sinh lại, lặp lại tối đa 2–3 vòng cho mỗi ảnh. Nếu vẫn lỗi thì đổi cách chụp (ví dụ đổi góc không lộ tay/mặt).
* Khi PD duyệt: tạo `image_manifest.md` (file | mục đích | vị trí trên trang | alt text | tỉ lệ) và đưa bộ prompt đã chỉnh cuối cùng vào `08_prompts/image_prompts.md`, để tái tạo được về sau.

**Spec khi viết prompt:** tỉ lệ ảnh (4:5 hoặc 1:1), nền sáng, hướng ánh sáng, bảng màu. Spec phải khớp layout gallery ở wireframe và **phong cách ảnh/palette trong Visual Direction Brief (1c-bis)**.

**Bộ ảnh cần có (6–8 ảnh, tách ảnh sinh bằng tool và ảnh dựng trên Claude Design):**
  1. Hero góc 3/4 (nền sáng)
  2. Góc ngang/mặt bên
  3. Cận cảnh chất liệu/chi tiết
  4. Lifestyle sử dụng thực tế
  5. Ảnh tỉ lệ/kích thước (cầm trên tay hoặc đặt cạnh vật quen thuộc)
  6. Infographic lợi ích (**dựng trên Claude Design** vì có chữ, không sinh bằng tool ảnh)
  7. Ảnh gói Combo/Bundle (sinh ảnh sản phẩm không chữ, nhãn giá/tiết kiệm dựng trên Claude Design)
  8. 1–2 ảnh kiểu UGC (dùng cho khu review, tránh cảm giác toàn ảnh quảng cáo)
* **Soi lỗi từng ảnh:** sản phẩm lệch giữa các ảnh, chữ bị méo, bàn tay/ngón tay sai, bóng đổ không khớp. Ảnh lỗi thì sinh lại, không dùng tạm.
* Ngoài ảnh studio, cần ảnh có thể đọc rõ ở thumbnail nhỏ trên mobile.
* **Quy tắc ảnh riêng cho Mẹ & Bé:**
  * Ảnh em bé do AI sinh dễ lỗi giải phẫu (tay, tỉ lệ đầu, khuôn mặt) và rất dễ bị phát hiện. Ưu tiên ảnh sản phẩm, ảnh bàn tay bố mẹ, góc không lộ rõ mặt bé.
  * Ảnh lifestyle phải đúng hướng dẫn an toàn: bé nằm ngửa, nôi trống (không gối, chăn rời, thú bông). Một ảnh sai tư thế ngủ là đủ để mất trust với khách am hiểu.
  * Thêm bảng size theo tháng tuổi/cân nặng (dựng trên Claude Design bằng chữ thật, không sinh bằng tool ảnh).

### Bước 4: Spec UI → Đóng Gói Input Pack → Dựng Trên Claude Design (Mobile-First)

**4a. Spec component & quy tắc UI (nhúng nguyên văn vào prompt P1–P4)**

PD không dựng tay ở bước này. Đây là phần spec mà các prompt ở 4b sẽ chép vào để Claude Design làm theo.

*Danh sách component:*
* **Cơ bản:** Header, Gallery, Buy Box, Variant selector, Bundle selector, Accordion, Review card, Sticky CTA, Trust row.
* **Chuyển đổi:** khối giá (giá bán, giá gạch, tiền tiết kiệm, dòng trả góp/BNPL), thông tin giao hàng dự kiến và tồn kho, cross-sell/upsell.
* **Đặc thù Mẹ & Bé:**
  * **Size guide:** chọn size theo tháng tuổi/cân nặng, mở từ ngay cạnh variant selector, kèm hướng dẫn chọn độ ấm TOG theo nhiệt độ phòng.
  * **Tùy chọn quà tặng:** gói quà, thiệp lời nhắn (phục vụ persona ông bà/người mua quà).
  * **Bộ lọc review theo tuổi bé.**
* Tokens và icon lấy từ Bước 2b. Mọi lựa chọn lệch khỏi tokens phải ghi lý do.

*Quy tắc UI (Mobile 390px trước, gutter 16px, sau đó Desktop 1440px):*
* **Ngân sách màn đầu:** viewport 390×844 chỉ thấy khoảng 650–700px hữu dụng. Tiêu đề, rating và giá phải lộ ra ở màn đầu. Gallery không được chiếm hết màn. Có dấu hiệu vuốt được (dots, peek ảnh kế tiếp).
* **Sticky Add-to-Cart bar** hiện khi cuộn qua Buy Box.
* **Trust row** (đổi trả, giao hàng, bảo hành, thanh toán) nằm sát nút mua, không giấu vào accordion.
* **"Ít box" nghĩa là:** chỉ dùng khung cho thứ tương tác được (variant, bundle, nút). Nội dung tĩnh dùng khoảng trắng và đường kẻ mảnh.
* **Bundle selector:** tối đa 3 lựa chọn, mặc định chọn gói giữa gắn nhãn "Most popular", hiển thị tiền tiết kiệm bằng số tuyệt đối và giá mỗi đơn vị. Thêm thanh tiến độ free ship nếu phù hợp.
* **Accordion** chỉ cho Specs, chất liệu, hướng dẫn chăm sóc. Mở sẵn mục đầu tiên.
* **Truy cập:** tương phản chữ ≥ 4.5:1 (WCAG AA), vùng chạm ≥ 44px, chữ body ≥ 16px. Chú ý chữ xám nhạt và đường kẻ quá mảnh trên nền sáng.
* **Desktop:** bố cục 2 cột, gallery sticky bên trái, Buy Box bên phải. Đây không phải bản phóng to của mobile.
* **Đủ các trạng thái UI:** variant đang chọn/chưa chọn/hết hàng, nút đang xử lý, đã thêm vào giỏ, lỗi, size guide mở/đóng.

**4b. Đóng gói Claude Design Input Pack (file + ảnh + prompt)**

Tổng hợp đầu ra của Bước 0–3 thành một thư mục duy nhất. Gợi ý cấu trúc:

```
claude-design-input-pack/
├── 00_README.md              # Cách dùng pack: thứ tự đưa file/prompt lên Claude Design
├── 01_brief.md               # Brief Bước 0 (sản phẩm, tệp khách, giá, traffic, brand, tone)
├── 02_research/
│   ├── pain_point_map.md     # Bảng map pain-point → giải pháp → vị trí (1b)
│   ├── layout_decision.md    # Pattern chuẩn, 2–3 phương án, ma trận chọn (1c, 1d)
│   └── visual_direction_brief.md  # Hướng thị giác đã chọn (1c-bis)
├── 03_wireframe/
│   ├── wireframe_mobile_390.png
│   └── wireframe_desktop_1440.png
├── 04_copy/
│   └── copy_doc.md           # 100% chữ thật theo từng section, đánh dấu placeholder
├── 05_tokens/
│   ├── tokens.md             # Tạo ở Bước 2b: màu (mã hex), font, thang chữ, spacing, bo góc
│   └── tokens.json
├── 06_images/
│   ├── 01_hero.png ...       # Đặt tên theo thứ tự trong gallery
│   └── image_manifest.md     # Bảng: file | mục đích | vị trí trên trang | alt text | tỉ lệ
├── 07_brand/                 # Tạo ở Bước 2b
│   ├── logo.svg
│   └── icons/                # Bộ icon đã chọn
├── 08_prompts/
│   ├── P1_tokens_components.md
│   ├── P2_mobile_page.md
│   ├── P3_desktop_page.md
│   ├── P4_states.md
│   ├── P5_self_review.md
│   └── image_prompts.md      # Prompt sinh từng ảnh, để tái tạo được
└── 09_reference/
    └── benchmark_shots/      # Ảnh chụp benchmark đã chọn, mỗi ảnh có chú thích "mượn gì, vì sao"
```

*Bộ prompt (08_prompts), chạy lần lượt, mỗi lượt kiểm tra kết quả trước khi sang lượt sau:*

| Prompt | Nội dung | Tệp đính kèm |
|---|---|---|
| **P1 Tokens & components** | Dựng design tokens và toàn bộ component trong danh sách ở 4a (gồm cả khối giá, size guide, tùy chọn quà tặng, lọc review theo tuổi bé) | `visual_direction_brief`, `tokens`, `07_brand` |
| **P2 Mobile page 390px** | Ghép trang mobile theo wireframe và copy doc | `wireframe_mobile`, `copy_doc`, `06_images`, `image_manifest`, tokens |
| **P3 Desktop page 1440px** | Mở rộng sang desktop (2 cột, gallery sticky), không phải bản phóng to của mobile | Kết quả P2, `wireframe_desktop` |
| **P4 States** | Các trạng thái UI: chọn/hết hàng, đang xử lý, đã thêm giỏ, lỗi, accordion mở/đóng | Kết quả P2, P3 |
| **P5 Self-review** | AI tự chấm theo rubric Bước 5 và sửa lỗi P0/P1 | Rubric, ảnh chụp kết quả |

*Mỗi prompt phải có đủ các phần sau (viết rõ ràng, không viết mơ hồ kiểu "làm cho đẹp"):*
1. **Vai trò và mục tiêu:** "Bạn là Product Designer chuyên PDP e-commerce, mục tiêu là trang chuyển đổi cao cho ngành Mẹ & Bé."
2. **Bối cảnh:** tóm tắt brief (sản phẩm, tệp khách, giá, traffic, brand).
3. **Tệp đính kèm và cách dùng từng tệp:** tệp nào là nguồn sự thật cho gì (layout lấy từ wireframe, chữ lấy từ copy doc, màu/font lấy từ tokens, ảnh lấy từ manifest).
4. **Cấu trúc trang:** thứ tự section chính thức, ghi theo wireframe.
5. **Quy tắc UI bắt buộc:** chép nguyên văn danh sách component và quy tắc UI ở 4a (ngân sách màn đầu, sticky CTA, trust row, "ít box", bundle, truy cập).
6. **Những điều KHÔNG được làm:** không viết lại/rút gọn copy, không thêm hay bớt section, không dùng lorem ipsum, không đổi màu/font ngoài tokens, không dùng các claim đã cấm (xem Bước 2), không thêm ảnh ngoài manifest.
7. **Đầu ra mong muốn:** khung (frame) nào, kích thước nào, đặt tên layer/component ra sao.
8. **Tiêu chí chấp nhận:** trích từ rubric Bước 5 để AI tự kiểm trước khi trả kết quả.

*Prompt sinh ảnh (image_prompts.md)* đã được tạo và chốt ở **Bước 3** (trước khi đóng pack), không viết lại ở đây. Ở 4b chỉ kiểm tra file có trong pack, khớp tên với `image_manifest.md`, và ảnh đưa vào pack là ảnh đã được duyệt ở Bước 3c.

*Kiểm tra trước khi coi pack là xong:*
* Mọi tệp được prompt nhắc đến đều có trong pack, đúng tên.
* Copy doc không còn placeholder chưa được đánh dấu. Mọi ảnh trong manifest đều có file thật.
* **Chạy thử P1–P2** trên Claude Design để xem prompt có đủ rõ không. Prompt nào cho kết quả lệch thì sửa prompt, không chỉ sửa kết quả, rồi ghi lại phiên bản (v1, v2...). Bản prompt cuối cùng sau khi chạy thử là bản đưa vào pack.
* Kiểm tra giới hạn của Claude Design (số tệp, dung lượng, định dạng được chấp nhận, độ dài prompt) và điều chỉnh cách đóng gói cho phù hợp (ví dụ gộp nhiều file thành một, nén ảnh). Phần này chưa được xác minh trong plan, PD cần kiểm tra thực tế.

**4c. Dựng trên Claude Design**
* Chạy lần lượt P1 → P2 → P3 → P4 → P5 từ pack. Sau mỗi prompt, PD kiểm tra kết quả trước khi chạy prompt tiếp theo.
* Kết quả lệch spec thì ưu tiên **sửa prompt trong pack** rồi chạy lại, để pack luôn khớp với thiết kế cuối.

### Bước 5: Review Giao Diện Bằng Rubric (2–3 Vòng) + Kiểm Tra Người Thật

**5a. Vòng AI review**
* Chụp màn hình Mobile (390px) và Desktop, đưa cho AI reviewer (persona Principal PD + CRO) chấm theo rubric, mỗi tiêu chí 1–5:

| Tiêu chí | Câu hỏi kiểm tra |
|---|---|
| Buy Box mobile | Gọn, đẹp, thấy giá + rating + CTA? Sticky CTA hoạt động? |
| Khớp layout đã chốt | UI cuối có đúng wireframe và lý do chọn ở 1d không? Chỗ nào lệch thì có lý do ghi lại? |
| Mật độ & độ dài | Có chia quá nhiều box? Trang ≤ 6–8 chiều cao viewport? |
| Đồng bộ thương hiệu | Header, logo, font, icon, ảnh đồng nhất, tạo cảm giác tin cậy? |
| Khớp Visual Direction Brief | Màu, font, phong cách ảnh, icon có đúng hướng đã chốt? Visual hierarchy dẫn mắt đúng thứ tự giá → lợi ích → CTA? Cảm xúc tổng thể đúng 3 tính từ đã chọn? |
| Trust & giảm rủi ro | Mỗi pain-point ở bảng map đã được giải tỏa đúng chỗ? |
| Bundle & AOV | Rõ ràng, dễ chọn, tiết kiệm hiển thị rõ? |
| Truy cập | Tương phản, vùng chạm, cỡ chữ đạt chuẩn? |
| Đầy đủ trạng thái | Có đủ các state ở Bước 4a? |
| Component đặc thù ngành | Size guide, tùy chọn quà tặng, khối giá/BNPL, giao hàng/tồn kho, lọc review theo tuổi bé có đủ và dễ dùng trên mobile? |

* Phân loại lỗi: **P0** (chặn mua/gây hiểu lầm), **P1** (giảm chuyển đổi rõ), **P2** (hoàn thiện).
* **Điều kiện dừng:** hết P0/P1 và mọi tiêu chí ≥ 4. Mỗi vòng phải sửa thật và chụp lại. Nếu reviewer chỉ khen mà không tìm ra vấn đề, đổi persona hoặc phiên khác.

**5b. 5-second test (nếu có thể)**
* Cho 3–5 người xem màn đầu mobile trong 5 giây, rồi hỏi: *Đây là sản phẩm gì? Dành cho ai? Giá bao nhiêu? Bạn sẽ bấm vào đâu?*
* Nếu ≥ 2 người trả lời sai ở cùng một câu, sửa màn đầu rồi test lại.

### Bước 6: Handoff Package

* **Claude Design Input Pack bản cuối** (cấu trúc ở 4b, gồm file, ảnh và bộ prompt P1–P5 + prompt sinh ảnh đã qua chạy thử, có ghi phiên bản). Đây là đầu ra chính để tái sử dụng làm template. Phần lõi giữ nguyên; đổi ngành thì chạy lại module theo ngành (Bước 0–3) như định nghĩa ở phần Mục tiêu.
* **Design spec:** tokens, component, kích thước, khoảng cách, breakpoint (Mobile 390px, Desktop).
* **Annotation & trạng thái:** các state ở Bước 4, hành vi sticky CTA, gallery, accordion, bundle selector.
* **Asset export:** bộ ảnh đúng tỉ lệ, logo vector, icon.
* **Copy doc:** toàn bộ chữ thật, đánh dấu phần placeholder (review, số liệu).
* **Bảng pain-point → giải pháp** từ Bước 1b, để dev/marketer hiểu lý do thiết kế.
* **Danh sách giả thuyết A/B test** (3–5 mục), ví dụ:
  * Mặc định gói bundle giữa vs gói lẻ.
  * Có hoặc không có sticky CTA.
  * Vị trí khu review (trước hoặc sau phần lợi ích).
  * Các phương án layout đã loại ở 1d (ví dụ chuyển từ Hybrid sang Buy-first hoặc Proof-first), kèm giả thuyết ở 1c.
  * Headline theo pain-point A vs B.
  * Có hoặc không có thanh tiến độ free ship.
* **Visual Direction Brief** (hướng đã chọn, hướng đã loại, bảng visual audit, bằng chứng loại A–D) để người nhận hiểu vì sao chọn màu, font, phong cách này.
* **Research layout:** bảng pattern (loại nguồn A–D, độ tin cậy), 2–3 phương án layout cùng ma trận chọn, wireframe đã duyệt. Giúp người nhận biết vì sao layout này được chọn và nên thử gì tiếp theo.

---

## 3. Câu Hỏi Nhờ AI Reviewer Kiểm Tra Lại Plan v2

Hãy đóng vai **Principal Product Designer kiêm Chuyên gia CRO E-commerce**, đánh giá ngắn gọn plan trên:
1. Bước 0 và Bước 1 (benchmark từ trang thật, bảng map pain-point, research layout có phân loại nguồn A–D, đề xuất 2–3 phương án, self-critique có rubric) đã đủ chặt để tránh kết quả chung chung và tránh kết luận layout dựa trên số liệu bịa chưa?
2. Còn yếu tố nào của một PDP chuẩn bị thiếu hoặc chưa cụ thể?
3. Quy tắc UI ở Bước 4 có chỗ nào mâu thuẫn với nhau hoặc khó thực hiện trên Claude Design không?
4. Rubric Bước 5 và gói handoff Bước 6 đã đủ để kết luận bản thiết kế sẵn sàng bàn giao chưa?
