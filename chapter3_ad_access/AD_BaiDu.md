##BaiDu广告接入流程
	1.注册百度开发者账号账号  
	2.百度广告在百度平台上架后才可以创建广告位
	
##测试参数：
	1.广告id
		bannerID:1000000
		interstitialID:1000001
		splashID:1000002
		rewardVideoID：1000003
	2.meta-data
		DUOKU_AD_APPKEY:50040
		DUOKU_AD_PRODUCT_KEY:OWNDEV_w6FRJc4aTw2oCPxyj
		DUOKU_AD_VERSION:3.1.0
	3.assets/adhmcfg
		app_key=998
		app_channelid=1

##游戏参数：
	1.广告id
		bannerID:2050839
		interstitialID:2050840
		splashID:2050841
		rewardVideoID:2050842s
	2.meta-data
		DUOKU_AD_APPKEY:11125131
		DUOKU_AD_PRODUCT_KEY:uDxP9u9InnhH1DzDHsGXofVT
		DUOKU_AD_VERSION:3.1.0
	3.assets/adhmcfg
		app_key=1000048
		app_channelid=1


##Baidu渠道接入注意事项
	1.AndroidManifest.xml中的特殊配置
		a.修改ReportDataContentProvider的authorities属性为 应用包名+.ReportDataContentProvider
		b.修改fileprovider的authorities属性为 应用包名+_lm.fileprovider
		c.配置meta-data:DUOKU_AD_APPKEY;DUOKU_AD_PRODUCT_KEY;DUOKU_AD_VERSION
		d.配置assets/adhmcfg文件
		e.配置res/values/tm_ids
	2.初始化在自定义Applicatioin里
		a.DuoKuAdSDK.getInstance().setOnline(false,this);//设置是否是线上地址
		b.DuoKuAdSDK.getInstance().setDebug(true);设置是否开启调试日志
		c.DuoKuAdSDK.getInstance().initApplication(this);初始化