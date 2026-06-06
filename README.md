# MyTranslation — Bản dịch cho Amazing Cultivation Simulator (iOS)

Mod dịch cho game **了不起的修仙模拟器 / Amazing Cultivation Simulator (ACS)** chạy trên **iOS**, nạp trực tiếp qua chức năng **load mod từ link GitHub** trong game (không cần copy file vào thư mục game).

Mod ghi đè gói ngôn ngữ **OfficialEnglish** bằng cách đặt file đúng tên + đúng đường dẫn tương đối, **không sửa file gốc** của game.

## Cách nạp

1. Mở game ACS trên iOS → vào **MOD store**.
2. Dùng nút **nạp mod từ địa chỉ git** (góc trên bên phải MOD store).
3. Dán URL repo này: `https://github.com/kudoshinichisec/translate`
4. Bật mod **MyTranslation** trong danh sách mod, khởi động lại nếu game yêu cầu.
5. **Quan trọng:** đặt ngôn ngữ game về **English** — mod ghi đè slot `OfficialEnglish`, nên bản dịch chỉ hiện khi đang dùng ngôn ngữ English.

> ⚠️ **Bắt buộc phải có GitHub Release.** Loader iOS không đọc thẳng file trên nhánh — nó gọi `releases/latest` rồi tải bản zip nguồn của release đó. Repo không có release sẽ báo lỗi **"load release info failed"**.

## Cấu trúc

```
Info.json                          # khai báo mod (Name, GameVersion, Author...)
Language/
└── OfficialEnglish/               # ghi đè gói ngôn ngữ English của game
    ├── Settings/                  # phần lớn nội dung dịch (Def, UI, item, story...)
    ├── SL/
    ├── CodeDictionary.txt
    ├── MapStoryDictionary.txt
    └── UIText.xml
```

## Thông tin mod

| Trường | Giá trị |
|--------|---------|
| Name | MyTranslation |
| GameVersion | 1.177 |
| Version | 1.0 |
| Author | kudo |

## Cập nhật / phát hành bản mới

Loader đọc **bản Release mới nhất**, nên mỗi lần sửa bản dịch phải tạo Release mới:

```bash
# 1) Sửa file trong Language/OfficialEnglish/...
git add -A
git commit -m "update: ..."
git push

# 2) Tạo Release mới (tag tăng dần, vd 1.1) — đây là bước game thực sự đọc
gh release create 1.1 --target main --title "MyTranslation 1.1" --notes "..."
```

Trong game tải lại link là có bản mới (có thể cần xóa cache mod cũ).

## Ghi chú

- `GameVersion` đặt bằng phiên bản game đang chạy (1.177). Nếu cập nhật game lên bản mới hơn, mod vẫn nạp được; chỉ nâng số này khi đã kiểm tra tương thích.
- Cơ chế hoạt động: loader tải zip nguồn của release rồi duyệt mọi thư mục con; file/Def trùng tên + trùng đường dẫn tương đối sẽ ghi đè bản gốc theo thứ tự nạp.
- Tham khảo chuẩn chính thức: [`GSQStudio/acs1_example_mod`](https://github.com/GSQStudio/acs1_example_mod) (mod mẫu) và [`GSQStudio/acs1_mods`](https://github.com/GSQStudio/acs1_mods) (cửa hàng mod iOS chính thức).
