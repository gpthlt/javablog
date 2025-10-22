# Hướng dẫn deploy Hugo lên GitHub Pages

## 1. Tạo repository trên GitHub
- Tạo repo mới, ví dụ: `javablog`.

## 2. Khởi tạo dự án Hugo trên máy
- Chạy lệnh:
  ```cmd
  hugo new site javablog
  ```
- Thêm theme, chỉnh sửa nội dung theo ý muốn.

## 3. Thêm workflow deploy lên GitHub Pages
- Tạo file `.github/workflows/deploy.yml` với nội dung như mẫu workflow.

## 4. Đẩy code lên GitHub
- Khởi tạo git, thêm remote:
  ```cmd
  git init
  git remote add origin https://github.com/<username>/javablog.git
  ```
- Thêm, commit và push code lên nhánh `main`:
  ```cmd
  git add .
  git commit -m "init"
  git branch -m master main
  git push -u origin main
  ```

## 5. Cấu hình GitHub Pages
- Vào repo trên GitHub → "Settings" → "Pages".
- Chọn "Source" là "GitHub Actions".

## 6. Kiểm tra workflow
- Vào tab "Actions" để kiểm tra workflow có chạy thành công không.
(nếu build hoặc deploy fail thì chọn Deployments ở left sibar trang action để build lại )

## 7. Truy cập website
- Sau khi deploy thành công, truy cập:
  ```
  https://<username>.github.io/javablog/
  ```

---

**Lưu ý:**
- Hugo chỉ build site tĩnh, không có backend.
- Mỗi lần cập nhật nội dung, chỉ cần push lên nhánh `main`, workflow sẽ tự động deploy lại.

abctesteta