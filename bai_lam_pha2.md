# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ TÀI CHÍNH CÁ NHÂN)

- **Họ tên:** Nguyễn Ngọc Tú
- **Lớp:** CNTT3
- **Link repository Pha2:** https://github.com/TusNguyennVN/HNKS26CNTT3_KyNangPromtingvoiAI_luyen_tap
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký hội thảo ra JSON

**KET QUA AI**

```text
[
  {
    "ma_goi": "DT",
    "ngay_hoi_thao": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "hang_ve": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "CB",
    "ngay_hoi_thao": "2027-01-10",
    "nguoi_lon": 3,
    "tre_em": 0,
    "hang_ve": "thuong",
    "ghi_chu": "xe lăn cần lối đi riêng"
  },
  {
    "ma_goi": "VIP",
    "ngay_hoi_thao": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "hang_ve": "vip",
    "ghi_chu": "ngồi bàn đầu gần màn hình chiếu"
  }
]
```

**Link trò chuyện:** https://share.gemini.google/63Dg91kzcmK3

## 4.3. Báo giá vé hội thảo bằng Chain-of-Thought

**KET QUA AI**

```text
Dưới đây là bảng kê chi tiết tính toán báo giá cho gói **DT (Gói Đầu Tư)** với đơn giá gốc là **1.500.000 đồng/người lớn**:

1. **Tiền người lớn:**
Nhóm có 4 người lớn.
* Phép tính: $4 \times 1.500.000 = 6.000.000$ đồng


2. **Tiền trẻ em:**
* 2 trẻ em (8 tuổi và 11 tuổi) nằm trong độ tuổi từ 6 đến 12 nên tính 50% giá vé người lớn ($1.500.000 \times 50\% = 750.000$ đồng/trẻ).
* 1 bé 4 tuổi (dưới 6 tuổi) được miễn phí ($0$ đồng).
* Phép tính: $(2 \times 1.500.000 \times 50\%) + (1 \times 0) = 1.500.000$ đồng


3. **Tiền vé (trước giảm giá):**
* Phép tính: $6.000.000 + 1.500.000 = 7.500.000$ đồng


4. **Giảm giá nhóm:**
Nhóm có đủ 4 người lớn trở lên nên được áp dụng mức giảm 10% trên tổng tiền vé.
* Tiền được giảm: $7.500.000 \times 10\% = 750.000$ đồng
* Tiền vé sau giảm giá: $7.500.000 - 750.000 = 6.750.000$ đồng


5. **Phụ thu sổ tay:**
Nhóm đặt mua 2 bộ sổ tay lập kế hoạch tài chính cá nhân (không áp dụng giảm giá).
* Phép tính: $2 \times 200.000 = 400.000$ đồng


6. **Tổng tiền thanh toán:**
* Phép tính: $6.750.000 + 400.000 = 7.150.000$ đồng



[RESULT: 7.150.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/McLjy6pSIpBK

### b) Kiểm tra kết quả AI

Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_phien_bi_anh_huong": 2,
  "tom_tat": "Khách mua gói DT bị xếp ghế phụ thiếu bàn viết trong 2 phiên đầu."
}
```

**Link trò chuyện:** https://share.gemini.google/6cHUJW6wL528

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 2,5 / 5,0 | **Đạt (2,5 điểm):** Cung cấp chính xác điều kiện hoàn 100% tiền vé khi thông báo huỷ trước ngày diễn ra sự kiện ít nhất 4 ngày.<br>

<br>

<br>**Lỗi trừ điểm (-2,5 điểm):**<br>

<br>- **Câu bị lỗi (trích nguyên văn):** *"Vé gói Đầu Tư bên em giá chỉ 1.200.000đ/người thôi, đi học về đầu tư chứng khoán lời khủng luôn ạ."*<br>

