PEM Cracker Lab - Bản build tĩnh sẵn sàng deploy
================================================

Đây là toàn bộ file tĩnh đã build sẵn. Chỉ cần upload toàn bộ
nội dung thư mục này lên bất kỳ host tĩnh nào (Netlify, Vercel,
Cloudflare Pages, GitHub Pages, Nginx, Apache, S3...).

Cấu hình:
- Đặt index.html làm trang gốc.
- Cấu hình SPA fallback: mọi đường dẫn không tìm thấy file -> trả về /index.html
  + Nginx: try_files $uri $uri/ /index.html;
  + Apache: dùng .htaccess với RewriteRule . /index.html [L]
  + Netlify: tạo file _redirects với:  /*  /index.html  200
  + Vercel: tự nhận dạng SPA, không cần cấu hình thêm.

Toàn bộ ứng dụng chạy 100% phía client - không cần backend.
