## Endpoint Summary
- GetRoles［<font color=#00FF00> GET </font>］ /api/account/roles
- GetRoleById［<font color=#00FF00> GET </font>］ /api/account/roles/<font color=#00FF00>\<id\></font>
- Create-Role［<font color=#FF6600> POST </font>］ /api/account/roles
- Delete-Role［<font color=#FF0000> DELETE </font>］ /api/account/roles
- Update-Role［<font color=#00FFFF> PUT </font>］ /api/account/roles

## User Role格式
- GetRoles
    - method：<font color=#00FF00>GET</font>
    - url：/api/account/roles
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        [
            {
                "id":"123",
                "name":"ROLE123"
                "description":""
            }, {...}, ...
        ]
        ```
        - fail: 400 / 401（Unauthorized）

- GetRoleById
    - method：<font color=#00FF00>GET</font>
    - url：/api/account/roles/<font color=#00FF00>\<id\></font>
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        {
            "id":"123",
            "name":"ROLE123"
            "description":""
        }
        ```
        - fail: 400 / 401（Unauthorized）

- Create-Role
    - method：<font color=#FF6600> POST </font>
    - url：/api/account/roles
    - input： header- {"MD-Auth":token}
        ```c
        {
            "name":"ROLE123"
            "description":""
        }
        ```
    - output: 
        - success： 201
        - fail： 400 / 401（Unauthorized）

- Delete-Role
    - method：<font color=#FF0000> DELETE </font>
    - url：/api/account/roles
    - input： header- {"MD-Auth":token}
        ```c
        [
            {
                "id":"ttt123",
            }, 
            {...}, ...
        ]
        ```
    - output: 
        - success： 204（No Content）
        - fail： 400 / 401（Unauthorized）

- Update-Role
    - method：<font color=#00FFFF> PUT </font>
    - url：/api/account/roles
    - input： header- {"MD-Auth":token}
        ```c
        {
            "id":"123",
            "name":"ROLE123"
            "description":""
        }
        ```
    - output: 
        - success： 204
        - fail： 400 / 401（Unauthorized）
