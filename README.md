# Check List
[群組管理]

* 可以成功開啟，呼叫 GetAllGroup.php、GetAllUser.php、GetAllAuth.php
* 刪除群組人員，呼叫 DeleteGroupMember.php
* 刪除群組，呼叫 DeleteGroup.php
* 新增群組，呼叫 NewGroup.php
* 編輯群組
  * 修改名稱，呼叫 EditGroupInfo.php
  * 新增人員，呼叫 AddGroupMember.php
  * 刪除人員，呼叫 DeleteGroupMember.php
  * 新增權限，呼叫 AddGroupAuth.php
  * 刪除權限，呼叫 DeleteGroupAuth.php
  
[使用者管理]

* 可以成功開啟，呼叫 GetAllGroup.php、GetAllUser.php
* 刪除使用者，呼叫 DeleteUser.php
* 新增使用者，呼叫 NewUser.php
* 編輯使用者
  * 修改名稱、密碼，呼叫 EditUserInfo.php
  * 新增群組，呼叫 AddGroupMember.php
  * 刪除群組，呼叫 DeleteGroupMember.php

# 2017-02-15 錯誤記錄

* 查詢群組

  http://114.32.225.116/QueryGroup.php

  沒有回傳 GroupID

* 查詢全部人員、查詢人員

  http://114.32.225.116/GetAllUser.php

  http://114.32.225.116/QueryUser.php

  UserGroup 沒有包含群組ID 
  ```
    "UserGroup": [
        "管理者群組",
        "一般使用者群組",
        "編輯發票群組",
        "編輯日期群組",
        "群組管理群組",
        "使用者管理群組",
        "訂單管理群組"
    ]
  ```

  我要這種格式
  ```
    "UserGroup": [
        {
            "GroupID": "xx",
            "GroupName": "管理者群組"
        }, {
            "GroupID": "xx",
            "GroupName": "一般使用者群組"
        }
    ]
  ```

* 刪除人員

  http://114.32.225.116/DeleteUser.php

  UserID:41

  `{"code":300,"result":"操作失敗","description":"查詢使用者時: Unknown column 'xxxx' in 'where clause'"}`

* 新增人員

  http://114.32.225.116/NewUser.php

  沒有回傳 UserID

  NewUserName:123222

  NewUserPassword:123

  `{"code":200,"result":"操作成功","description":"使用者: '123222'，新增成功"}`
