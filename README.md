# LINE Bot 自動回覆專案

此專案是一個簡單的 LINE Bot，使用 Python語言 自動回覆訊息。它基於 Flask 框架和 LINE Messaging API。

## 專案結構

```
line-bot
├── src
│   ├── app.py               # 應用程式的進入點，初始化 LINE Bot 的 Webhook 並設置路由。
│   ├── handlers
│   │   └── message_handler.py # 包含 MessageHandler 類別，用於處理接收到的訊息。
│   ├── utils
│   │   └── helper.py         # 匯出用於格式化回覆訊息的輔助函式。
├── requirements.txt          # 列出所需的 Python 套件及其版本。
├── .env                      # 儲存環境變數，例如 LINE Channel Access Token 和 Secret。
└── README.md                 # 安裝、配置和運行機器人的文件說明。
```

## 安裝

1. 複製此專案：
   ```
   git clone <repository-url>
   cd line-bot
   ```

2. 建立虛擬環境：
   ```
   python -m venv venv
   source venv/bin/activate  # Windows 使用 `venv\Scripts\activate`
   ```

3. 安裝所需套件：
   ```
   pip install -r requirements.txt
   ```

## 配置

1. 在專案根目錄建立 `.env` 文件，並新增你的 LINE Channel Access Token 和 Channel Secret：
   ```
   CHANNEL_ACCESS_TOKEN=your_channel_access_token
   CHANNEL_SECRET=your_channel_secret
   ```

## 運行機器人

運行以下指令啟動機器人：
```
python src/app.py
```

確保在 LINE Developer Console 中將 Webhook URL 設置為指向此機器人所在的伺服器。

## 使用方式

當機器人運行後，它將監聽收到的訊息，並根據 `message_handler.py` 中定義的邏輯自動回覆。你可以透過修改 `MessageHandler` 類別中的 `handle_message` 方法來自訂回覆行為。