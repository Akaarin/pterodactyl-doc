# API - Server - 面板服务器管理

{% hint style="info" %}
使用这些 API 之前请先检查你的 API Key 是否拥有此权限（管理）。

**请注意这不是用来管理自己的面板服的，是服务商的服务器管理接口**。如有需要请使用 Client API 用户端接口。
{% endhint %}

{% page-ref page="../shi-yong-api/api-tou-bu.md" %}

{% page-ref page="api-client-yong-hu-duan.md" %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/servers" %}
{% api-method-summary %}
Get all servers
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
      "object": "server",
      "attributes": {
        "id": 2,
        "external_id": null,
        "uuid": "47a7052b-f07e-4845-989d-e876e30960f4",
        "identifier": "47a7052b",
        "name": "Eat Cows",
        "description": "",
        "suspended": false,
        "limits": {
          "memory": 2048,
          "swap": -1,
          "disk": 10000,
          "io": 500,
          "cpu": 300
        },
        "feature_limits": {
          "databases": 10,
          "allocations": 0
        },
        "user": 1,
        "node": 2,
        "allocation": 3,
        "nest": 1,
        "egg": 4,
        "pack": null,
        "container": {
          "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
          "image": "quay.io/pterodactyl/core:java",
          "installed": true,
          "environment": {
            "SERVER_JARFILE": "server.jar",
            "VANILLA_VERSION": "latest",
            "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
            "P_SERVER_LOCATION": "test",
            "P_SERVER_UUID": "47a7052b-f07e-4845-989d-e876e30960f4"
          }
        },
        "updated_at": "2018-11-20T14:35:00+00:00",
        "created_at": "2018-09-29T22:50:16+00:00"
      }
    },
    {
      "object": "server",
      "attributes": {
        "id": 6,
        "external_id": null,
        "uuid": "6d1567c5-08d4-4ecb-8d5d-0ce1ba6b0b99",
        "identifier": "6d1567c5",
        "name": "Wow",
        "description": "t",
        "suspended": false,
        "limits": {
          "memory": 0,
          "swap": -1,
          "disk": 5000,
          "io": 500,
          "cpu": 200
        },
        "feature_limits": {
          "databases": 0,
          "allocations": 0
        },
        "user": 5,
        "node": 2,
        "allocation": 4,
        "nest": 1,
        "egg": 15,
        "pack": null,
        "container": {
          "startup_command": "./parkertron",
          "image": "quay.io/parkervcp/pterodactyl-images:parkertron",
          "installed": true,
          "environment": {
            "STARTUP": "./parkertron",
            "P_SERVER_LOCATION": "test",
            "P_SERVER_UUID": "6d1567c5-08d4-4ecb-8d5d-0ce1ba6b0b99"
          }
        },
        "updated_at": "2018-11-10T19:52:13+00:00",
        "created_at": "2018-11-10T19:51:23+00:00"
      }
    }
  ],
  "meta": {
    "pagination": {
      "total": 2,
      "count": 2,
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

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/servers/<internal-id>" %}
{% api-method-summary %}
Get server information
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="internal-id" type="integer" required=false %}
\*\*内部 ID\*\*
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "server",
  "attributes": {
    "id": 2,
    "external_id": null,
    "uuid": "47a7052b-f07e-4845-989d-e876e30960f4",
    "identifier": "47a7052b",
    "name": "Survival",
    "description": "gsk;ljgkj;hgdakl;gha",
    "suspended": false,
    "limits": {
      "memory": 2048,
      "swap": -1,
      "disk": 10000,
      "io": 500,
      "cpu": 300
    },
    "feature_limits": {
      "databases": 10,
      "allocations": 0
    },
    "user": 1,
    "node": 2,
    "allocation": 3,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io/pterodactyl/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "47a7052b-f07e-4845-989d-e876e30960f4"
      }
    },
    "updated_at": "2018-11-20T02:52:37+00:00",
    "created_at": "2018-09-29T22:50:16+00:00"
  }
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/servers/external/<external-id>" %}
{% api-method-summary %}
Get server by external ID
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="external-id" type="string" required=false %}
External ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "object": "server",
  "attributes": {
    "id": 7,
    "external_id": "cow_eater",
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "ok....",
    "suspended": false,
    "limits": {
      "memory": 1024,
      "swap": 0,
      "disk": 1000,
      "io": 500,
      "cpu": 0
    },
    "feature_limits": {
      "databases": 0,
      "allocations": 0
    },
    "user": 1,
    "node": 2,
    "allocation": 9,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io/pterodactyl/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "78165af0-4835-405f-b281-07e961bfd0ad"
      }
    },
    "updated_at": "2018-12-17T20:00:16+00:00",
    "created_at": "2018-12-11T21:56:00+00:00"
  }
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pterodactyl.app" path="/api/application/servers" %}
{% api-method-summary %}
Create server
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="deploy" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="allocation.additional.\*" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="allocation.additional" type="array" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="allocation.default" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="allocation" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="environment" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="feature\_limits.allocations" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="feature\_limits.databases" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="feature\_limits" type="array" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits.cpu" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits.io" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits.disk" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits.swap" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits.memory" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="limits" type="array" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="startup" type="string" required=false %}
服务器启动指令
{% endapi-method-parameter %}

{% api-method-parameter name="docker\_image" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="pack" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="egg" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="external-id" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Please note that every environment variable from the egg must be set.
{% endhint %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/application/servers/<internal-id>/details" %}
{% api-method-summary %}
Update server details
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="internal-id" type="string" required=false %}
内部 ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

