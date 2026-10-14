## So sánh Deploy thủ công và DevOps (CI/CD)

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
|---|---|---|
| Làm sao để deploy? | Tự copy file lên server bằng FTP/SCP hoặc đăng nhập hosting, upload từng file bằng tay | Push code lên GitHub → pipeline tự chạy |
| Mất bao lâu? | Vài phút đến hàng chục phút, tùy số file và thao tác | ~30 giây |
| Ai làm deploy? | Con người (developer hoặc admin) làm trực tiếp | GitHub Actions (máy tự làm) |
| Có bị sai sót không? | Có, dễ upload thiếu file, nhầm thư mục, deploy nhầm phiên bản | Không — pipeline nhất quán 100% |
| Rollback nếu lỗi? | Khó và chậm: phải tìm bản cũ, upload đè lại bằng tay | `git revert` + push → tự động rollback |
| Làm sao biết deploy thành công? | Tự mở website kiểm tra bằng mắt, hoặc chờ người dùng báo lỗi | GitHub Actions gửi notification ✅/❌ |
