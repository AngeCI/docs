# Emoji 字典
Emoji 字典是一個以假正經角度解釋繪文字釋義的機器人。

## 指令列表
- `/emojilist`: 列出所有字典文件繪文字。
- `/emojidict`: 查詢指定繪文字的釋義，可於指令後附上，或者回覆一個帶有繪文字的信息來查詢。

## 字典格式
字典文件名應在 `config.json` 文件中指定。

```json
{
  "🍇": {
    "codepoint": "1F347",
    "name": "Grapes",
    "shortcode": ["grapes"],
    "description": "提子，提防騙子。"
  },
  ...
}
```
