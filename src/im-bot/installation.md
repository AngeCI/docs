# 機器人配置指南

首先，開啟用以運作機器人之伺服器的命令列，輸入以下指令下載機器人程式：
```sh
git clone https://github.com/AngeCI/im-bot.git
```

安裝依賴：
```sh
cd im-bot
npm install
```

然後輸入以下指令開始運行機器人：

```sh
node main.js > <stdout> 2> <stderr>
```

當中 `<stdout>` 是普通日誌檔案的路徑、`<stderr>` 是錯誤日誌檔案的路徑。若不提供日誌路徑，機器人就不會保留日誌。
