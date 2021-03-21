## Endpoint Summary
- Login［<font color=#FF6600> POST </font>］ /api/account/login
- Register［<font color=#FF6600> POST </font>］ /api/account/register
- GetUsers［<font color=#00FF00> GET </font>］ /api/account/users
- GetUserByUsername［<font color=#00FF00> GET </font>］ /api/account/users/<font color=#00FF00>\<username\></font>

## 帳戶格式
- Login
    - method：<font color=#FF6600> POST </font>
    - url：/api/account/login
    - input：
        ``` c
        {
            "username":"stark", 
            "password":"ppp123"
        }
        ```
    - output：
        - success：200, 
            ```c
            {
                "username":"stark", 
                "token":"ttt123123"
            }
            ```
        - fail：400

- Register:
    - method：<font color=#FF6600> POST </font>
    - url：/api/account/register
    - input：
        ```c
        {
            "username":"stark", 
            "password":"ppp123", 
            "email":"abc123@gmail.com", 
            "gender":"M", 
            "phone":"0912345678", 
            "firstname":"Lin", 
            "lastname":"stark"
            "photo":"photo-url",
            "biography":"hello my name is blalbalbla"
        }
        ```
    - output: 
        - success：200
        - fail：400

- GetUsers
    - method：<font color=#00FF00>GET</font>
    - url：/api/account/users
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        [
            {
                "id":"123",
                "username":"stark",
                "profile": [ 
                    {
                        "id":"", 
                        "firstname":"", 
                        "lastname":"", 
                        "email":"", 
                        "phone":"", 
                        "gender":"",
                        "biography":"hello my name is blalbalbla",
                        "createdat":2021-03-21 10:00:00,
                        "updatedat":2021-03-21 10:00:00
                    }, ...
                ],
                "role":[ 
                    {
                        "id":"", 
                        "name":"", 
                        "description":"", 
                        "createdat":2021-03-21 10:00:00,
                        "updatedat":2021-03-21 10:00:00
                    }, ...
                ],
                "createdat":2021-03-21 10:00:00,
                "updatedat":2021-03-21 10:00:00
            }, {...}, ...
        ]
        ```
        - fail: 400 / 401（Unauthorized）

- GetUserByUsername
    - method：<font color=#00FF00>GET</font>
    - url：/api/account/users/<font color=#00FF00>\<username\></font>
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        {
            "id":"123",
            "username":"stark",
            "profile": [ 
                {
                    "id":"", 
                    "firstname":"", 
                    "lastname":"", 
                    "email":"", 
                    "phone":"", 
                    "gender":"",
                    "biography":"hello my name is blalbalbla",
                    "createdat":2021-03-21 10:00:00,
                    "updatedat":2021-03-21 10:00:00
                }, ...
            ],
            "role":[ 
                {
                    "id":"", 
                    "name":"", 
                    "description":"", 
                    "createdat":2021-03-21 10:00:00,
                    "updatedat":2021-03-21 10:00:00
                }, ...
            ],
            "createdat":2021-03-21 10:00:00,
            "updatedat":2021-03-21 10:00:00
        }
        ```
        - fail: 400 （Bad Request）/ 401（Unauthorized）
