# Nginx

## Nginx 命令

1. nginx -t 检查配置文件是否正确
2. nginx -s reload 重新加载配置文件
3. nginx -s stop 停止nginx
4. nginx -s quit 退出nginx
5. nginx -s reopen 重新打开日志文件

热部署：修改 nginx 配置文件之后，不需要停止 nginx，不需要中断请求，就能让配置文件生效。
原理：在重新加载配置之后，会新启用 worker 进程，新的请求由新的 worker 进程处理，在老的 worker 进程处理完之前的请求后，停止。

## Ngnix 配置

参数|作用
-|-
$args                   |请求中的参数
$content_length         |HTTP请求信息里的"Content-Length"
$content_type           |请求信息里的"Content-Type"
$document_root          |针对当前请求的根路径设置值
$document_uri           |与$uri相同
$host                   |请求信息中的"Host"，如果请求中没有Host行，则等于设置的服务器名
$http_host              |d
$limit_rate             |对连接速率的限制
$request_method         |请求的方法，比如"GET"、"POST"等
$remote_addr            |客户端地址
$remote_port            |客户端端口号
$remote_user            |客户端用户名，认证用
$request_filename       |当前请求的文件路径名
$request_body_file      |当前请求的文件
$request_uri            |请求的URI，带查询字符串
$query_string           |与$args相同
$scheme                 |所用的协议，比如http或者是https，比如rewrite ^(.+)$ $scheme://example.com$1redirect
$server_protocol        |请求的协议版本，"HTTP/1.0"或"HTTP/1.1"
$server_addr            |服务器地址
$server_name            |请求到达的服务器名
$server_port            |请求到达的服务器端口号
$uri                    |请求的URI，可能和最初的值有不同，比如经过重定向之类的
