# IM 群組聊天機器人
＜正式名稱待定＞是一個由 AngeCI 所製作的多用途機器人。目前（計劃）支持部署於以下平台：Telegram、Discord、Matrix。此機器人之源碼可於[此處](https://github.com/AngeCI/im-bot)找到。

本機器人目前支援（或計劃支援）的功能如下，讀者可點擊下表之連結以查看該功能的詳細說明。請注意有部份功能可能會在一部份群組被禁用。

- [配置指南](installation.md)
- [API 查詢](api.md)
- [查詢帳戶跨平台聯繫](account.md)
- [群組設置](group_settings.md)
- [群組驗證機制](group_auth.md)
- [聊天記錄搜索](chat_history.md)
- [DM 轉發](#dm-轉發)
- [貼圖搜索](sticker_seacrh.md)
- [發送隨機貼圖](random_sticker.md)
- [`/spam` 指令](spam.md)
- [Emoji 字典](emoji_dict.md)
- [聖經查詢](bible.md)
- [五子棋](gomoku.md)（目前不支持禁手）
- [國際象棋](chess.md)
- [中國象棋](chinese_chess.md)
- [漢語拼音、注音、Raven 碼轉換](raven.md)
- ~~置頂消息同步~~
- ||可能還有一些隱藏的除錯指令||

## 指令列表
- `general` 類：`/start`, `/help`
- `ping` 類：`/ping`
- `chat_history` 類：`/search`
- `pin` 類：`/pin`
- `checkuser` 類：`/checkuser`
- `random_sticker` 類：`/sticker`, `/sticker_stat`
- `sticker_search` 類：`/sticker_search`, `/sticker_stat`
- `spam` 類：`/spam`
- `emoji_dict` 類：`/emojilist`, `/emojidict`
- `bible` 類：`/search_bible`, `/info_bible`
- `5m` 類：待定<!-- `/create5m`, `/join5m`, `next5m`, `/pass5m`, `/undo5m`, `/resend5m`, `/hurry_up5m`, `/abandon5m` -->
- `ch` 類：待定<!-- `/createch`, `/joinch`, `nextch`, `/passch`, `/undoch`, `/resendch`, `/hurry_upch`, `/abandonch` -->
- `xq` 類：待定<!-- `/createxq`, `/joinxq`, `nextxq`, `/passxq`, `/undoxq`, `/resendxq`, `/hurry_upxq`, `/abandonxq` -->
- `raven` 類：`/pinyin`, `/pinyindc`, `/zhuyindc`
- `debug_commands` 類：`/echo`, `/getfileid`, `/flag`, `/sendtext`, `/sendsticker`, `/forward`, `/forward2`

## `/start` 指令
目前只支持對 `/start` 指令回應固定字串信息。訊息內容可在 `config.json` 文件中定義。

如果字串不存在或者為空字串，那麼機器人就不會響應 `/start` 指令。

## `/help` 指令
輸出幫助訊息，幫助訊息內容可在 `config.json` 文件中定義。

## `/ping` 指令
用以檢測消息橋是否正常運作。為了防止重覆推送消息（特別是 Telegram），某些功能可能會需要一直 ping 橋。

## DM 轉發

## 配置指南
`config.json` 文件格式：

```json
{
  "bot_tokens": {
    "telegram": "<TELEGRAM_BOT_TOKEN>",
    "discord": "<DISCORD_BOT_TOKEN>",
    "matrix": "<MATRIX_BOT_TOKEN>"
  },
  "global_switch": {
    "general": true,
    "ping": true,
    "chat_history": true,
    "pin": true,
    "checkuser": true,
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
  },
  "language_list": ["en", "zh-TW", "zh-CN"],
  "chat_history_directory": "history",
  "account_info_file": "users.json",
  "group_info_file": "groups.json",
  "sticker_file": "stickers.json",
  "sticker_index_file": "stdb.json",
  "spam_config_file": "spam_config.json",
  "emoji_dict_file": "emoji_dict.json",
  "bible_file": "bible.json",
  "tg_start_msg": ["Start command received."],
  "tg_help_msg": [
    "Currently supported commands: /start, /help, /sticker, /sticker_stat, /getfileid",
    "In order to make users feel better, debug commands are neither registered on Telegram nor show here.",
    "/start 內置起動按鈕。\n/help 輸出幫助。\n/echo 重複信息。\n/flag 輸入國家地區代碼，輸出旗幟，稍後將實作自動修正功能。\n/sendtext 發送文字信息，目前只支持純文字。\n/sendsticker 發送貼圖。 \n/forward 轉發信息。\n/forward2 轉發信息，命令格式跟 forward 有點不同。\n/pinyin 輸出漢語拼音，注意多音字可能無法正確判斷。\n/pinyindc 拼音解碼。（使用本機器人取得編碼）\n/zhuyindc 注音輸入法解碼。\n本機器人有隱藏指令，請慎用。\n"
  ],
  "emoji_dict_template": "${emoji}\n*U\\+${codepoint} “${name}”*\nShortcode: ${shortcode}\n\n${description}"
}
```

## 手動發送訊息指南
### 多平台

### 單平台
#### Telegram
#### Discord
#### Matrix
