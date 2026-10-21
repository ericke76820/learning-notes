# 將專案上傳至github指令步驟:

# 初始化 Git 倉庫
git init

# 將所有檔案加入準備區/更新專案 (別忘了那個點 .)
git add .
git add foldername/filename.dataformal

# 提交更新紀錄
git commit -m "Initial commit: My Streamlit Portfolio"

# 建立連接 (weblink)
git remote add origin https://github.com/帳戶名稱/專案名.git

# 重新命名分支為 main
git branch -M main

# 正式推送檔案
git push -u origin main

# 會列出含有指定文字的檔名 
git grep -l -F Select-Object -- src/main/java(檔名) | Select-Object -First 10(只取前十筆)
