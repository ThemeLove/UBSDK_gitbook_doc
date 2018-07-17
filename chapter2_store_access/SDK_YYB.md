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
	            return ePlatform.getEnum(ret.platform);s
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
		b.
		
	



