# API 简述

翼龙提供了一个 HTTP API，可以供你通过 RESTful API 远程控制服务器，比如控制服务器电源，发出控制台指令，获得服务器的各项信息，资源占用等。

当然，对于服务商，这个 API 同样提供给你丰富的管理能力。获得 Node 信息、客户服务器信息、增删改查 Node/Nest，停止客户服务器等等，都不在话下。

## 🤔 可以用来做什么？

1. QQ 机器人，远程控制服务器开关，实时查看和警告服务器过载、硬盘占用过高。
2. 定时获取服务器资源占用，占用过高时直接关服保平安。
3. 更方便的网页白名单系统。
4. 写一个机器人，定时检查客户机器到期时间并自动暂停客户机器。

## 👍 如何使用？

### 创建 API Key

在使用 API 前你需要有一个 API Key，你可能在控制面板上见过了：

![API &#x6807;&#x7B7E;&#x9875;](../.gitbook/assets/image%20%2815%29.png)

你需要创建一个 API Key，才能使用 API，这也是为了安全着想。

![](../.gitbook/assets/image%20%2812%29.png)

创建后，点击 Key，然后复制那一串乱码，它会很重要。

这里是一个简单的调用 API 的例子：

{% api-method method="get" host="https://demo.pterodactyl.io" path="/api/client" %}
{% api-method-summary %}
获取API Key账户名下所有服务器
{% endapi-method-summary %}

{% api-method-description %}
该示例调用了翼龙官方示例面板，获取账户名下的所有服务器。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=true %}
Application/vnd.pterodactyl.v1+json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer &lt;api-key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
JSON 输出了账户名下所有服务器的信息。
{% endapi-method-response-example-description %}

```javascript
{
   "object":"list",
   "data":[
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

