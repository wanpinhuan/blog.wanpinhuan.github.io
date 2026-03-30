 

很多人问我：_“既然 OpenClaw 这么强，为什么普及不起来？”_

我去网上搜了一圈“部署教程”，答案瞬间清晰了——那哪是教程啊，那是“劝退说明书”。

*   乱： 满网的帖子，有的是 2026 年碎片化的代码，看得人头皮发麻。
    
*   杂： 这一篇让你装 Docker，那一篇让你配环境变量，还没开跑，你的电脑已
    
    经装了一堆没用的垃圾。
    
*   坑： 最离谱的是，居然有人在某鱼上把“代部署”做成了生意。点点鼠标、复制
    

几行代码就要收你几百块？这不仅是收割智商税，更是对技术的侮辱。

“难道普通人，真的不配拥有自己的 24 小时 AI 员工吗？”

看着那些因为卡在“第一步”而不得不放弃的开发者，我决定不再等了。

我开发了 GMClaw。

它的逻辑极其简单：把复杂的部署流程封装进可视化界面。 你不再需要盯着那个黑乎乎的终端窗口发呆，不再需要去翻那些不知所云的博客。

一键点击，自动配置，秒级上线。

**一、下载应用部署**

**1.进入GMSSH桌面在应用中心下载GMClaw进行安装部署**

