# tct_docker_battery_historian

与 gcr.io/android-battery-historian/stable:3.1 同步

解决
1.公司无法访问google网络问题
2.go版本无法解析AndroidQ bugreport问题

安装方法：
使用docker直接运行
sudo docker run -p 9999:9999 tctdocker/tct_docker_battery_historian:3.1 --port 9999