<br>- **Lý do sai:** Báo sai giá vé niêm yết của ban tổ chức đối với gói Đầu Tư (giá chuẩn là 1.500.000đ/người, không phải 1.200.000đ/người). | **Câu sửa đề xuất:** *"Hiện tại, vé gói Đầu Tư của chương trình có mức giá niêm yết là 1.500.000đ/người."* |
| **Đầy đủ (30%)** | 1,5 / 3,0 | **Đạt (1,5 điểm):** Đã đề cập đủ hai nội dung khách hàng thắc mắc là giá vé và chính sách huỷ vé.<br>

<br>

<br>**Lỗi trừ điểm (-1,5 điểm):**<br>

<br>- **Câu bị lỗi (trích nguyên văn):** *"Anh/chị báo huỷ trước 4 ngày thì bên em hoàn lại đủ 100% tiền vé nha, cứ yên tâm chốt đơn đi ạ!"*<br>

<br>- **Lý do sai:** Thiếu lời mời khách hàng cung cấp thông tin đăng ký bắt buộc gồm **ngày tham dự hội thảo** và **số lượng vé muốn đăng ký**. | **Câu sửa đề xuất:** *"Nếu anh/chị có nhu cầu tham dự, vui lòng cho em biết ngày hội thảo dự kiến tham gia cùng số lượng vé muốn đăng ký để em hỗ trợ giữ chỗ ạ."* |
| **Giọng điệu (20%)** | 0,0 / 2,0 | **Lỗi trừ điểm 1 (-1,0 điểm):**<br>

<br>- **Câu bị lỗi (trích nguyên văn):** *"Dạ chào anh/chị nha! Vé gói Đầu Tư bên em giá chỉ 1.200.000đ/người thôi, đi học về đầu tư chứng khoán lời khủng luôn ạ."*<br>

<br>- **Lý do sai:** Sử dụng từ ngữ suồng sã (*"nha"*) trong giao tiếp và đưa ra lời hứa hẹn lợi nhuận quá đà (*"lời khủng luôn ạ"*), vi phạm chuẩn mực tư vấn lĩnh vực tài chính.<br>

<br>

<br>**Lỗi trừ điểm 2 (-1,0 điểm):**<br>

<br>- **Câu bị lỗi (trích nguyên văn):** *"Anh/chị báo huỷ trước 4 ngày thì bên em hoàn lại đủ 100% tiền vé nha, cứ yên tâm chốt đơn đi ạ!"*<br>

<br>- **Lý do sai:** Tiếp tục lặp lại tiểu từ suồng sã (*"nha"*) và dùng khẩu ngữ bán hàng thiếu chuyên nghiệp (*"cứ yên tâm chốt đơn đi ạ!"*). | **Câu sửa đề xuất 1:** *"Dạ, em xin chào anh/chị. Vé gói Đầu Tư có giá niêm yết là 1.500.000đ/người, nội dung tập trung cung cấp kiến thức và phương pháp đầu tư chứng khoán bài bản ạ."*<br>

<br>

<br>**Câu sửa đề xuất 2:** *"Trường hợp anh/chị thông báo huỷ trước ngày diễn ra sự kiện ít nhất 4 ngày, ban tổ chức sẽ hỗ trợ hoàn lại 100% giá trị vé ạ."* |
| **Tổng điểm** | **4,0 / 10** | **Chưa đạt yêu cầu.** Nhân viên tư vấn tập sự báo sai thông tin giá vé niêm yết, bỏ sót bước khai thác thông tin đặt vé của khách hàng và mắc lỗi nghiêm trọng về chuẩn mực ngôn từ tư vấn. | Nhân viên cần rà soát lại biểu phí chuẩn của ban tổ chức, bổ sung đầy đủ thông tin điều hướng đăng ký và điều chỉnh văn phong lịch sự, chuẩn mực, tuyệt đối không cam kết lợi nhuận đầu tư. |
```

**Link trò chuyện:** https://share.gemini.google/D60HiNKx8cqQ
