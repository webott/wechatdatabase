# wechatdatabase
PC微信机器人接口api之实战分析微信数据库句柄
Q：2645542961
今天我们分析微信数据库句柄，就是实时查询最新数据，思路是，当我们登陆微信时，他会读取本地的sqlite 数据库，先OD附加微信，读数据的api是CreateFileW，找到后，下一个断点，然后点击微信登陆，看到已经断下来了，然后在右下角找是否有db结尾的数据库，如果没，就放过去断点，继续找，
![image](https://user-images.githubusercontent.com/73727649/121851111-509c4c00-cd20-11eb-98df-60826ed72a8e.png)
然后最后发现有db数据库信息，都在db下面的 返回到…，点击右键，点击反汇编窗口中跟随，在左上角里面下断点，
![image](https://user-images.githubusercontent.com/73727649/121851136-56922d00-cd20-11eb-9711-b01f6a35070c.png)
![image](https://user-images.githubusercontent.com/73727649/121851148-5a25b400-cd20-11eb-98c8-30ab86f087cb.png)
 然后走断点，发现ecx里面装的数据库路径，edx里面装的缓冲区，这里就是数据库句柄
 ![image](https://user-images.githubusercontent.com/73727649/121851170-61e55880-cd20-11eb-80fa-c3e9567e4273.png)
目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961

![image](https://user-images.githubusercontent.com/73727649/121851221-73c6fb80-cd20-11eb-8748-5ade74d6bc30.png)
