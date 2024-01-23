# Nginx

## Nginx 命令

1、nginx -t 检查配置文件是否正确
2、nginx -s reload 重新加载配置文件
3、nginx -s stop 停止nginx
4、nginx -s quit 退出nginx
5、nginx -s reopen 重新打开日志文件

热部署：修改 nginx 配置文件之后，不需要停止 nginx，不需要中断请求，就能让配置文件生效。
原理：在重新加载配置之后，会新启用 worker 进程，新的请求由新的 worker 进程处理，在老的 worker 进程处理完之前的请求后，停止。
