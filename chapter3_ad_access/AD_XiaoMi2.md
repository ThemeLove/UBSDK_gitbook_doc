##XiaoMi广告接入流程
	1.注册小米开发者账号  
[开放平台](http：//dev.xiaomi.com)  
	2.小米广告联盟入口在：管理控制台----->流量变现
	3.创建广告位参数
	

##测试参数：  
	2.广告id:
		bannerID:646f81ed5f4f4e57a9d426905c88ffef
		interstitialID:9edf613fe0c44bfab5fb29362117251c
		splashID:58a469f76d9a4a53aa651b875c4e2775
		nativeID：8b4baa87708a403eaed3c59614174882

##游戏数据：（碰碰球）	
	


##xiaomi广告接入注意事项
	1.初始化接口MimoSdk.init(application, mADXiaoMiAppID,"fake_app_key","fake_app_token");  
	  其中“fake_app_key”,"fake_app_token"为固定值
	2.debug 和stage模式，发布时请务必关闭
	  MimoSdk.setDebugOn();
	  MimoSdk.setStageOn();
	3.系统开屏广告位miui为应用下发的，不用接入任何sdk,只要在广告后台开启，应用上线的时候即可显示，一般不会出现问题。
	4.应用内开屏和贴片视频广告会存在没预算和资源位不足的情况，所有会没有广告，加载失败的情况。banner和插屏预算和资源位相对充足。
