v1.1.2 2019/07/23
==
1. SDK功能更新
---
- 1.1 SDK支持多浏览器，包括chrome（版本不限），360，腾讯，搜狗，微信浏览器，safari，opera，暂不支持firefox
- 1.2 修改了切换视频流大小图接口，目前可以自由配置流大图小图，之前版本只支持同时显示一个大图
---
2. demo更新
---
- 2.1 web demo 支持多浏览器
- 2.2 web demo 更改切换大小图代码（搜索 streamInfos 变量相关方法）
---
3. 新增接口
---
- 3.1 接口StarRtc.StarRoomSDK.streamConfigApply（新的切换大小图方法）
- 3.2 接口StarRtc.StarVideoRoomSDK.streamConfigApply（新的切换大小图方法）
- 3.3 接口StarRtc.StarVideoSDK.streamConfigApply（新的切换大小图方法）
---
4. 接口变更
---
- 4.1 接口StarRtc.StarSDK.setSrcServerInfo= function (srcServerUrl, srcServerWebsocketPort, srcServerWebrtcPort, srcServerWebrtcIP)，新加参数srcServerWebrtcIP，此参数为可选参数，不传入时与serverUrl相同，用于chrome72版本以下、firefox、safari使用
- 4.2 接口StarRtc.StarSDK.setVdnServerInfo = function (vdnServerUrl, vdnServerWebsocketPort, vdnServerWebrtcPort, vdnServerWebrtcIP)，新加参数vdnServerWebrtcIP，此参数为可选参数，不传入时与serverUrl相同，用于chrome72版本以下、firefox、safari使用
- 4.3 接口StarRtc.StarSDK.setVoipServerInfo = function (voipServerUrl, voipServerPort, voipServerWebsocketPort, voipServerWebrtcPort, voipServerWebrtcIP)，新加参数voipServerWebrtcIP，此参数为可选参数，不传入时与serverUrl相同，用于chrome72版本以下、firefox、safari使用
---
5. 接口废弃
---
- 5.1 接口StarRtc.StarRoomSDK.streamConfigChange（旧的切换大小图方法）
- 5.2 接口StarRtc.StarVideoRoomSDK.streamConfigChange（旧的切换大小图方法）
- 5.3 接口StarRtc.StarVideoSDK.streamConfigChange（旧的切换大小图方法）
---
6. bug修复
---
- 6.1 demo修复创建房间失败时，再次创建房间会报chatroom重复登录的错误
---
7. 已知问题
---
- 7.1 多浏览器支持在微信浏览器，safari，opera进行视频互通时，会出现没有画面的情况
---
v1.1.1 2019/07/10
==
1. SDK功能更新
---
- 1.1 SDK支持voip音频对话模式
---
2. demo更新
---
- 2.1 web demo voip可选择音、视频对话示例
- 2.2 im demo提供聊天室创建，群组创建，群组成员查看、添加示例
---
3. 接口变更
---
- 3.1 接口StarRtc.StarSDK.getVoipRoomSDK = function (_oper, _userCallback, _userData)，参数_userData结构变为{"roomInfo":{"targetId":对方id, "audioOnly":是否仅进行音频聊天（可不传入，默认值为false，视频聊天）}}
- 3.2 接口StarRtc.StarSDK.sendVoipCallMsg = function (_targetId, _ts, _flag) 新加可选参数_flag， 是否是音频呼叫，默认为false（可选）
---
4. bug修复
---
- 4.1 修复没有摄像头时，voip无法连接的bug
---
v1.1.0 2019/07/8
==
1. SDK功能更新
---
- 1.1 SDK现在允许没有摄像头和麦克风时进入房间观看他人画面或者声音（vdn，src，voip）
- 1.2 SDK目前支持使用接口 StarRtc.StarRoomSDK.createScreenCaptureStream， 创建屏幕分享流
- 1.3 SDK提供超级对讲SDK StarRtc.StarSuperRoomSDK， 半双工模式，允许超大房间自由上麦
- 1.4 SDK StarRtc.StarSDK 现在允许多实例化（实现多用户同时登陆）， 实现超级监控功能（demo中有简单示例）
- 1.5 StarRtc.StarRoomSDK 目前提供自适应加入无chatRoom房间， 进入房间时，传入32位房间id则认为有chat功能， 传入16位房间id则认为没有chat功能
---
2. demo更新
---
- 2.1 demo提供超级对讲功能示例
- 2.2 demo提供超级监控功能示例
- 2.3 demo提供分享视频流功能示例
- 2.4 demo去掉了公有云配置及逻辑代码，增加了开启AEC或关闭AEC时的测试代码
---
3. 新增类和接口
---
- 3.1 类StarRtc.StarSDK（对应之前的StarRtc.Instance，提供多实例化能力）
- 3.2 类StarRtc.StarVideoRoomSDK， videoSDK简单封装
- 3.3 类StarRtc.StarChatRoomSDK， chatSDK简单封装
- 3.4 类StarRtc.StarSuperRoomSDK， 超级对讲SDK
- 3.5 类StarRtc.StarConfig， 配置
- 3.6 类StarRtc.StarUserInfo， 用户信息
- 3.7 接口StarRtc.StarSDK.setConfigUseAEC
- 3.8 接口StarRtc.StarSDK.getVideoRoomSDK
- 3.9 接口StarRtc.StarSDK.getChatRoomSDK
- 3.10 接口StarRtc.StarSDK.getSuperRoomSDK
- 3.11 接口StarRtc.StarRoomSDK.createScreenCaptureStream， StarRtc.StarVideoSDK.createScreenCaptureStream
- 3.12 接口StarRtc.StarVideoSDK.createNewSuperRoom
---
4. 接口变更
---
- 4.1 StarRtc.StarSDK.login 方法去掉了 authKey 参数
- 4.2 StarRtc.StarSDK.reportRoom
- 4.3 StarRtc.StarSDK.delRoom
- 4.4 StarRtc.StarSDK.queryRoom
- 4.5 StarRtc.StarRoomSDK构造函数
- 4.6 StarRtc.StarVideoSDK构造函数
- 4.7 StarRtc.StarChatSDK构造函数
---
5. 废弃类和接口，demo废弃代码
---
- 5.1 类StarRtc.Instance， 目前已经被StarRtc.StarSDK 代替，demo中为提出一种更改最少的方式， 目前令StarRtc.Instance = new StarRtc.StarSDK()
- 5.2 setConfigModePulic
- 5.3 接口StarRtc.StarRoomSDK.login
- 5.4 接口StarRtc.StarVideoSDK.login
- 5.5 接口StarRtc.StarChatSDK.login
- 5.6 接口StarRtc.Instance.setLoginServerUrl 
- 5.7 接口StarRtc.Instance.setMsgScheduleUrl 
- 5.8 接口StarRtc.Instance.setChatRoomScheduleUrl 
- 5.9 接口StarRtc.Instance.setSrcScheduleUrl 
- 5.10 接口StarRtc.Instance.setVdnScheduleUrl 
- 5.11 接口StarRtc.Instance.setVoipServerUrl 
- 5.12 接口StarRtc.Instance.setWorkServerUrl 
- 5.13 接口StarRtc.Instance.setWebrtcServerIP 
- 5.14 接口StarRtc.Instance.setConfigModePulic
- 5.15 接口StarRtc.Instance..queryVideoClassRoom 
- 5.16 接口StarRtc.Instance..queryChatRoom
- 5.17 接口StarRtc.Instance..queryVideoMeetingRoom 
- 5.18 接口StarRtc.Instance..queryVideoLiveRoom 
- 5.20 接口StarRtc.Instance..querySuperTalkRoom 
- 5.21 接口StarRtc.Instance.reportSuperTalkRoom 
- 5.22 接口StarRtc.Instance.reportVideoMeetingRoom 
- 5.23 接口StarRtc.Instance.reportVideoLiveRoom 
- 5.24 接口StarRtc.Instance.reportVideoClassRoom 
- 5.25 接口StarRtc.Instance.reportChatRoom 
- 5.26 接口StarRtc.Instance.delSuperTalkRoom 
- 5.27 接口StarRtc.Instance.delVideoMeetingRoom 
- 5.28 接口StarRtc.Instance.delVideoLiveRoom 
- 5.29 接口StarRtc.Instance.delVideoClassRoom 
- 5.30 接口StarRtc.Instance.delChatRoom 
---
6. 已知问题
---
- 6.1 web端听手机端音频音量过小问题
- 6.2 超级对讲创建房间时，创建者会自动显示在页面上的问题
---
v1.0.1 2019/06/14
==
更新sdk，vdn模式下不需要获取摄像头也可以观看画面