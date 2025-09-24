# 帳戶跨平台聯繫
作為一個多平台機器人，提供多個平台帳號的自動連結是必須的。

## 查詢帳戶跨平台聯繫
## `checkuser` 指令
- 用法：`/checkuser |<用戶名、用戶 ID 或用戶連結>|`
- 用戶 ID 若無指定平台前綴，機器人將嘗試自動偵測，否則默認查詢呼叫指令的平台。
- 用戶 ID 平台前綴：
- - `tg`, `tgx`: Telegram。帶「`x`」的為十六進制。
- - `dc`, `dcx`: Discord。帶「`x`」的為十六進制。
- - `mx`: Matrix。
- 若此指令用於回覆另一條信息，將查詢被回覆訊息之出者。
- 若此指令沒有回覆訊息，亦無於指令後提供參數，則默認為查詢指令呼叫者。

## 手動配置帳戶跨平台聯繫表
帳戶列表的地址可於 `config.json` 中指定（默認為 `users.json`）。各個欄位所需要的格式如下：

- 跨平台用戶標識：字串，作為機器人對用戶的主要標識名稱。
- Telegram 用戶編號：可選 52 位元整數。
- Discord 用戶編號：可選 64 位元整數，**基於平台相容性考慮，必須儲存成由兩個 32 位整數組成的數組**，高位在前低位在後。
- Matrix 用戶 ID：可選字串，必須為 `@<username>:<homeserver>.<tld>` 的完整格式。
- Telegram 用戶名稱：可選字串，作為方便提及用戶的緩存數據。
- Discord 用戶名稱：可選字串，作為方便提及用戶的緩存數據。
- [偽基百科（正體中文）](https://uncyclopedia.hk)用戶名。此項信息受 `user_wiki_info` 群組選項控制。
- [偽基百科（粵語）](https://yue.uncyclopedia.hk)用戶名。此項信息受 `user_wiki_info` 群組選項控制。
- [元偽基](https://uncyclomedia.org)用戶名。此項信息受 `user_wiki_info` 群組選項控制。
- [維基百科](https://www.wikipedia.org)用戶名。此項信息受 `user_wiki_info` 群組選項控制。
- `wiki_remarks` 選項：可選字串，作為只在 `user_wiki_info` 群組選項開啟的群組上顯示的額外帳戶信息。

```json
{
  "users": {
    "<name>": {
      "telegram": 9007199254740991,
      "telegram_username": "<username>",
      "discord": [4294967296, 4294967296],
      "discord_username": "<username>",
      "matrix": "@<username>:<homeserver>.<tld>",
      "uncyc_tw": "<username>",
      "uncyc_yue": "<username>",
      "uncyc_meta": "<username>",
      "wikipedia": "<username>",
      "remarks": "<remarks>",
      "wiki_remarks": "<wiki_remarks>"
    }
  }
}
```

## 自動同步
