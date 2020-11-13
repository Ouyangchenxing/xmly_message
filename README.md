# 喜马拉雅极速版  
# 此版本为本人自用，增加ios bark app推送（符合我本人自己的需求，增加一个新的Secrets-BARK_MACHINE_CODE
<p align="center">
  <img src="xmly_speed.jpg" alt="喜马拉雅极速版收益" width='40%' height='40%'/>

## 注意
如果使用bark app推送，建议直接fork本仓库，或者自行修改原作者 xmly_speed/.github/workflows/喜马拉雅.yml 文件，自己加一个secrets
由于本打算自己用的，所以我改了secrets的刷时长的value，现在修复了，不管怎样，现在给出解决放啊（只有github action受影响）  
解决方法  
* 打开action看日志，看看action是否打开时长，如果显示未打开，则查看脚本代码第44行，如下  
  if "XMLY_ACCUMULATE_TIME" in os.environ and os.environ["XMLY_ACCUMULATE_TIME"] == 'zero_s1':  
* 把secrets改成代码里的最后引号一个值，True或者zero_s1，自己看  
如果你忍不了报错（github action红色报错）注释掉代码848行，这个作者是注释掉的，我给打开了。  

如果想更改通知文字格式，请自己修改第822行代码  

### 关于测试bark app推送
打开脚本，注释掉第856行代码（if bj_dt.hour % 18 == 0 and bj_dt.hour / 18 == 1 and bj_dt.minute <= 30:），第857行代码向左缩进一个tab键（不缩进也无所谓，那应该会推送两次，反正是测试） ，测试完恢复原状就行，如果是煤30分钟运行一次，则每天晚上6.00-6.30推送一次，更改运行间隔时间肯定报错，详细请修改脚本第856行代码！

开个新坑    
喜马拉雅**极速版**自动化脚本    
请仔细阅读本说明     
暂时无法每天签到    
 [xmly_speed](xmly_speed.py)    

### 支持功能
~~1.幸运转盘4次~~  收益过低,且容易报错,故去除  
2.答题赚钱(完整)  
3.听书集卡获得抽卡机会、领取万能卡，但不会自动兑换  
4.首页、宝箱奖励及翻倍(完整)  
5.自动刷收听时长(可选项)   



### 邀请任务
[注册链接直达](https://m.ximalaya.com/xmds-node-spa/apps/speed-growth-activities/web-earn/landing?parentUserId=266513239&channel=1&srcChannel=weixin&srcPicUrl=https://fdfs.xmcdn.com/group63/M06/26/3C/wKgMcl0Z7-bgXtm3AAAP_-xdbjM707.png&srcText=1) (手机号注册)  
如果你的手机以及手机号之前没有注册过喜马拉雅的话，可以帮我完成一个邀请任务，感谢。

### 账号注册以及风控
1、使用**不同的手机设备**进行注册、刚注册的账号**不要退出**和切换账号，以免账号被封禁  
2、刚注册的账号**不要立刻跑脚本**，以免账号被封禁，无法提现  
3、同一手机最好不要切换账号，以免cookie过期 (待测) 

### 运行方案

1、GitHub action自动运行，账号信息读取自`Repo-Setting-Secrets`  

- cookie 信息抓包自**手机app(喜马拉雅极速版)**，域名为 `m.ximalaya.com`的可以
- fork 本项目
- Secrets 新增 `XMLY_SPEED_COOKIE`，填入cookie信息 ，多账号换行
- Secrets BARK_MACHINE_CODE，填你bark app的机器码（https://api.day.app/Y8G3ER7Bh/这里改成你自己的推送内容，机器码则为Y8G3ER7Bh｜每天晚上6点左右通知一次）
- star一下，立即执行，观察运行情况
-  **必须**  修改一次文件（比如自己库中的README.md文件）才能定时运行   (！！！！不要再问为什么不能自动运行;不懂不要修改cron )  
- 需要刷时长的，Secrets 新增 `XMLY_ACCUMULATE_TIME`，填入`zero_s1`；可能会黑号，请知悉

2、下载到本地运行   
   需要第三方库`requests`  

### 如何抓包cookie
- [手机抓包工具汇总](https://blog.zengrong.net/post/capture-package-on-phone/)
- [Stream -- iPhone上抓包神器](https://blog.csdn.net/heqiang2015/article/details/84023327)

<p align="center">
  <img src="抓包.png" alt="抓包" width='40%' height='40%'/> 

框中信息，不包含开头的`Cookie: `

### 查看

点击 Actions -Workflows

### Note
- 部分新手任务接口没有抓到，需要手动完成  
- **有些游戏 (比如转盘) 第一次需要手动运行**
- 暂时无法每天签到
- ~~旧脚本会刷收听时长，因此而黑号的，本人概不负责，请知悉（最新代码已经移除）~~ 最新版本修订为可选项
- ~~暂时去除刷时长功能，但是**保留了收取时长气泡以及翻倍的功能**。因此你可以保持app后台播放，每隔一段时间进入app刷新福利页面即可~~
- 不要询问 **可以通过简单搜索就可以知道答案** 的问题
