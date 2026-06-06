# MyTranslation — Bản dịch cho Amazing Cultivation Simulator (iOS)

Mod dịch cho game **了不起的修仙模拟器 / Amazing Cultivation Simulator (ACS)** chạy trên **iOS**, nạp trực tiếp qua chức năng **load mod từ link GitHub** trong game (không cần copy file vào thư mục game).

Mod ghi đè gói ngôn ngữ **OfficialEnglish** bằng cách đặt file đúng tên + đúng đường dẫn tương đối, **không sửa file gốc** của game.

## Cách nạp

1. Mở game ACS trên iOS.
2. Vào chức năng **nạp mod từ link GitHub**.
3. Dán URL repo này (ví dụ: `https://github.com/<tài-khoản>/translate`).
4. Bật mod **MyTranslation** trong danh sách mod, khởi động lại nếu game yêu cầu.
5. **Quan trọng:** đặt ngôn ngữ game về **English** — mod ghi đè slot `OfficialEnglish`, nên bản dịch chỉ hiện khi đang dùng ngôn ngữ English.

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

## Ghi chú

- `GameVersion` đặt bằng phiên bản game đang chạy (1.177). Nếu cập nhật game lên bản mới hơn, mod vẫn nạp được; chỉ nâng số này khi đã kiểm tra tương thích.
- Cơ chế hoạt động: game duyệt mọi thư mục con của repo; file/Def trùng tên + trùng đường dẫn tương đối sẽ ghi đè bản gốc theo thứ tự nạp.
