---
description: "用户管理的相关 API，利用它们你可以✍出例如自动管理用户（谁到期了直接自动暂停和删除）的功能，大大解放你的双手\U0001F44D。"
---

# API - User - 用户管理

{% hint style="info" %}
使用这些 API 之前请先检查你的 API Key 是否拥有此权限（管理）。
{% endhint %}

{% page-ref page="../shi-yong-api/api-tou-bu.md" %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/users" %}
{% api-method-summary %}
获取用户列表
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "list",
  "data": [
    {
      "object": "user",
      "attributes": {
        "id": 1,
        "external_id": null,
        "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
        "username": "codeco",
        "email": "codeco@file.properties",
        "first_name": "Rihan",
        "last_name": "Arfan",
        "language": "en",
        "root_admin": true,
        // 是否启用二次验证
        "2fa": false,
        "created_at": "2018-03-18T15:15:17+00:00",
        "updated_at": "2018-10-16T21:51:21+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 4,
        "external_id": null,
        "uuid": "f253663c-5a45-43a8-b280-3ea3c752b931",
        "username": "wardledeboss",
        "email": "wardle315@gmail.com",
        "first_name": "Harvey",
        "last_name": "Wardle",
        "language": "en",
        "root_admin": false,
        "2fa": false,
        "created_at": "2018-09-29T17:59:45+00:00",
        "updated_at": "2018-10-02T18:59:03+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 5,
        "external_id": null,
        "uuid": "0d8da9a5-6ccd-4b57-9786-70a97a1a55e7",
        "username": "matthewp",
        "email": "me@matthewp.io",
        "first_name": "Matthew",
        "last_name": "Penner",
        "language": "en",
        "root_admin": true,
        "2fa": false,
        "created_at": "2018-09-29T22:39:05+00:00",
        "updated_at": "2018-09-29T22:39:27+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 6,
        "external_id": null,
        "uuid": "d006fe91-3c64-4b0c-81d1-718af2cc384e",
        "username": "rihan554rnk",
        "email": "rihan554@gmail.com",
        "first_name": "Server",
        "last_name": "Subuser",
        "language": "en",
        "root_admin": false,
        "2fa": false,
        "created_at": "2018-10-02T21:26:18+00:00",
        "updated_at": "2018-10-02T21:26:18+00:00"
      }
    }
  ],
  "meta": {
    "pagination": {
      "total": 4,
      "count": 4,
      "per_page": 50,
      "current_page": 1,
      "total_pages": 1,
      "links": []
    }
  }
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/users/<user-id>" %}
{% api-method-summary %}
获取特定用户资料
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="user-id" type="string" required=false %}
用户 ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": null,
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Rihan",
    "last_name": "Arfan",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-10-16T21:51:21+00:00"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/users/external/<external-id>" %}
{% api-method-summary %}
从 External ID 获得用户信息
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="external-id" type="string" required=false %}
用户 external id
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": "1",
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Rihan",
    "last_name": "Arfan",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-10-16T21:51:21+00:00"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pterodactyl.app" path="/api/application/users" %}
{% api-method-summary %}
创建用户
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="language" type="string" required=false %}
用户语言，需要**可用**的语言
{% endapi-method-parameter %}

{% api-method-parameter name="root\_admin" type="boolean" required=false %}
是否是全局管理员
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=false %}
sometimes\|nullable\|string
{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}
required\|string\|between:1,255
{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}
required\|string\|between:1,255
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
required\|email\|unique:users,email
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
required\|between:1,255\|unique:users,username
{% endapi-method-parameter %}

{% api-method-parameter name="external\_id" type="string" required=false %}
sometimes\|nullable\|string\|max:255\|unique:users,external\_id
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "user",
  "attributes": {
    "id": 7,
    "external_id": "example_ext_id",
    "uuid": "68b23b39-f172-4cd3-ba4a-ef5761c01374",
    "username": "example",
    "email": "example@example.com",
    "first_name": "John",
    "last_name": "Doe",
    "language": "en",
    "root_admin": false,
    "2fa": false,
    "created_at": "2018-11-20T03:05:23+00:00",
    "updated_at": "2018-11-20T03:05:23+00:00"
  },
  "meta": {
    "resource": "https://pterodactyl.app/api/application/users/7"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

body 为 JSON，例子：

```javascript
 {
      "external_id": "example_ext_id",
      "username": "example",
      "email": "example@example.com",
      "first_name": "John",
      "last_name": "Doe",
      "password": "cat",
      "root_admin": false,
      "language": "en"
  }
```



{% api-method method="patch" host="https://pterodactyl.app" path="/api/application/users/<user-id>" %}
{% api-method-summary %}
编辑用户
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="language" type="string" required=false %}
用户语言，需要**可用**的语言
{% endapi-method-parameter %}

{% api-method-parameter name="root\_admin" type="boolean" required=false %}
是否是全局管理员
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=false %}
sometimes\|nullable\|string
{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}
required\|string\|between:1,255
{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}
required\|string\|between:1,255
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
required\|email\|unique:users,email
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
required\|between:1,255\|unique:users,username
{% endapi-method-parameter %}

{% api-method-parameter name="external\_id" type="string" required=false %}
sometimes\|nullable\|string\|max:255\|unique:users,external\_id
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": "codeco",
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Updated",
    "last_name": "User",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-12-17T19:34:37+00:00"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

请求 body 的例子：

```javascript
{
      "external_id": "codeco",
      "username": "codeco",
      "email": "codeco@file.properties",
      "first_name": "Updated",
      "last_name": "User",
      "password": "betterPassword",
      "root_admin": true,
      "language": "en"
  }
```

{% api-method method="delete" host="https://pterodactyl.app" path="/api/application/users/<user-id>" %}
{% api-method-summary %}
删除用户
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
成功的话，返回空。
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

