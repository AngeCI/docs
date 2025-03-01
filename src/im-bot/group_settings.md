# 群組設定
群組設定位於 `group_info_file` 通用選項所指向的文件中（默認為 `groups.json`）。

- Telegram 用戶編號：可選 52 位元整數。
- Discord 群組編號：可選 64 位元整數，**基於平台相容性考慮，必須儲存成由兩個 32 位整數組成的數組**，高位在前低位在後。
- Matrix 群組標識：可選字串，必須為 `!<group_id>:<homeserver>.<tld>` 的完整格式。
- 群組語系：字串。
- 指令類別選項：可選布爾值，指令類別的名稱可在[此處](README.md#指令列表)找到。
- `user_wiki_info` 選項：可選布爾值，若此項開啟，則[查詢帳號資訊](account.md)時會輸出共筆網站相關的額外信息。
- `throw_error` 選項：可選布爾值，決定是否向群組推送機器人的錯誤信息。

```json
{
  "Group 1": {
    "telegram": 0,
    "discord" [0, 0],
    "matrix": "!<group_id>:<homeserver>.<tld>",
    "lang": "zh-TW",
    "general": true,
    "ping": true,
    "chat_history": true,
    "pin": true,
    "checkuser": true,
    "user_wiki_info": true,
    "random_sticker": true,
    "sticker_search": true,
    "spam": true,
    "emoji_dict": true,
    "bible": true,
    "5m": true,
    "ch": true,
    "xq": true,
    "raven": true,
    "debug_commands": true,
    "throw_error": true
  }
}
```
