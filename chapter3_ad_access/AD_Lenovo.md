##Lenovo广告接入流程
	1.注册账号 [联想开放平台](http://open.lenovo.com/developer/lenovoReg.jspx)  
	2.创建应用，获取OPENAPPID,OPPOAPPID在单机sdk和广告sdk中公用一个  
	3.开发者后台----->联想广告平台，创建广告位参数








##Lenovo渠道接入注意事项
	1.参数申请：联想后台创建广告位参数
	2.包名要求：.lenovo 结尾
	3.meta-data配置OPPOAPPID
		    <meta-data
            	android:name="lenovo.open.appid"
            	android:value="1603040292217.app.ln" />  
	4.onComplete激励视频回调给出时机   
	即播放完成再退出：激励视频广告播放中途退出广告不会给出onComplete回调
	1.不给回调:激励视频播放中途用户点击物理返回键或者广告右上角的关闭按钮，并点击弹出框中的"退出播放"  
	2.给回调：激励视频倒计时结束，用户点击物理返回键或者右上角的关闭按钮  
		
	