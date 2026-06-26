# Caption Translator (Gemini Live) — Bản phát hành nội bộ

Extension **dịch realtime** phụ đề/âm thanh cuộc họp (Teams / Meet / Zoom…) qua Google **Gemini Live**:
nghe **micro** hoặc **âm thanh hệ thống** → **chép lời + dịch + đọc to (TTS) + tóm tắt**.
Mỗi người dùng **tự nhập Gemini API key** của mình (gói cài KHÔNG chứa khóa bí mật).

> Repo này chỉ để **phát hành / host gói cài**. Cài bằng **chính sách force-install** cho **Edge & Chrome** trên Windows (máy được quản lý hoặc có quyền Admin).

- **Extension ID:** `anflamknalpoacapofekflmndbkblkjl`
- **Trình duyệt:** Microsoft Edge hoặc Google Chrome (Windows)

---

## 🟢 Cài đặt (cho người dùng)

1. Vào mục **Releases → `dist` → Assets**, tải file **`apply-policy.bat`**.
2. **Bấm-đúp** file → hộp thoại UAC hiện ra → chọn **Yes** (file tự xin quyền Admin).
   - Nếu Windows SmartScreen cảnh báo: bấm **More info → Run anyway**.
3. **Khởi động lại** Edge / Chrome hoàn toàn.
4. Mở `edge://extensions` (hoặc `chrome://extensions`) → thấy **Caption Translator** kèm nhãn
   *"Installed by your organization"* ⇒ đã cài xong.

> Yêu cầu: có **quyền Admin** trên máy + máy **vào được github.com**.
> Nếu máy bị IT khóa (không có Admin) → nhờ IT triển khai qua **GPO/Intune** (mục bên dưới).

## ▶️ Cách dùng
1. Bấm icon extension → mở **Side Panel**.
2. Bấm ⚙️ → dán **Gemini API key** (lấy ở https://aistudio.google.com/apikey).
3. Chọn nguồn (🎤 Micro / 🔊 Âm thanh) → bấm **Bắt đầu**.

## 🗑️ Gỡ cài đặt
Tải & chạy **`remove-policy.bat`** (tự xin Admin) → khởi động lại trình duyệt.

---

## 🏢 Dành cho IT — triển khai hàng loạt (GPO / Intune)
Thay vì chạy `.bat` từng máy, đẩy chính sách:
- **Edge** (ADMX): *Configure the list of force-installed extensions*
- **Chrome** (ADMX): *Configure the list of force-installed apps and extensions*
- **Giá trị thêm vào:**
  ```
  anflamknalpoacapofekflmndbkblkjl;https://github.com/<OWNER>/<REPO>/releases/download/dist/update.xml
  ```

## 🔧 Dành cho người bảo trì — cập nhật phiên bản
1. Tăng `version` trong source `manifest.json`; build lại `extension.crx` **bằng đúng khóa `.pem`** (giữ nguyên ID).
2. Tăng `version` trong `update.xml` cho khớp.
3. Vào Release **`dist`** → **Edit** → xóa asset cũ → upload lại **`extension.crx` + `update.xml`** (và `apply-policy.bat`/`remove-policy.bat` nếu đổi).
4. Máy người dùng **tự cập nhật** (vài giờ hoặc mở lại trình duyệt). **URL & policy không đổi.**

---
*Lưu ý: file CRX công khai là bình thường — không chứa bí mật; quyền dịch dùng API key cá nhân của từng người.*
