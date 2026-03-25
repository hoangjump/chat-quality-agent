# Changelog

## v2026.03.26

### Tinh nang moi
- **Thong bao cap nhat**: Banner thong bao khi co phien ban moi + changelog + huong dan update
- **Nut Dung job**: Co the dung job dang chay tu giao dien (#7)
- **Docs + Version**: Hien thi o sidebar, truy cap nhanh tai lieu va changelog

### Bug Fixes
- **Job bi treo**: Fix infinite loop khi batchSize=0, them context cancellation check, check loi DB query (#7)
- **Facebook token**: Fix loi "must be called with Page Access Token" — tu dong exchange User Token thanh Page Token (#12, #13, #14)
- **Gemini models**: Thay gemini-2.0-flash (deprecated) bang gemini-2.5-flash/pro
- **Lich chay**: Khong luu duoc "Lich chay" khi sua cong viec (#9)
- **AI model**: Job detail hien dung AI model tu Settings global thay vi gia tri cu (#33)
- **Ty gia**: Dashboard dung ty gia tu tenant settings thay vi hardcode 26000 VND (#23)
- **Install script**: Fix bi treo tren Ubuntu do interactive prompt (#35)
- **Anh trong danh gia**: Hien thi anh/sticker/file trong "Dien bien cuoc chat" + lightbox zoom (#39)

### Bao mat
- Them security log khi tu choi truy cap file (IDOR fix)
- IDOR: Kiem tra tenant ownership khi serve file (#22)
- Token refresh: Fix race condition gay logout bat ngo (#26)
- OAuth state URL-encoded (#29)
- Goroutine timeout cho TriggerJob va TestRunJob (#30, #31)
- Gioi han per_page max 100 tranh DB exhaustion (#32)
- Infinite polling: Frontend tu dung poll sau timeout (#27, #28)

### Documentation
- Sua huong dan lay Telegram Group ID — dung Telegram Web (#36)
- Them huong dan chay localhost (Zalo OA ho tro callback localhost) (#34)
- Sua docs Zalo OA: localhost khong can SSL (#37)
- Don gian hoa cai dat Watchtower — 1 lenh curl thay vi sua YAML thu cong

---

## v2026.03.24

### Bug Fixes
- **Timezone**: Sửa lệch giờ 7 tiếng giữa Zalo OA và CQA — giờ hiển thị đúng GMT+7 (#5)
- **Sửa công việc**: Không lưu được "Quy tắc cho AI" khi sửa công việc phân tích (#2)
- **Đồng bộ kênh**: Chuyển sang async để tránh lỗi 504 timeout khi đồng bộ
- **Rate limit**: Tăng giới hạn mặc định lên 500/IP và 1000/user mỗi phút
- **Hiển thị ảnh**: Sửa lỗi không hiển thị ảnh từ Facebook trong tin nhắn
- **Auto-reload**: Tự tải lại khi JS chunks cũ sau deploy

### Mobile UI
- Onboarding bar: scroll ngang mượt, nút X luôn hiện
- Dashboard: ẩn tiêu đề trên mobile, date filter responsive
- Tin nhắn: toggle list/detail trên mobile thay vì xếp chồng
- Tạo công việc: stepper không còn đè chữ
- Chi tiết công việc: header compact, buttons responsive
- Bảng dữ liệu: thêm scroll ngang cho các bảng bị tràn

### CI/CD
- Tự động build + push Docker image lên Docker Hub khi push main
- Versioning theo ngày: v2026.03.24, v2026.03.24.2...
- Tự động tạo GitHub Release với changelog

### Documentation
- Thêm yêu cầu hệ thống vào hướng dẫn cài đặt
- Ảnh trong docs có thể click zoom
- Hỗ trợ macOS và Windows (Docker Desktop)

---

## [1.0.0] - 2025-03-23

### Ra mắt phiên bản đầu tiên

- Đồng bộ tin nhắn từ Zalo OA và Facebook Messenger
- Đánh giá chất lượng CSKH bằng AI (Claude / Gemini)
- Phân loại chat theo chủ đề tùy chỉnh
- Cảnh báo tự động qua Telegram và Email
- Batch AI mode — tiết kiệm chi phí gọi AI
- Dashboard với biểu đồ và thống kê
- Multi-tenant với phân quyền Owner > Admin > Member
- Tích hợp MCP cho Claude Web/Desktop
- Nginx reverse proxy + SSL tự động (Let's Encrypt)
- Docker Compose deployment
- Hỗ trợ Docker Hub images
