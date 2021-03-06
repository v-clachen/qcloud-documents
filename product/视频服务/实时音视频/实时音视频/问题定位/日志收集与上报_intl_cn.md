## 日志位置

日志在开发控制台输出的同时，也会写入终端的存储中。开发者可以在这些地方找到日志：

### Android

SDK|目录
:--:|:--:
iLiveSDK|tencent/imsdklogs/包名/ilivesdk_YYYYMMDD.log
IMSDK|tencent/imsdklogs/包名/imsdk_YYYYMMDD.log
AVSDK|tencent/imsdklogs/包名/QAVSDK_YYYYMMDD.log

### iOS

SDK|目录
:--:|:--:
iLiveSDK|Library/Caches/ilivesdk_YYYMMDD.log
IMSDK|Library/Caches/imsdk_YYYMMDD.log
AVSDK|Library/Caches/QAVSDK_YYYMMDD.log

### Mac

SDK|目录
--|--
iLiveSDK|/Users/**user**/Library/Caches/ilivesdk_YYYMMDD.log
IMSDK|/Users/**user**/Library/Caches/imsdk_YYYMMDD.log
AVSDK|/Users/**user**/Library/Caches/QAVSDK_YYYMMDD.log

* 注：user 是你自己电脑的登录账户，比如当前电脑的登录账户是 zhangsan，那么缓存路径是 /Users/zhangsan/Library/Caches

### PC

SDK|目录
:--:|:--:
iLiveSDK|程序运行目录/txsdklog/ilivesdk_YYYMMDD.log
IMSDK|程序运行目录/txsdklog/imsdk_YYYMMDD.log
AVSDK|程序运行目录/txsdklog/QAVSDK_YYYMMDD.log

### Web

SDK|目录
:--:|:--:
iLiveSDK|%appdata%/Tencent/iLiveSDK/txsdklog/ilivesdk_YYYMMDD.log<br/>(在开始菜单的运行中执行%appdata%可打开appdata目录)
IMSDK|%appdata%/Tencent/iLiveSDK/txsdklog/imsdk_YYYMMDD.log
AVSDK|%appdata%/Tencent/iLiveSDK/txsdklog/QAVSDK_YYYMMDD.log


## 日志收集接口

在需要用户上报日志的时候，调用日志上报接口。iLiveSDK 会直接把日志传到腾讯云后台。   

**Android接口**   

```java
/**
 * 上报日志
 *
 * @param desc 描述
 * @param data 0表示当天 1-昨天 2-前天 类推
 * @param callBack 回调
 * 
 */
ILiveSDK.getInstance().uploadLog(String desc, int data ILiveCallBack callback);
```
**iOS接口**         

```java
/**
 日志上报
 
 @param logDesc      日志描述
 @param dayOffset    日期，0-当天，1-昨天，2-前天，以此类推
 @param uploadResult 上报回调
 */
(void)uploadLog:(NSString *)logDesc logDayOffset:(int)dayOffset uploadResult:(ILiveLogUploadResultBlock)uploadResult;
```

**PC接口**

```c++
//暂未暴露接口
```

**Web接口**

```js
//暂未暴露接口
```

开发者可以在[ 日志查询平台 ](http://vip.avc.qcloud.com/SdkLog/home)查询用户和下载用户上传的日志。
![](https://main.qcloudimg.com/raw/deec9b5df4e0ae801f49854bb48da0b4.png)


