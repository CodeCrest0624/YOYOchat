##YOYOchat
#注意：由于项目太大，代码量多，独自一人开发。可能有BUG。发现请提交到 2964714665@qq.com 及时修复更新

![Github Release](https://img.shields.io/badge/release-v1.0.0-orange%20color)
![Language](https://img.shields.io/badge/language-Python-239120)
![OS](https://img.shields.io/badge/OS-Windows-0078D4)

#部署博客地址
[https://blog.csdn.net/weixin_66825409/article/details/144847166?fromshare=blogdetail&sharetype=blogdetail&sharerId=144847166&sharerefer=PC&sharesource=weixin_66825409&sharefrom=from_link](https://blog.csdn.net/weixin_66825409/article/details/144847166?fromshare=blogdetail&sharetype=blogdetail&sharerId=144847166&sharerefer=PC&sharesource=weixin_66825409&sharefrom=from_link "部署——博客地址")

##第一个版本主要是以实现功能为主，未做太多的优化。如果该项目有望，将会进行进一步更新和开发、优化。
#调查问卷链接
[https://www.wjx.cn/vm/eJauUnI.aspx#](https://www.wjx.cn/vm/eJauUnI.aspx# "YOYOchat优化/更新 调查文件")

#简介
一款 纯Python开发的聊天软件 `YOYOchat` 聊天工具，专为`Windows`开发:

<img src="http://techsavant.cn/github/YOYOchat/main_interface.png" width="70%" height="50%">

##主要功能

### 1. `好友聊天`
	 	需要先发送好友申请，同意后才能聊天
### 2. `群聊聊天`
### 3. `朋友圈`
### 4. `语音聊天`
### 5. `视频聊天`
### 6. `文件传输`



## 客户端配置
#连接服务器配置文件
	在 app/ini 文件夹下 
	connect_server_informations.json      #连接服务器配置信息
	ftp_server.json                       #连接FTP服务器配置信息（encrypt_decrypt_tools.exe 通过指定key加密的数据保存）
<img src="http://techsavant.cn/github/YOYOchat/client/QQ20241230-120405.png" width="70%" height="250px">

#加密文件(.py)里的key密钥设置
	在 app/rear_end 文件夹下
	encrypt_decrypt.py 文件 
<img src="http://techsavant.cn/github/YOYOchat/client/QQ20241230-122455.png" width="70%" height="450px">

	修改 encrypt_decrypt.py 文件 里的 client_service_key 变量 设为 对应的加密key（注意要和服务端一致）
<img src="http://techsavant.cn/github/YOYOchat/client/QQ20241230-122518.png" width="100%" height="490px">
	
	[未安装模块]
	pip install cryptography
	[python]
	from cryptography.fernet import Fernet
	# 生成密钥
	key = Fernet.generate_key()
	print(key)


##服务端部署
#配置服务器相关信息
	在文件目录 app\ini 里
	email_account.json      里的  sender[邮箱]、auth_code[授权码] 参数 需要填写  [IMAP/SMTP服务]配置 
	super_password.json   配置文件是删除服务端日志信息超级密码——解密数据为 love4you（可以自行更改）
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-120138.png" width="60%" height="280px">
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-120051.png" width="60%" height="130px">

	还需 phpstudy 的 
	apache 服务
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-123928.png" width="80%" height="110px">
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-123921.png" width="80%" height="510px">

	FTP 服务
	“yoyo_chat_phpstudy_ftp.zip”	#为FTP目录结构
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-123857.png" width="80%" height="310px">
	
	app/rear_end 文件夹下
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-123454.png" width="80%" height="510px">

	encrypt.py 文件里的 client_service_key 变量 设置为 加密key
<img src="http://techsavant.cn/github/YOYOchat/server/QQ20241230-123259.png" width="80%" height="510px">

	[未安装模块]
	pip install cryptography
	[python]
	from cryptography.fernet import Fernet
	# 生成密钥
	key = Fernet.generate_key()
	print(key)
