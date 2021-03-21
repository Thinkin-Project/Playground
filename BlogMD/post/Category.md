## Endpoint Summary
- GetCategories<font color=#00FF00> GET </font>］ /api/categories
- GetCategoryById<font color=#00FF00> GET </font>］ /api/categories/<font color=#00FF00>\<id\></font>
- Create-Category<font color=#FF6600> POST </font>］ /api/categories
- Delete-Category<font color=#FF0000> DELETE </font>］ /api/categories
- Update-Category<font color=#00FFFF> PUT </font>］ /api/categories


## Category格式
- GetCategories
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles/categories
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
        - fail: 400 / 401（Unauthorized）

- GetCategoryById
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles/categories/<font color=#00FF00>\<id\></font>
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
        - fail: 400 / 401（Unauthorized）

- Create-Category
    - method：<font color=#FF6600> POST </font>
    - url：/api/articles/categories
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

- Delete-Category
    - method：<font color=#FF0000> DELETE </font>
    - url：/api/articles/categories
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

- Update-Category
    - method：<font color=#00FFFF> PUT </font>
    - url：/api/articles/categories
    - input： header- {"MD-Auth":token}
        ```c
        {
            "id"："update-category-id"
            "name":"ASP"
            "content":"",
            "metaname":"",
            "slug":""
        }
        ```
    - output: 
        - success： 204
        - fail： 400（Bad Request）/ 401（Unauthorized）

