# tct_docker_battery_historian

与 gcr.io/android-battery-historian/stable:3.1 同步

解决
1.公司无法访问google网络问题
2.go版本无法解析AndroidQ bugreport问题

安装方法：
使用docker直接运行
sudo docker run -p 9999:9999 tctdocker/tct_docker_battery_historian:3.1 --port 9999

如上可以成功部署docker版本的battery historian
但是还无法解析，因为解决过程中需要访问google网站的js，所以需要本地化，请参照 https://github.com/gusha915/no-ssr-battery-historian 操作
