##百度渠道
	1.开放平台：http://wiki.open.qq.com/wiki/YSDK介绍
	





##百度渠道接入注意事项
	1.百度渠道sdk的targetSdkVersion 不能高于21，不然初始化不成功，打包的时候一定要注意，表现为闪屏不能自动跳过
	2.百度渠道初始化的时候DKPlatform.getInstance().init(mActivity, 
								baiDu_Game_isLandscape, //true:横屏；false:竖屏
								SdkMode.SDK_PAY, // 接入模式，支付版
								null, // DKCMMMData,移动MM初始化参数
								null, // DKCMGBData,移动基地初始化参数
								null, // DKCpWoStoreDaa,Cp版沃商店初始化数据
								new IDKSDKCallBack() )
	特别注意，第二个参数代表游戏的横竖屏方向，一定要和AndroidManifest.xml中的DKContainerActivity的横竖屏方向保持一致，不然调起支付时报错，甚至是crash.