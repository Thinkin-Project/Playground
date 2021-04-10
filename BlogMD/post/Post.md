## Endpoint Summary
- GetArticles<font color=#00FF00> GET </font>］ /api/articles
- GetArticlesById<font color=#00FF00> GET </font>］ /api/articles/<font color=#00FF00>\<id\></font>
- Create-Articles［<font color=#FF6600> POST </font>］ /api/articles
- Delete-Articles［<font color=#FF0000> DELETE </font>］ /api/articles
- Update-Articles［<font color=#00FFFF> PUT </font>］ /api/articles


## 文章格式
- GetArticles
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        [
            {
                "id":"123",
                "tags": [ {"id":"", "name":"", "content":"", "metaname":"", "slug":""}, ...],
                "categories": [ {"id":"", "name":"", "content":"", "metaname":"", "slug":"", "parentid":""}, ...],
                "title":"ttt123",
                "content":"",
                "summary":"",
                "visible":True,
				"published":True,
                "author":{"name":"start"},
                "metatitle": "aaaaa",
                "slug":"",
                "createdat":2021-03-21 10:00:00,
                "updatedat":2021-03-21 10:00:00,
                "publishedat":2021-03-21 10:00:00
            }, {...}, ...
        ]
        ```
        - fail: 400 / 401（Unauthorized）

- GetArticlesById
    - method：<font color=#00FF00>GET</font>
    - url：/api/articles/<font color=#00FF00>\<id\></font>
    - input： header- {"MD-Auth":token}
    - output：
        - success：200, 
        ```c
        {
            "id":"123",
            "tags": [ {"id":"", "name":"", "content":"", "metaname":"", "slug":""}, ...],
            "categories": [ {"id":"", "name":"", "content":"", "metaname":"", "slug":"", "parentid":""}, ...],
            "title":"ttt123",
            "content":"",
            "summary":"",
            "visible":True,
			"published":True,
            "author":{"name":"start"},
            "metatitle": "aaaaa",
            "slug":"",
            "createdat":2021-03-21 10:00:00,
            "updatedat":2021-03-21 10:00:00,
            "publishedat":2021-03-21 10:00:00
        }
        ```
        - fail: 400（Bad Request）/ 401（Unauthorized）

- Create-Article
    - method：<font color=#FF6600> POST </font>
    - url：/api/articles
    - input： header- {"MD-Auth":token}
        ```c
        {
            "title":"ttt123",
            "content":"",
            "summary":"",
            "visible":True,
			"published":True,
            "metatitle": "aaaaa",
            "slug":"",
            "tags": ["tag-id001", "tag-id002", ...],
            "categories": ["category-id001", "category-id002", ...],
        }
        ```
    - output: 
        - success： 201
        - fail： 400 （Bad Request）/ 401（Unauthorized）

- Delete-Article
    - method：<font color=#FF0000> DELETE </font>
    - url：/api/articles
    - input： header- {"MD-Auth":token}
        ```c
        ["article-id001", "article-id002", ...]
        ```
    - output: 
        - success： 204（No Content）
        - fail： 400 / 401（Unauthorized）

- Update-Article
    - method：<font color=#00FFFF> PUT </font>
    - url：/api/articles
    - input： header- {"MD-Auth":token}
        ```c
        {
            "id"："update-article-id"
            "title":"ttt123",
            "content":"",
            "summary":"",
            "visible":True,
			"published":True,
            "metatitle": "aaaaa",
            "slug":"",
            "tags": ["tag-id001", "tag-id002", ...],
            "categories": ["category-id001", "category-id002", ...],
        }
        ```
    - output: 
        - success： 204
        - fail： 400（Bad Request）/ 401（Unauthorized）

