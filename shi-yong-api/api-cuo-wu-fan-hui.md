# API 错误返回

以下是翼龙 API 有可能返回的错误代码，请注意错误代码与返回 JSON 的其他消息可能有出入，请以错误代码的解释为准。

| Error Code | Meaning |
| :--- | :--- |
| 400 | **Bad Request** 请求无效或有问题 |
| 401 | **Unauthorized** 检查 API Key，有问题 |
| 403 | **Forbidden** 你被拒绝访问该 API，比如管理员操作 |
| 404 | **Not Found** API 不存在 |
| 405 | **Method Not Allowed** API 所需的 HTTP 请求方法不一致 |
| 406 | **Not Acceptable** 请求不是 JSON 格式 |
| 410 | **Gone** API 已被移除 |
| 418 | I'm a teapot. |
| 429 | **Too Many Requests** API 请求超速，降低请求速度 |
| 500 | **Internal Server Error** 内部出错 |
| 503 | **Service Unavailable** 后端拒绝请求，服务器资源不足，或暂时关闭维护 |



