# 開始
`git clone` OSAdmin 原始碼到一個本機目錄

然後在本機另一目錄 `git init` 一個新的 repo

## 以下對新 repo 作業
拖入原先 `git clone` 到本機的 repo 的 master

### 設置遠程 repo
如有需要則設置好然後 `git push`

建立新 branch config, 將配置變更好，並 commit

* `uploads/include/config/config.inc.php`
* `sql/osadmin.sql`

具體變更有：

* 訪問位址
* 資料庫 account 設定
* 資料庫 prefix 設定
* 替換 `sql/osadmin.sql` 中的 prefix

### 建立開發用的 branch
自 master 建立新 branch dev `git checkout -b dev`

以下對新 repo 的 dev 作業

# 再度（／二次）開發
待續……

# 部署
有需要的話，將 `include/complied` 目錄寫入權限授予調用 php 模組的程式（如 `httpd`）

## 預設使用者
* admin:123456
* demo:123456
