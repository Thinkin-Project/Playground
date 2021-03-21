## Endpoint Summary
- GetTags<font color=#00FF00> GET </font>］ /api/tags
- GetTagById<font color=#00FF00> GET </font>］ /api/tags/<font color=#00FF00>\<id\></font>
- Create-Tag<font color=#FF6600> POST </font>］ /api/tags
- Delete-Tag<font color=#FF0000> DELETE </font>］ /api/tags
- Update-Tag<font color=#00FFFF> PUT </font>］ /api/tags


## Tag格式
- GetTags
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles/tags
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        [
            {
                "id":"123",
                "name":"ASP"
                "content":"",
                "metaname":"",
                "slug":"",
            }, {...}, ...
        ]
        ```
        - fail: 400（Bad Request）/ 401（Unauthorized）

- GetTagById
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles/tags/<font color=#00FF00>\<id\></font>
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        {
            "id":"123",
            "name":"ASP"
            "content":"",
            "metaname":"",
            "slug":""
        }
        ```
        - fail: 400（Bad Request）/ 401（Unauthorized）

- Create-Tag
    - method：<font color=#FF6600> POST </font>
    - url：/api/articles/tags
    - input： header- {"MD-Auth":token}
        ```c
        {
            "name":"ASP"
            "content":"",
            "metaname":"",
            "slug":""
        }
        ```
    - output: 
        - success： 201
        - fail： 400（Bad Request）/ 401（Unauthorized）

- Delete-Tag
    - method：<font color=#FF0000> DELETE </font>
    - url：/api/articles/tags
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
        - fail： 400（Bad Request）/ 401（Unauthorized）

- Update-Tag
    - method：<font color=#00FFFF> PUT </font>
    - url：/api/articles/tags
    - input： header- {"MD-Auth":token}
        ```c
        {
            "id"："update-Tag-id"
            "name":"ASP"
            "content":"",
            "metaname":"",
            "slug":""
        }
        ```
    - output: 
        - success： 204
        - fail： 400（Bad Request）/ 401（Unauthorized）