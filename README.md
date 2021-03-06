# 推流 所在项目 Streaming

![推流](art/streaming.gif)

#### 左边是推流端,右边是播放端, 由于gif图片过大,如果加载不出来,请查看art/streaming.gif

### 开发工具
Android Studio 3.0

Android NDK r12

使用的开源库
------

- [openh264](https://github.com/cisco/openh264)
- [fdk-aac](https://github.com/mstorsjo/fdk-aac)
- [srs-librtmp](https://github.com/ossrs/srs)
- [libyuv](https://chromium.googlesource.com/libyuv/libyuv/)

支持如下功能:
-------

- [x] H.264/AAC 硬编 Api 18支持.
- [x] H.264/AAC 软编 Api 16.
- [x] 更多可选项配置(正在开发中).
- [x] 水印(正在开发中).

使用方式:

onCreate中设置初始化

```java

CameraSetting cameraSetting = new CameraSetting();
AudioSetting audioSetting = new AudioSetting();
StreamingSetting streamingSetting = new StreamingSetting();
streamingSetting.setRtmpUrl("rtmp://www.ossrs.net:1935/live/demo")
    .setEncoderType(EncoderType.SOFT);

GLSurfaceView glSurfaceView = (GLSurfaceView) findViewById(R.id.gl_surface_view);
mMediaStreamingManager = new MediaStreamingManager(glSurfaceView);
mMediaStreamingManager.prepare(cameraSetting, streamingSetting, audioSetting);
```

### 打开摄像头在```onResume```中调用
```java
mMediaStreamingManager.resume();
```

### 释放摄像头```onPause```中调用
```java
mMediaStreamingManager.pause();
```

### 开始推流
```java
mMediaStreamingManager.startStreaming();
```

### 停止推流
```java
mMediaStreamingManager.stopStreaming();
```


### 最近离职了,开始找工作了,如果不介意高中学历,有合适的机会谢谢帮忙推荐 [简历](https://github.com/wlanjie/Resume)

### 关于我

wlanjie，
联系方式:qq:153920981 微信:w153920981
