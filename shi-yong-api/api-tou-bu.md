# API 头部

翼龙 API 调用所必须的 header 主要有：

| key | example value | explanation |
| :--- | :--- | :--- |
| Accept | Application/vnd.pterodactyl.v1+json | - |
| Authorization | Bearer ocLJIbd7xUyjHQ3G0... | 这个头包含了你的 API Key，请注意**必须以 Bearer+空格开头**，之后再是你的 API Key。 |
| Content-Type | application/json | - |

## 验证头

调用 API 的 HTTP 请求中必须包含 `Authorization` 头，这个头中包括了你的 API Key，以及 Bearer，作为前缀。`Authorization` 头的格式应为 `Bearer <你的APIKey>`。

请一定注意不要忘记携带 Bearer 前缀，我因为这个捣鼓了两个小时 :\(

