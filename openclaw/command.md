# 徹底殺掉舊程序

openclaw daemon stop 
taskkill /F /IM node.exe

# 使用管理員權限重新安裝

npm install -g openclaw@latest

# 驗證版本與診斷

openclaw --version
openclaw doctor

# 重新啟動服務

openclaw daemon start

# 停止ollama模型

ollama stop qwen2.5:14b