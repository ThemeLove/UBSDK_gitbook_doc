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
		f.com.tencent.connect.common.AssistActivity必须是portrait
	11.游客模式 
		a.YSDK 从 1.2.3 版本开始支持接入游客登录体系。通过该功能，应用开发者可以不使用任何账号直接登入游戏。  
		b.该模块在接入时除了无需任何额外工作，只需要登录的时候调用对应的登录接口即可。  
		c.目前游客模式仅提供给单机类游戏使用

	12.应用宝登录必要权限android.permission.READ_PHONE_STATE.如果没有该权限会登录失败。要显示申请 
	13.单机游戏米大师后台分区回调配置，还需要将appID发给应用宝的人配置才能生效，否则Q币、Q卡、手机充值卡会有弹框错误   
	沙箱：http://10.175.133.101:80/v3/r/pay/pdc_gateway_dummy 
	现网：http://10.223.30.52:8090/v3/r/pay/pdc_gateway_dummy 
	14.打包时jni目录的处理方式： 
	a.打包时只保留armeabi文件夹以及对应运行库so文件，删掉其它的所有jni支持库的文件夹如(arm64 X86 X86_64 mips等)；
	b.如只有armeab_v7a则把YSDK JniLib 中armeabi目录下对应so库copy到armeab_v7a文件夹内  




##打包前注意修改事项 
	1.要手动修改AndoridManifest.xml中的的手Q的AppID 和微信的AppID， 
	  并且要和assets/ysdkconf.ini中配置的一样
	2.应用宝渠道要求游戏的主Activity要配置
	  android:configChanges="orientation|screenSize|keyboardHidden"  
	  android:launchMode="singleTop"  
	  screenOrientation="游戏的横竖屏"
	3.assets/ysdkconf.ini中的正式包时一定要切换到线上环境； 
	  该文件里还包含手Q AppID、微信AppID、米大师offerID、icon等开关控制 
	4.米大师的AppKey在正式上线的时候要用现网appKey，并且要在后台发布到现网环境,在channel中配置； 
	  并且配置米大师后台分区回调，还需要将appID发给应用宝的人配置才能生效，否则Q币、Q卡、手机充值卡会有弹框错误 
	  沙箱：http://10.175.133.101:80/v3/r/pay/pdc_gateway_dummy 
	  现网：http://10.223.30.52:8090/v3/r/pay/pdc_gateway_dummy 
	5.BoomDots这个游戏的签名要用debug签名，fingerprint:71:5D:C9:EC:BE:70:2A:DC:73:54:5F:8F:CA:81:5C:00
	6.YSDK_Android_1.39_917.jar中有包含assets目录，要将其解压之后放到assets目录下，并将jar中的assets目录删除
	7.目前不同的游戏打包时需要单独build的一个ubsdk_yyb_xxxxx.jar，因为要适配WXEntryActivity.java的包名， 
	  后期可以完善在UBTool打包脚本里
	8.打包时要特别注意处理jni的目录，xxxx.so的一定要在armeabi或者armeabi-v7a目录中， 
	  且最终的游戏包一定要有这2个目录的至少其中一个，否则可能出问题 
	



