## So sánh Deploy thủ công và DevOps (CI/CD)

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
|---|---|---|
| Làm sao để deploy? | Tự copy file lên server bằng FTP/SCP hoặc đăng nhập hosting, upload từng file bằng tay | Push code lên GitHub → pipeline tự chạy |
| Mất bao lâu? | Vài phút đến hàng chục phút, tùy số file và thao tác | ~30 giây |
| Ai làm deploy? | Con người (developer hoặc admin) làm trực tiếp | GitHub Actions (máy tự làm) |
| Có bị sai sót không? | Có, dễ upload thiếu file, nhầm thư mục, deploy nhầm phiên bản | Không — pipeline nhất quán 100% |
| Rollback nếu lỗi? | Khó và chậm: phải tìm bản cũ, upload đè lại bằng tay | `git revert` + push → tự động rollback |
| Làm sao biết deploy thành công? | Tự mở website kiểm tra bằng mắt, hoặc chờ người dùng báo lỗi | GitHub Actions gửi notification ✅/❌ |

## Workflow CI/CD của dự án

<img width="822" height="650" alt="image" src="https://github.com/user-attachments/assets/945e8ae8-dc80-4b6b-82c0-28190f392072" />


 Trả lời câu hỏi

1. **DevOps tự động hóa những bước nào mà cách thủ công phải làm bằng tay?**
   Build, kiểm tra file và deploy lên GitHub Pages đều do GitHub Actions tự làm sau mỗi lần push.

2. **Nếu deploy sai, làm sao quay lại phiên bản cũ?**
   Dùng `git revert <commit>` rồi push, pipeline sẽ tự deploy lại bản cũ.

3. **Pipeline tiết kiệm bao nhiêu thời gian so với thủ công?**
   Thủ công: tải file, upload lên server, cấu hình, kiểm tra mất khoảng 15–30 phút.
   Pipeline: `git push` rồi chờ khoảng 30 giây (theo tab Actions của lab này).
