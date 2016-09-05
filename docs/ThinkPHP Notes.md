# ThinkPHP Notes
## Key Points
- ThinkPHP 內建的方法；
- Role Based Access Control for ThinkPHP（要求：精通）；
- `D()` 和 `M()`；
- Model；

## 筆錄
### Methods and Functions
#### Database operations
- C: `add()`
- U: `save()`
- R: `select()`
- D: `delete()`

#### MVC Related
- `Controller()->success()`
- `Controller()->error()`
- `Controller()->asign()`
- `Controller()->display()`
- `D() // 實例化模型類物件`
- `M() // 實例化不需要靜態定義的模型類物件`
- `M()->data()`
- `I() // 用於輸入變數，good for debug`
- `U('Module/Controller/method') // bulid the URL`
- `C() // configuration`
- `F() // 快速緩存 DATA_PATH`
- `p()`
- `halt()`
- `_initialize() // 方法構造`
- `A() // 實例化 controller 並返回物件`
- `S() // 緩存管理`
- `L()`
- `R() // 遠端呼用`
- `T() // 取得模板文件名稱`
- `G() // runtime 統計`
- `dump() // 變量調試`
- `W()`
- `theme()`
- `fetch()`
- `show()`

### URL 預設參名
- module: m
- controller: c
- action: a

### 3-rd Party Library
`Library/ORG/Util/Image` 裏的 `buildImageVerify`

### Configuration
Database connection information could be saved in this file.

可透過配置引入外部函式。
``` PHP
array(
	'DEFAULT_FILTER' => 'htmlspecialchars', // for removing special chars, reference for ThinkPHP 3.1
	'APP_GROUP_LIST',
	'DEFAULT_GROUP',
	'TMPL_VAR_IDENTIFY' => 'array', // template related: using dot
	'TMPL_FILE_DEPR' => '_',
);
```

### Special Notes
查詢資料：
``` PHP
$cond = new stdClass();
$cond->name = 'what';
$cond->status = 1;
$cond->_logic = 'AND';
M('schema')->where($cond)->select();
```

#### 查詢形式
- string
- array
- object

#### 查詢方法
- 表達式查詢
- 快捷查詢
- 區間查詢
- 組合查詢
- 動態查詢

另：
``` PHP
$Model = new Model();
$Model->query(); // as a operation of READING (while using distributed database with IO separation)
$Model->execute(); // as a operation of WRITING
```

應用模式 - 模組 - 入口

3.1.3 | 3.2
----- | ---
獨立分組 | Module（模組）
模塊 | Controller

Non-standard **O**bject **R**elational **M**apping Model of **Active Record**

f   | f(x)
--- | ----
table | class
record | object

#### Debug Related
``` PHP
E('Error', 23); // 扔出一個異常，並編號 23，並中斷，同下：
throw new \Think\Exception('Error', 23);

M()->getLastSql(); // 3.2 版本中等價於：
M()->_sql();

// CURD 異常檢查
M()->getDbError();
```

#### 安全
資料過濾可用 `stripslashes`，`htmlentities`，`htmlspecialchars`，`strip_tags` 諸函式。

傳至 model 前可加上鏈式作業：`M()->filter()` 作過濾，同理，可用 `M()->field()` 作限定資料內容

#### 緩存
資料查詢緩存：
`M()->chche(true)`

####
Template:
解析物件或 array 多數情況可用 `.`，物件可專用 `:` 解析。
