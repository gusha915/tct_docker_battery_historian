# tct_docker_battery_historian

与 gcr.io/android-battery-historian/stable:3.1 同步

解决  
1.公司无法访问google网络问题  
2.go版本无法解析AndroidQ bugreport问题  

安装方法：  
使用docker直接运行  
sudo docker run --restart=always -p 9999:9999 tctdocker/tct_docker_battery_historian:3.1 --port 9999  
加入 --restart=always 参数，表示机器重启后或者docker服务重启，容器也会自动重启运行     

docker安装方法 https://docs.docker.com/install/   

如上可以成功部署docker版本的battery historian 但是还无法解析，因为解析过程中需要访问google网站的js，所以需要本地化，请参照 https://github.com/gusha915/no-ssr-battery-historian 操作  
在 https://github.com/gusha915/no-ssr-battery-historian 下载base.html 及cdn目录，替换原码下的 battery-historian\templates\base.html 以及创建battery-historian\third_party 下cdn（docker根目录 /var/lib/docker）   
gaoxiang.zou@U-gaoxiang:/var/lib/docker$ sudo find ./ -name base.html  
./aufs/diff/3e3c95b069f1f065beb8acca0edd590a830777ddb4a1c5974b92d0580ea96f33/gopure/src/github.com/google/battery-historian/templates/base.html  
./aufs/diff/1d2db5b994f2debe79ca6e3d094871309cbf6a6ff6db34fbbadf50d0fdf79c12/gopure/src/github.com/google/battery-historian/templates/base.html  
./aufs/mnt/9e10024fbde3a938665752a90d06fa3a18e7132f175dd77933ce4d50e4974023/gopure/src/github.com/google/battery-historian/templates/base.html  
gaoxiang.zou@U-gaoxiang:/var/lib/docker$ sudo find ./ -name cdn  
./aufs/diff/1d2db5b994f2debe79ca6e3d094871309cbf6a6ff6db34fbbadf50d0fdf79c12/gopure/src/github.com/google/battery-historian/third_party/cdn  
./aufs/mnt/9e10024fbde3a938665752a90d06fa3a18e7132f175dd77933ce4d50e4974023/gopure/src/github.com/google/battery-historian/third_party/cdn
gaoxiang.zou@U-gaoxiang:/var/lib/docker$  

