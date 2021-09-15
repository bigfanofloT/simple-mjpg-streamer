# simple-mjpg-streamer
使用UVC摄像头搭建网络摄像头基于`mjpg-streamer`简化

测试使用交叉编译器arm-himix200-linux-gcc

编译
`make`

依赖`jpeg`库，请将编译后的动态库放到`lib`目录
`export LD_LIBRARY_PATH=yourpath/lib`

使用
最简洁调用：
* `./mjpg_streamer -i "input_uvc.so -r 2592x1944" -o "output_http.so -w ./www"`
* `./mjpg_streamer -i "input_uvc.so -r 1920x1080" -o "output_file.so -f ./"`

板卡ip为`192.168.1.120`

* 视频流查阅：
在浏览器输入
<http://192.168.1.120:8080/?action=stream>
或者
<http://192.168.1.120:8080/javascript.html>
* 抓拍图片
在浏览器输入
<http://192.168.1.120:8080/?action=snapshot>
* 保存图片到本地
`curl http://192.168.1.120:8080/?action=snapshot -o a.jpg`

