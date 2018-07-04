##TapTap广告接入流程
	1.TapTap没有自家的广告sdk,需要cp自己找广告厂商合作。  
	这里我们选择Yomobsdk

	

##测试参数：  
	2.广告id:
		bannerID:
		interstitialID:
		splashID:
		nativeID：

##游戏数据：（碰碰球）	
	


##广告接入注意事项
	  其中“fake_app_key”,"fake_app_token"为固定值
	2.debug 和stage模式，发布时请务必关闭
	  MimoSdk.setDebugOn();
	  MimoSdk.setStageOn();
	3.系统开屏广告位miui为应用下发的，不用接入任何sdk,只要在广告后台开启，应用上线的时候即可显示，一般不会出现问题。
	3.应用内开屏和贴片视频广告会存在没预算和资源位不足的情况，所有会没有广告，加载失败的情况。banner和插屏预算和资源位相对充足。
