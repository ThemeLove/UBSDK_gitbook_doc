##应用宝广告接入流程
	1.应用宝广告接的是广点通，应用需要在应用宝平台上线之后才能在广点通后台申请广告参数
	

##测试参数：  
	广告id:
		bannerID:
		interstitialID:
		splashID:
		nativeID：

##游戏数据：（碰碰球）	
	广告appID:1107718281
	广告id:
		bannerID:2090931808783334
		interstitialID:5090830838085455


##应用宝广告接入注意事项
	1.插件代码要对23版本以上处理动态权限问题，请求广点通sdk所需的必要的权限 
	2.最好需要额外导入org.apache.http.legacy.jar
	  
	3.Banner 广告初始化必要权限android.permission.READ_PHONE_STATE，如果没有，初始化会失败， 
	  23版本以上特别注意要动态权限处理
	4.AndroidManifest.xml中要替换包名： 
	  android.support.v4.content.FileProvider的authorities属性的值为${applicationId}.fileprovider 
	5.广点通广告id要和广告后台填写的包名对应
