##应用宝渠道
	1.开放平台：http://wiki.open.qq.com/wiki/YSDK介绍
	





##应用宝渠道接入注意事项
	1.应用宝渠道要先完善财务信息，才能进行下一步，材料审核。  
	2.应用宝标准接入+米大师
	3.YSDK需要同步生命周期调用	onCreate(初始化)、onRestart、onResume、onPause、onStop、onDestory、onNewIntent、onActivityResult
	4.登录方式：
		a.QQ登录：YSDKApi.login(ePlatform.QQ)  
		b.WX登录：YSDKApi.login(ePlatform.WX)
		c.游客登录：YSDKApi.login(ePlatform.Guest)  
	5.获取当前的登录态和登录平台：  
		// 获取当前登录平台
	    public ePlatform getPlatform() {
	        UserLoginRet ret = new UserLoginRet();
	        YSDKApi.getLoginRecord(ret);
	        if (ret.flag == eFlag.Succ) {
	            return ePlatform.getEnum(ret.platform);
	        }
	        return ePlatform.None;
	    }  
	6.获取pf和pfKey  
		YSDKApi.getPf();  
		YSDKApi.getPfKey();
	7.获取登录记录  
		UserLoginRet ret=snew UserLoginRet();
		YSDKApi.getLoginRecord(ret)  
	8.登出  
		YSDKApi.logout();    
	9.道具直购-客户端下单  
		YSDKApi.bugGoods(false,
						大区id,  
						payItem(道具id,道具名称，道具描述，道具价格，道具数量),  
						MIDAS_APPKey,  
						byte[](商品图片)，	
						midasExt  
						ysdkExt  
						PayListener) 
	10.配置相关 
		a.游戏的主Activity在AndroidManifest.xml中配置需要配置  
		android:configChanges="orientation|screenSize|keyboardHidden"  
		android:launchMode="singleTop"  
		b.游戏的主Activity一定要配置横竖屏  
		c.APMidasPayProxyActivity中横竖屏的配置一定要和游戏主Activity的横竖屏配置一致  
		d.assets/ysdkconf.ini中手Q的appID必须和AndroidManifest.xml中com.tencent.tauth.AuthActivity中参数配置一致  
		e.assets/ysdkconf.ini中微信的appID必须和AndroidManifest.xml中***.***.***.WXEntryActivity中参数配置一致  
	11.游客模式 
		a.YSDK 从 1.2.3 版本开始支持接入游客登录体系。通过该功能，应用开发者可以不使用任何账号直接登入游戏。  
		b.该模块在接入时除了无需任何额外工作，只需要登录的时候调用对应的登录接口即可。  
		c.目前游客模式仅提供给单机类游戏使用
	



