# HCM-KS26-CNTT2_Nhap-mon-CNTT_Session10_ex6
```markdown
# BÀI TẬP: PHÂN TÍCH VÀ CHUYỂN ĐỔI TÀI LIỆU DỰ ÁN GREENTECH (PLAIN TEXT VS RICH TEXT)

##  PHẦN 1: PHÂN TÍCH TƯ DUY NGUYÊN NHÂN VÀ GIẢI PHÁP

### 1. Chỉ ra 2 sai lầm trong tư duy của Nam khi dùng file Rich Text (.docx)
* **Sai lầm 1 - Nhầm lẫn về khả năng quản lý phiên bản của Git:** 
  Nam dùng tệp Word (`.docx`) để lưu trữ tài liệu dự án trên Git[cite: 1]. Về bản chất, `.docx` là file nhị phân (binary/compressed archive) chứa nhiều mã cấu trúc phức tạp bên trong[cite: 1]. Do đó, Git không thể đọc và phân tích sự thay đổi chi tiết theo từng dòng (Git Diff)[cite: 1]. Chỉ cần Nam sửa một dấu phẩy, cấu trúc nhị phân của tệp bị thay đổi hoàn toàn, khiến Git hiểu rằng toàn bộ file đã bị chỉnh sửa và dẫn đến lỗi **xung đột toàn bộ file (Conflict)** khi làm việc nhóm[cite: 1].

* **Sai lầm 2 - Nhầm lẫn về tính tiện dụng và tương thích trên môi trường Dev:** 
  Nam nghĩ rằng dùng Word sẽ dễ trình bày và ai cũng có thể xem được[cite: 1]. Tuy nhiên, GitHub không hỗ trợ xem trực tiếp (preview) nội dung file `.docx` trên trình duyệt[cite: 1]. Điều này buộc các thành viên khác phải tải file về máy rồi mở bằng Microsoft Word, làm gián đoạn quy trình làm việc nhóm, mất thời gian và giảm tính hiệu quả khi review nhanh nội dung[cite: 1].

---

### 2. So sánh Markdown (Plain Text) và Word (Rich Text)

#### A. Khả năng chống hư hại file (Data Corruption)
* **Đối với File Word (.docx):** Nếu tệp bị gián đoạn mạng khi tải làm mất dù chỉ **1 byte** dữ liệu, toàn bộ cấu trúc file nhị phân sẽ bị hỏng hoàn toàn (corrupted) và ứng dụng sẽ không thể mở lại được[cite: 1].
* **Đối với Markdown (.md):** Markdown là văn bản thô (Plain Text)[cite: 1]. Nếu bị mất 1 byte hay một vài ký tự do lỗi truyền tải, chỉ đúng byte/ký tự đó bị ảnh hưởng hoặc biến dạng, toàn bộ phần nội dung còn lại của văn bản vẫn hoàn toàn nguyên vẹn, đọc được và dễ dàng khôi phục.

#### B. Tại sao Markdown lại an toàn và nhẹ hơn?
* **An toàn hơn:** Không bị phụ thuộc vào các phần mềm đọc file độc quyền; không nguy cơ hỏng toàn bộ dữ liệu do lỗi cấu trúc nhị phân; dễ dàng theo dõi chi tiết lịch sử chỉnh sửa trên Git (Git Diff) giúp việc merge code/tài liệu diễn ra suôn sẻ, ít xung đột[cite: 1].
* **Nhẹ hơn:** Không chứa các mã định dạng ngầm, hình ảnh nhúng phức tạp hay bộ đệm ứng dụng như Word[cite: 1]. File Markdown chỉ lưu trữ đúng các ký tự văn bản thuần túy và thẻ định dạng chuẩn (`#`, `-`, `**`), giúp dung lượng file siêu nhẹ (chỉ vài KB) và tối ưu hóa tối đa tốc độ `git push` / `git pull`[cite: 1].

---

##  PHẦN 2: NỘI DUNG CHUYỂN ĐỔI SANG MARKDOWN (.MD)

*(Có thể dán đoạn bên dưới vào StackEdit hoặc lưu thành file `README.md` trên GitHub)*

```markdown
# GreenTech

## 1. Giới thiệu
GreenTech là dự án hướng tới việc ứng dụng công nghệ để bảo vệ môi trường, giúp cuộc sống xanh và bền vững.

## 2. Mục tiêu
- Tạo ra giải pháp công nghệ xanh.
- Nâng cao ý thức cộng đồng.
- Phát triển bền vững.

```
