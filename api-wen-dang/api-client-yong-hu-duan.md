---
description: 如果你是某服务商的客户，名下有你自己的服务器，就可以使用 Client API 对自己的服务器进行管理啦。
---

# API - Client - 用户端

{% hint style="info" %}
以下内容均为翼龙官方文档翻译，会尽力保持更新，但是你懂得，API 这东西写好了如果不出错，应该没人会愿意天天翻文档吧，不会吧不会吧
{% endhint %}

{% hint style="warning" %}
以下所有请求或多或少地要求在 **使用 API** 章节中的 **API 头部**。请不要忘记携带这些 header。在下面的文档中将不再赘述。
{% endhint %}

{% page-ref page="../shi-yong-api/api-tou-bu.md" %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/client" %}
{% api-method-summary %}
列出名下所有服务器
{% endapi-method-summary %}

{% api-method-description %}
梅开二度
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Accept" type="string" required=true %}
Application/vnd.pterodactyl.v1+json
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer &lt;api-key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "object":"list",
   "data":[
      {
         "object":"server",
         "attributes":{
            // 是否是 owner
            "server_owner":true,
            // ID, 调用很多API会用到
            // https://面板地址/server/[ID]
            "identifier":"d3aac109",
            // UUID
            "uuid":"d3aac109-e5a0-4331-b03e-3454f7e136dc",
            // 服务器名字
            "name":"Survival",
            // 描述
            "description":"",
            // 资源限制
            "limits":{
               "memory":1024,
               "swap":0,
               "disk":5000,
               "io":500,
               "cpu":200
            },
            // 功能限制
            "feature_limits":{
               // 数据库数量
               "databases":5,
               // 端口数量
               "allocations":5
            }
         }
      }
   ],
   "meta":{
      "pagination":{
         "total":1,
         "count":1,
         "per_page":25,
         "current_page":1,
         "total_pages":1,
         "links":[

         ]
      }
   }
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/client/servers/<ID>" %}
{% api-method-summary %}
特定服务器数据
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ID" type="string" required=true %}
服务器 identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "object":"server",
   "attributes":{
      "server_owner":true,
      "identifier":"d3aac109",
      "uuid":"d3aac109-e5a0-4331-b03e-3454f7e136dc",
      "name":"Survival",
      "description":"",
      "limits":{
         "memory":1024,
         "swap":0,
         "disk":5000,
         "io":500,
         "cpu":200
      },
      "feature_limits":{
         "databases":5,
         "allocations":5
      }
   }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pterodactyl.app" path="/api/client/servers/<ID>/utilization" %}
{% api-method-summary %}
获取服务器资源利用率
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ID" type="string" required=true %}
服务器 identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "object":"stats",
   "attributes":{
      "state":"on",
      "memory":{
         "current":375,
         "limit":1024
      },
      "cpu":{
         "current":1.522,
         "cores":[
            0.033,
            0.048,
            0.04,
            0,
            0.031,
            0,
            0.021,
            0.024,
            0.249,
            0.042,
            0.007,
            0,
            0.293,
            0.003,
            0.6,
            0.131
         ],
         "limit":200
      },
      "disk":{
         "current":119,
         "limit":5000
      }
   }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pterodactyl.app" path="/api/client/servers/<ID>/command" %}
{% api-method-summary %}
向服务器发送指令
{% endapi-method-summary %}

{% api-method-description %}
**服务器必须处于开启状态，否则返回 412 ❌错误。**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ID" type="string" required=true %}
identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="BODY 内容" type="object" required=true %}
{ "command": "say 你好世界！" }
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
成功的话，不会返回任何数据。
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pterodactyl.app" path="/api/client/servers/<id>/power" %}
{% api-method-summary %}
向服务器发送电源动作（开关机）
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ID" type="string" required=true %}
identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="BODY 内容" type="object" required=false %}
{ "signal": "start" }
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
成功的话，不会返回任何数据。
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

忍不住吐槽一下，这编辑器真的体验很差，复制东西不了还要去地址栏二次复制一下...

###  电源信号 Signal 参数

| signal | meaning |
| :--- | :--- |
| start | 开服 |
| stop | 关服 |
| restart | 重启 |
| kill | 杀进程 |

{% hint style="warning" %}
使用 kill 会强制杀死进程。这可能导致回档甚至区块错乱这种问答版大佬都解决不了的各种严重问题。请慎重使用 kill，仅将其作为最后手段使用。
{% endhint %}

