
# 相关结构

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 消息结构

```java
MsgInfo {
    long getMsgId();// 消息Id
    int getType();// 消息类型
    long getCreateTime();// 创建时间
    String getTalker();// 聊天Id(群聊/私聊)
    String getSendTalker();// 发送者Id
    String getContent();// 消息内容
    
    String getMsgSource();// 消息来源
    List<String> getAtUserList();// 艾特列表
    boolean isAnnounceAll();// 公告通知全体
    boolean isNotifyAll();// 艾特通知全体
    boolean isAtMe();// 艾特我

    QuoteMsg getQuoteMsg();// 引用消息
    PatMsg getPatMsg();// 拍一拍消息
    FileMsg getFileMsg();// 文件消息

    boolean isPrivateChat();// 私聊
    boolean isOpenIM();// 企业微信
    
    boolean isGroupChat();// 群聊
    boolean isChatroom();// 普通群聊
    boolean isImChatroom();// 企业群聊
    
    boolean isOfficialAccount();// 公众号
    
    boolean isSend();// 自己发的

    boolean isText();// 文本
    boolean isImage();// 图片
    boolean isVoice();// 语音
    boolean isShareCard();// 名片
    boolean isVideo();// 视频
    boolean isEmoji();// 表情
    boolean isLocation();// 位置
    boolean isApp();// 应用
    boolean isVoip();// 通话
    boolean isVoipVoice();// 语音通话
    boolean isVoipVideo();// 视频通话
    boolean isSystem();// 系统
    boolean isLink();// 链接
    boolean isTransfer();// 转账
    boolean isRedBag();// 红包
    boolean isVideoNumberVideo();// 视频号视频
    boolean isNote();// 接龙
    boolean isQuote();// 引用
    boolean isPat();// 拍一拍
    boolean isFile();// 文件
}

QuoteMsg {
    String getTitle();// 回复标题
    String getMsgSource();// 消息来源
    String getSendTalker();// 发送者Id
    String getDisplayName();// 显示昵称
    String getTalker();// 聊天Id(群聊/私聊)
    int getType();// 消息类型
    String getContent();// 消息内容
}

PatMsg {
    String getTalker();// 聊天Id(群聊/私聊)
    String getFromUser();// 发起者Id
    String getPattedUser();// 被拍者Id
    String getTemplate();// 模板内容
    long getCreateTime();// 创建时间
}

FileMsg {
    String getTitle();// 文件标题
    long getSize();// 文件字节
    String getExt();// 文件后缀
    String getMd5();// 文件MD5
}
```
# 朋友圈方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 上传文字

```java
void uploadText(String content);

void uploadText(String content, String sdkId, String sdkAppName);

void uploadText(JSONObject jsonObj);
```

## 上传图文

```java
void uploadTextAndPicList(String content, String picPath);

void uploadTextAndPicList(String content, String picPath, String sdkId, String sdkAppName);

void uploadTextAndPicList(String content, List<String> picPathList);

void uploadTextAndPicList(String content, List<String> picPathList, String sdkId, String sdkAppName);

void uploadTextAndPicList(JSONObject jsonObj);
```
# 其他方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 执行

```java
void eval(String code);
```

## 导入

```java
void load(String path);
```

## 日志

```java
void log(Object msg);
```

## 提示

```java
void toast(String text);
```

## 通知

```java
void notify(String title, String text);
```

## 取顶部Activity

```java
Activity getTopActivity();
```

## 上传设备步数

```java
void uploadDeviceStep(long step);
```
# 媒体方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 发送媒体

```java
void sendMediaMsg(String talker, MediaMessage mediaMessage, String appId);
```

## 分享文件

```java
void shareFile(String talker, String title, String filePath, String appId);
```

## 分享小程序

```java
void shareMiniProgram(String talker, String title, String description, String userName, String path, byte[] thumbData, String appId);
```

## 分享音乐

```java
void shareMusic(String talker, String title, String description, String musicUrl, String musicDataUrl, byte[] thumbData, String appId);
```

## 分享音乐视频

```java
void shareMusicVideo(String talker, String title, String description, String musicUrl, String musicDataUrl, String singerName, String duration, String songLyric, byte[] thumbData, String appId);
```

## 分享文本

```java
void shareText(String talker, String text, String appId);
```

## 分享视频

```java
void shareVideo(String talker, String title, String description, String videoUrl, byte[] thumbData, String appId);
```

## 分享网页

