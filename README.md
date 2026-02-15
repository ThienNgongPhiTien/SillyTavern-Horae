# Horae - Ký Ức Thời Gian v1.0.1 | Plugin Tăng Cường Trí Nhớ SillyTavern

![Image](https://github.com/SenriYuki/SillyTavern-Horae/blob/main/HoraeLogo.jpg)

> *Horae (Hōrai) — Những nữ thần cai quản trật tự thời gian và các mùa trong thần thoại Hy Lạp*

Người chơi Roleplay (RP) dài tập chắc chắn đã từng gặp phải "bệnh cũ" này —— Trí nhớ của AI chỉ ngang với cá vàng: Chuyện hôm qua thì nói thành sáng nay, thậm chí chuyện xảy ra vài ngày trước thì lúc nào cũng bảo là "hôm qua"; cảnh trước vừa mặc đồng phục, cảnh sau thình lình đổi sang đồ thường; mối quan hệ NPC bị đảo lộn; quà đã tặng tự nhiên biến mất, đồ đã vứt đi lại quay về trên tay.

**Horae sử dụng các mốc thời gian có cấu trúc để trang bị cho AI của bạn một "cuốn sổ ghi nhớ" đáng tin cậy.**

**Lưu ý khi sử dụng:** Sau khi chỉnh sửa thẻ plugin bằng cây bút chì nhỏ hoặc thanh dưới cùng và lưu lại, hãy nhớ nhấn **nút làm mới (refresh)** ở thanh dưới cùng (giống như khi thao tác với thẻ biến số), plugin sẽ đọc nội dung đã sửa đổi để cập nhật dữ liệu.

---

## Các tính năng nổi bật

**Tạm biệt "Ngày Hôm Qua Vô Tận"**
Plugin tự động tính toán thời gian tương đối, tiêm vào các biểu đạt đời thường như "hôm qua", "thứ Tư tuần trước", "ngày 15 tháng trước". Cuối cùng AI cũng có thể phân biệt được hôm kia và tuần trước. Hỗ trợ đa dạng hệ thống lịch như hiện đại, lịch sử, kỳ ảo giả tưởng.

**Trang phục không còn "mặc loạn"**
Trang phục hiện tại của mỗi nhân vật được khóa và ghi lại, và hệ thống chỉ gửi thông tin trang phục của những nhân vật **có mặt**. Nhân vật sẽ không còn tự nhiên thay lại bộ đồ hôm qua một cách vô lý, và cũng không gửi mô tả quần áo của những người vắng mặt cho AI để tránh lãng phí token.

**NPC không còn bị "mờ nhạt" dần**
Các trường ngoại hình, tính cách, mối quan hệ,... được theo dõi độc lập. Tuổi tác thậm chí còn tự động tăng theo thời gian trong cốt truyện. Thiết lập các quy tắc Prompt nghiêm ngặt cho mối quan hệ, không còn tình trạng "bạn của bạn" bị nhầm thành "bạn trai".

**Quản lý túi đồ thông minh**
Tự động theo dõi ai đang giữ vật phẩm và nó đang nằm ở đâu (Ví dụ: Trên tay, trong balo, hay cất trong kho). Hỗ trợ đánh dấu vật phẩm Quan trọng (!) và Then chốt (!!). Tự động dọn dẹp các vật phẩm đã tiêu hao.

**Trực quan hóa Độ hảo cảm**
Ghi lại biến động tình cảm của NPC đối với nhân vật chính. Hỗ trợ cả giá trị tuyệt đối và giá trị tương đối.

**Lịch trình & Kế hoạch (Agenda)**
Ghi nhớ các lời hứa hẹn, cuộc hẹn hò hoặc kế hoạch trong tương lai. Tự động nhắc nhở AI khi đến ngày và xóa bỏ khi sự kiện đã hoàn thành.

**Bảng tùy chỉnh phong cách Excel**
Bạn cần theo dõi các chỉ số đặc biệt? Hãy tạo bảng tính 2x2 ngay trong plugin để AI tự điền thông tin theo ý bạn (Ví dụ: Bảng trạng thái cơ thể, Bảng quản lý kinh doanh, v.v.).

---

## Cơ chế hoạt động

1.  **Phân tích (Parsing):** Plugin quét nội dung phản hồi của AI để tìm thẻ `<horae>...</horae>`.
2.  **Lưu trữ & Tổng hợp:** Dữ liệu được trích xuất (Thời gian, Địa điểm, Vật phẩm...) sẽ được lưu vào metadata của tin nhắn và tổng hợp lại thành một "Trạng thái hiện tại" (Current State) mới nhất.
3.  **Tiêm ngữ cảnh (Injection):** Trước khi bạn gửi tin nhắn tiếp theo, Horae sẽ tạo một bản tóm tắt trạng thái ngắn gọn và chèn nó vào Prompt hệ thống (System Prompt) hoặc cuối lịch sử chat, giúp AI nắm bắt bối cảnh hiện tại một cách chính xác nhất.

---

## Cài đặt

1.  Tải xuống tệp nén hoặc Clone repository này.
2.  Giải nén vào thư mục `SillyTavern/public/scripts/extensions/`.
3.  Khởi động lại SillyTavern.
4.  Mở bảng điều khiển mở rộng (Extensions), tìm **Horae** và bật nó lên.

## Hướng dẫn sử dụng nhanh

* **Bảng điều khiển:** Nhấn vào icon Đồng hồ (Clock) trên thanh công cụ để mở bảng quản lý.
* **Chỉnh sửa thủ công:** Bạn có thể sửa trực tiếp thông tin trong bảng điều khiển ở dưới mỗi tin nhắn, hoặc dùng "Bút chì" để sửa thẻ `<horae>` trong văn bản gốc.
* **Regex:** Plugin đi kèm với các quy tắc Regex để ẩn thẻ `<horae>` khỏi giao diện chat, giúp trải nghiệm đọc truyện mượt mà hơn (nhưng AI vẫn nhìn thấy).

---

*Tác giả: SenriYuki*
*Dịch thuật: [Thiên Ngỗng Phi Tiên]*