![图片](https://i-blog.csdnimg.cn/img_convert/354481b0dbb95e34ad5d292c77136f88.png)

**2.打开应用，需要确保”docker管理器“ docker环境，docker镜像加速配置https://docker.gmssh.com（docker管理器设置）配置完成，应用会自动扫描环境**

![图片](https://i-blog.csdnimg.cn/img_convert/e3069af2663a6faccffa7bd65c6c4991.png)

**3.点击开始部署，配置自己的AI大模型，此处以deepseek为例**

![图片](https://i-blog.csdnimg.cn/img_convert/318c27f5646df074804eb3547f8f996d.png)

4.进入deepseek官网生成自己的 AI \-key，并且将自己的key填入

![图片](https://i-blog.csdnimg.cn/img_convert/aa903c2bfc04316f8ad800d802233c6f.png)

5.可以在高级设置自行设置占用的端口

![图片](https://i-blog.csdnimg.cn/img_convert/d4c81fc6f5290ecaf1be28d2038bf5b7.png)

6.设置完开始部署，等待片刻安装openclaw

![图片](https://i-blog.csdnimg.cn/img_convert/ba8d5985fb119c53c6a3db20f98a9576.png)

7.部署完成，进入控制台，可以打开Web-UI进入Openclaw（确保防火墙端口已打开）

![图片](https://i-blog.csdnimg.cn/img_convert/fb14071af75b29ea5310105fbdb2fcd3.png)

![图片](https://i-blog.csdnimg.cn/img_convert/1c2815a7cfbb7abb19923ac49e81b0a0.png)

* * *

二、接入三方聊天机器人

GMClaw支持可视化接入QQ、 企业微信 、飞书、钉钉等平台，接下来是接入教程。

【接入QQ】

进入QQ开放平台：https://q.qq.com/，注册账号后，进入机器人，创建一个应用

![图片](https://i-blog.csdnimg.cn/img_convert/4451065812d4d433234b832dc799d1e1.png)

![图片](https://i-blog.csdnimg.cn/img_convert/0ab8feb39ad02e0b16c9e04013c71ea6.png)

点击开发中进入机器人详情界面，复制如下信息：机器人ID、生成一个 密钥 ，并且白名单配置自己服务器的IP

![图片](https://i-blog.csdnimg.cn/img_convert/ecc94beadc204daf554b6e365fe45051.png)

回到GMClaw进行配置，选择QQ

![图片](https://i-blog.csdnimg.cn/img_convert/5ef4b4fedadbed9f6439e5307ce0d115.png)

输入配置信息后保存，等待片刻下载插件

![图片](https://i-blog.csdnimg.cn/img_convert/1375c8797c1c53f32ed355c3bfa46137.png)

![图片](https://i-blog.csdnimg.cn/img_convert/3b8fe6230e030c3139f3c23790f7b39b.png)

添加成员进行聊天，QQ扫码添加后聊天测试

![图片](https://i-blog.csdnimg.cn/img_convert/39c1b4853269324d152d3b62e5640e04.png)

![图片](https://i-blog.csdnimg.cn/img_convert/37c9684b12f23f8ed97db6c64aba5d1d.png)

【接入企业微信】

进入企业微信后台，进入应用管理，创建一个应用

```cobol
https://work.weixin.qq.com/wework_admin/frame#/apps
```

![图片](https://i-blog.csdnimg.cn/img_convert/41dd154a1b83b84d5cf11073c36dc05c.png)

拿到应用的 AgentId、Secret

![图片](https://i-blog.csdnimg.cn/img_convert/e3dd5ac676efea7020f4990ef9863b49.png)

进入我的企业拿到企业ID

![图片](https://i-blog.csdnimg.cn/img_convert/520a9104c5762d924da847b96f27cb99.png)

进入应用管理，点击刚才的应用，开启消息接收

![图片](https://i-blog.csdnimg.cn/img_convert/102e2c6ad61ad6dcbe1458e212e78415.png)

设置URL、Toekn、EncodingAESKey

注意：此处的Url一定需要域名，域名和你当前企业备案的域名一致，且域名需要解析到你部署的openclaw服务器上。如果没有可以选择接入其它聊天工具

Url示例，替换域名和端口即可

```cobol
http://域名:端口/wecom-app
```

![图片](https://i-blog.csdnimg.cn/img_convert/52e5b7c09c4327b5680c088ef2bb6765.png)

回到GMSSH，配置刚才复制的ID、密钥信息填入，点击保存完成配置。

![图片](https://i-blog.csdnimg.cn/img_convert/4aa3b5070d74b0f60611b39d538a61a6.png)

![图片](https://i-blog.csdnimg.cn/img_convert/b378bcc14150d936cf0895b86861aa14.png)

【接入飞书】

访问飞书开放平台：https://open.feishu.cn/app

创建企业自建应用、填写应用名称和描述、选择应用图标

![图片](https://i-blog.csdnimg.cn/img_convert/868038329ab3d27d03c79fe8414ba576.png)

在应用的 凭证与基础信息 页面，复制：

App ID（格式如 cli\_xxx）

App Secret

![图片](https://i-blog.csdnimg.cn/img_convert/aea641d345afb2a216da3c0a333ed353.png)

在 **权限管理** 页面，点击 **批量导入** 按钮，粘贴以下 JSON 配置一键导入所需权限：

![图片](https://i-blog.csdnimg.cn/img_convert/ff012bab3b4363cdbb85e6558fd64a41.png)

```csharp
{  "scopes": {    "tenant": [      "aily:file:read",      "aily:file:write",      "application:application.app_message_stats.overview:readonly",      "application:application:self_manage",      "application:bot.menu:write",      "cardkit:card:write",      "contact:user.employee_id:readonly",      "corehr:file:download",      "docs:document.content:read",      "event:ip_list",      "im:chat",      "im:chat.access_event.bot_p2p_chat:read",      "im:chat.members:bot_access",      "im:message",      "im:message.group_at_msg:readonly",      "im:message.group_msg",      "im:message.p2p_msg:readonly",      "im:message:readonly",      "im:message:send_as_bot",      "im:resource",      "sheets:spreadsheet",      "wiki:wiki:readonly"    ],    "user": ["aily:file:read", "aily:file:write", "im:chat.access_event.bot_p2p_chat:read"]  }}
```

启用机器人，点击编辑输入你的机器人名称，在后续配置需要使用

![图片](https://i-blog.csdnimg.cn/img_convert/af017de98d44211528f6318c30f98e84.png)

回到GM进行配置, 输入应用的ID、密钥，和刚刚配置的机器人名称。保存配置

![图片](https://i-blog.csdnimg.cn/img_convert/a66c5a8ad4465dcc91d606d6c83f5027.png)

返回飞书配置事件回调，选长连接

![图片](https://i-blog.csdnimg.cn/img_convert/a3da831e9d1975219ec1bc831f31008e.png)

添加事件,输入：im.message.receive\_v1，添加完后完成配置

![图片](https://i-blog.csdnimg.cn/img_convert/739abf0cff8f940cc4013286023deaff.png)

进入飞书APP，打开应用测试

![图片](https://i-blog.csdnimg.cn/img_convert/e6fc9cfcd54692e50a939e83f9bfa578.png)

![图片](https://i-blog.csdnimg.cn/img_convert/ca40f993028f573d89e5ae714db23e6f.png)

【接入钉钉】

进入钉钉，创建一个企业，如果有企业并且是管理员可以跳过到下一步

![图片](https://i-blog.csdnimg.cn/img_convert/54634a9d32a09aefd6174c3766e3d09e.png)

选择企业，和团队，完成创建。

![图片](https://i-blog.csdnimg.cn/img_convert/b9f9b534c37fbbfb46522a525969db85.png)

进入钉钉开放平台：https://open.dingtalk.com/

进入开发者后台

![图片](https://i-blog.csdnimg.cn/img_convert/7869309ca3d87be24b637d50f51f52bb.png)

进入应用开发，创建新应用，输入应用必要信息

![图片](https://i-blog.csdnimg.cn/img_convert/9c8413d7e5b9ad977f4a40d2b915ae3e.png)

进入机器人菜单，添加机器人能力

![图片](https://i-blog.csdnimg.cn/img_convert/cab564c82958a1861e73a68ccdb579c4.png)

进行配置机器人，注意消息回调一定要用Stream

![图片](https://i-blog.csdnimg.cn/img_convert/0662579121086c6082673d073b1e3c7c.png)

在“权限管理”中，搜索并添加权限：

1.  *   `Card.Instance.Write`（卡片实例写权限）
        
    *   `Card.Streaming.Write`（卡片流式写权限）
        
    *   `im:message`（消息相关权限，根据需要）
        

![图片](https://i-blog.csdnimg.cn/img_convert/a617f49f1d645559d432c872d1d99443.png)

在“版本管理与发布”中创建新版本并发布。

![图片](https://i-blog.csdnimg.cn/img_convert/a8ad39b60caffad67e68d384d22c64fc.png)

在概览处凭证与基础信息，复制App ID、AgentId、 Client ID、Client Secret回到GMSSH配置

![图片](https://i-blog.csdnimg.cn/img_convert/8d982258b2e781215bb0d8a6fa9b3c79.png)

Corp ID (企业 ID)在此处复制，右上角头像复制

![图片](https://i-blog.csdnimg.cn/img_convert/2900b2621a4615a160a066306a8ed0d3.png)

输入信息保存完成配置

![图片](https://i-blog.csdnimg.cn/img_convert/7bbd590d5f0b646c8ae6f77e07846ce3.png)

进入钉钉聊天添加机器人

![图片](https://i-blog.csdnimg.cn/img_convert/6c921bb699b2c6c4014612067013cd2b.png)

![图片](https://i-blog.csdnimg.cn/img_convert/5f56f5b84e3b2d8c92d3182a57ac67a2.png)

至此完成配置。

* * *

三、Skills能力管理

支持可视化安装skills，帮助你增强小 龙虾

![图片](https://i-blog.csdnimg.cn/img_convert/33b39a6159880ffd9d16e40291f3045e.png)

关注我，带你解锁更多openclaw使用技巧，后续不断更新更多可视化功能。

本文转自 <https://blog.csdn.net/Linux_cy/article/details/158572136>，如有侵权，请联系删除。