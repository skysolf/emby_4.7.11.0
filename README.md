# emby_4.7.11.0
# emby开心版


**emby开心版4.7.11**

# 1.下载4.7.11.0版本emby
下载地址：[https://github.com/MediaBrowser/Emby.Releases/releases/tag/4.7.11.0](https://github.com/MediaBrowser/Emby.Releases/releases/tag/4.7.11.0)



      大家根据自己的平台下载对应的安装程序，这里以群晖为例。下载好后到群晖套件中心，手动安装，选择安装包进行安装。

# 2.下载破解文件
将库里的[emby-happy4.7.11.0.sh](https://github.com/skysolf/emby_4.7.11.0/blob/main/emby-happy4.7.11.0.sh%20%22emby-happy4.7.11.0.sh%22) 和 [emby-happy.tar](https://github.com/skysolf/emby_4.7.11.0/blob/main/emby-happy.tar%20%22emby-happy.tar%22) 下载到你群晖任意目录下，如果非群晖用户，则需要您自己手动修改emby-happy4.7.11.0.sh，拷贝目录以你系统安装emby目录为准。

# 3.通过ssh连接你的nas，并到下载文件的目录运行脚本
```bash
#username是你nas用户名
#nasip是你nas地址
#port是端口号，如果你的nas ssh端口号是22就不用写-p这一段
ssh username@nasip -p port
#回车后输入你nas用户名对应的密码
#登陆成功后执行下面语句
#切换成root用户，回车后继续输入你nas用户名密码
sudo -i
#这里比如我们下载的emby-happy.tar和emby-happy4.7.11.0.sh在/root目录
cd /root
#修改文件执行权限
chmod 777 ./emby-happy4.7.11.0.sh
#执行破解
./emby-happy4.7.11.0.sh
```
# 4.停用emby和重新打开emby，并激活
    群晖用户到套件中心找到emby，停止运行，然后再次启动

    启动后点打开，跳转到emby页面，初始化ok后，进入设置--Emby Premiere--Emby Premiere 秘钥，随便输入几个字符，点击保存即可。这个时候状态就可以看到“您拥有一个 Lifetime Emby Premiere 计划且您的设备数未达到最大限制数量。”表示已经成功。右上角购买的图标也会消失。



# 5.如何判断是否开启硬解码
随便找一个hevc格式的视频，通过emby进行播放，然后打开设置--高级--日志--找到最新的ffmpeg-transcode-xxxxxx.txt，打开查看，如果能看到显卡信息以及硬解码已开启字样即可，如

```bash
>>>>>> Selected Codecs
Decoder VAAPI GeminiLake UHD Graphics 600 - H.265 (HEVC)
Adapter #0: 'GeminiLake UHD Graphics 600' Id:12677 (Driver: Intel iHD driver for Intel(R) Gen Graphics - 21.2.2 (27b773b2), Vendor: Intel Corporation)
Max Bitrate: 117 Mbit/s - Frame Sizes: max 8192x8192
Color Formats: NV12, P010 - Bit Depths: 8, 10
Profiles: Main Profile (Level 6.1), Main 10 Profile (Level 6.1)
 
Encoder VAAPI GeminiLake UHD Graphics 600 - H.264 (AVC)
Adapter #0: 'GeminiLake UHD Graphics 600' Id:12677 (Driver: Intel iHD driver for Intel(R) Gen Graphics - 21.2.2 (27b773b2), Vendor: Intel Corporation)
Max Bitrate: 234 Mbit/s - Frame Sizes: 32x32...4096x4096
Color Formats: NV12 - Bit Depths: 8
Profiles: Main Profile (Level 6), High Profile (Level 6), Constrained Baseline Profile (Level 6)
 
 
>>>>>> FindVideoEncoder - MediaType: h264, UseHardwareCodecs: True, HWA-Mode: Advanced
Info Checking: 'VAAPI GeminiLake UHD Graphics 600 - H.264 (AVC)'
Info Check successful - selecting 'VAAPI GeminiLake UHD Graphics 600 - H.264 (AVC)'
 
>>>>>> FindVideoDecoder - MediaType: hevc, UseHardwareCodecs: True, HWA-Mode: Advanced
Info Checking: 'VAAPI GeminiLake UHD Graphics 600 - H.265 (HEVC)'
Info Check successful - selecting 'VAAPI GeminiLake UHD Graphics 600 - H.265 (HEVC)'
Info Tone Mapping would be desired, but hardware tone mapping is disabled
```

