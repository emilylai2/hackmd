# 安裝
```bash
sudo apt update
sudo apt install git -y
git --version
```
- 設定使用者名稱與電子郵件
```bash
git config --global user.name "你的名字"
git config --global user.email "你的郵件"
git config --global --list
```

- 初始化Git repository
```bash
mkdir my_project
cd my_project
git init  # 初始化 Git 儲存庫
```

- 連接遠端儲存庫
```bash
git remote add origin <遠端儲存庫 URL>
#範例
git remote add origin https://github.com/你的帳號(emilylai2)/你的專案(ansible).git
```
- 查看是否成功連接
```bash!
git remote -v
```

## 添加檔案到Git(本地)
- 當下資料夾全部內容添加
```bash!
git add .
```
- 只添加單個檔案
```bash!
git add file_name.txt
```
- 提交變更
```bash!
git commit -m "這是提交訊息"
```
## Push 到Git
- 如果這是第一次推送，需要設定`main`分支:
```bash!
git branch -M main  # 設定 main 為預設分支
```
- 推送
```bash!
git push -u origin main
```
- 之後的推送只需要
```bash=
git push
```

##  如果團隊成員有更新遠端儲存庫，先同步最新版本
```bash=
git pull origin main

```
## 建立與切換分支
- 開發新功能建議使用分支
```bash=
git branch feature-branch  # 建立新分支
git checkout feature-branch  # 切換到新分支
```
- 直接建立並切換
```bash=
git checkout -b feature-branch
```
- 切換回main
```bash=
git checkout main
```
## 合併分支
- 當新功能開發完成，可以合併回`main`
```bash!
git checkout main
git merge feature-branch
```
- 然後刪除分支
```bash!
git branch -d feature-branch
```
## 檢查Git狀態與記錄
```bash
git status
```
- 查看提交記錄
```bash
git log --oneline --graph --all
```
## 回上一個版本
```bash=
git reset --hard HEAD~1
```
- 回到特定版本
```bash=
git reset --hard <commit-hash>
```

## 使用流程

- 先把ssh public key 加到Git 金鑰倉庫
```css
  +----------------------+
  |  Git 使用流程         |
  +----------------------+
        |
        v
  +---------------------+
  |  1. 初始化 Git 儲存庫 |
  +---------------------+
        |-- git init 
        v
  +-------------------+
  |  2. 設定使用者資訊  |
  +-------------------+
        |-- git config user.name
        |-- git config user.email
        v
  +------------------+
  |  3. 連結遠端倉庫  |
  +------------------+
        |-- git remote add origin
        v
  +------------------+
  |  4. 建立或修改檔案 |
  +------------------+
        |-- git add .
        v
  +------------------+
  |  5. 提交變更      |
  +------------------+
        |-- git commit -m '註記訊息'
        v
  +------------------+
  |  6. 推送至遠端    |
  +------------------+
        |-- git push origin main
        v
  +------------------+
  |  7. 建立新分支    |
  +------------------+
        |-- git checkout -b branch
        v
  +------------------+
  |  8. 進行開發與提交 |
  +------------------+
        |-- git add .
        |-- git commit -m '功能'
        v
  +------------------+
  |  9. 合併至 main  |
  +------------------+
        |-- git checkout main
        |-- git merge branch
        v
  +------------------+
  |  10. 刪除分支    |
  +------------------+
        |-- git branch -d branch
        v
  +------------------+
  |  11. 完成開發流程 |
  +------------------+
  ";
} 
```

 ## 刪除repository
 找到設定-general
 ![image](https://hackmd.io/_uploads/H12VyBKnJg.png)
拉到最下面的`Danger Zone`-->change visibility->change to private
![image](https://hackmd.io/_uploads/HyiK1SYhye.png)
- make private

![image](https://hackmd.io/_uploads/BJ3s1rt3kg.png)

## 搜尋要下載的repository
右上角的`search` 例`containerd`
找到想要的repository及release版本
![image](https://hackmd.io/_uploads/BksPxSF2Je.png)
- releases右邊選擇適合的版本
![image](https://hackmd.io/_uploads/rkr--BtnJg.png)
- Assets-找到適合的硬體版本
![image](https://hackmd.io/_uploads/r1t-zHY2kx.png)
複製連結或者直接下載