```java
void shareWebpage(String talker, String title, String description, String webpageUrl, byte[] thumbData, String appId);
```
# 网络方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## get

```java
void get(String url, Map<String, String> headerMap, PluginCallBack.HttpCallback callback);

void get(String url, Map<String, String> headerMap, long timeout, PluginCallBack.HttpCallback callback);
```

## post

```java
void post(String url, Map<String, String> paramMap, Map<String, String> headerMap, PluginCallBack.HttpCallback callback);

void post(String url, Map<String, String> paramMap, Map<String, String> headerMap, long timeout, PluginCallBack.HttpCallback callback);
```

## download

```java
void download(String url, String path, Map<String, String> headerMap, PluginCallBack.DownloadCallback callback);

void download(String url, String path, Map<String, String> headerMap, long timeout, PluginCallBack.DownloadCallback callback);
```
# 全局变量

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 变量说明

- `context`  
  上下文对象

- `moduleVer`  
  模块版本

- `cacheDir`  
  缓存路径

- `pluginDir`  
  插件路径

- `pluginId`  
  插件标识
# 联系方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 取当前登录Wxid

```java
String getLoginWxid();
```

## 取当前登录微信号

```java
String getLoginAlias();
```

## 取上下文Wxid

```java
String getTargetTalker();
```

## 取好友列表

```java
List<FriendInfo> getFriendList();
```

## 取好友昵称

```java
String getFriendName(String friendWxid);

String getFriendName(String friendWxid, String roomId);
```

## 取头像链接

```java
void getAvatarUrl(String username);

void getAvatarUrl(String username, boolean isBigHeadImg);
```

## 取群聊列表

```java
List<GroupInfo> getGroupList();
```

## 取群成员列表

```java
List<String> getGroupMemberList(String groupWxid);
```

## 取群成员数量

```java
int getGroupMemberCount(String groupWxid);
```

## 添加群成员

```java
void addChatroomMember(String chatroomId, String addMember);

void addChatroomMember(String chatroomId, List<String> addMemberList);
```

## 邀请群成员

```java
void inviteChatroomMember(String chatroomId, String inviteMember);

void inviteChatroomMember(String chatroomId, List<String> inviteMemberList);
```

## 移除群成员

```java
void delChatroomMember(String chatroomId, String delMember);

void delChatroomMember(String chatroomId, List<String> delMemberList);
```

## 通过好友申请

```java
void verifyUser(String wxid, String ticket, int scene);

void verifyUser(String wxid, String ticket, int scene, int privacy);
```

## 修改好友标签

```java

void modifyContactLabelList(String username, String labelName);

void modifyContactLabelList(String username, List<String> labelNames);
```
# 配置方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 读取方法

```java
String getString(String key, String defValue);

Set getStringSet(String key, Set defValue);

boolean getBoolean(String key, boolean defValue);

int getInt(String key, int defValue);

float getFloat(String key, float defValue);

long getLong(String key, long defValue);
```

## 写入方法

```java
void putString(String key, String value);

void putStringSet(String key, Set value);

void putBoolean(String key, boolean value);

void putInt(String key, int value);

void putFloat(String key, float value);

void putLong(String key, long value);
```
# 回调方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## 插件加载

```java
void onLoad();
```

## 插件卸载

```java
void onUnLoad();
```

## 监听收到消息

```java
void onHandleMsg(Object msgInfoBean);
```

## 发送按钮

```java
boolean onClickSendBtn(String text);
```

## 监听成员变动

```java
void onMemberChange(String type, String groupWxid, String userWxid, String userName);
```

## 监听好友申请

```java
void onNewFriend(String wxid, String ticket, int scene);
```
# 音频方法

::: warning 警告
本文档适用于 WAuxiliary v1.2.6 版本
:::

## mp3 到 Silk 文件

```java
File mp3ToSilkFile(String mp3Path);
```

## mp3 到 Silk 路径

```java
String mp3ToSilkPath(String mp3Path);
```

## mp3 到 Silk

```java
void mp3ToSilk(String mp3Path, String silkPath);
```

## silk 到 Mp3 文件

```java
File silkToMp3File(String silkPath);
```

## silk 到 Mp3 路径

```java
String silkToMp3Path(String silkPath);
```

## silk 到 Mp3

```java
void silkToMp3(String silkPath, String mp3Path);
```

## 取 silk 毫秒时长

```java
void getSilkDuration(String silkPath);
```
