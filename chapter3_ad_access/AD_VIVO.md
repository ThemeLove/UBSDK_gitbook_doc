##VIVO广告接入流程   Version=2.4.1
	1.注册VIVO账号[开放平台](https://developer.vivo.com.cn/)   
	2.VIVO广告联盟需要在VIVO游戏中心或者软件商店上架后才可以创建广告位。 
	3.广告位创建成功之后要邮件报备:邮件格式如下：报备邮件：liyanqi@vivo.com 抄送danji@vivo.com
![vivo广告报备邮件](https://i.imgur.com/bpO4jkC.png) 
	4.开发者后台提交的时候，如果apk中集成了广告，要备注：已接入vivo广告，以及广告弹出策略
	

##测试参数：  
	1.appID:b220712c388141d6a5cb944980c3f57b
	2.广告id:
		bannerID:646f81ed5f4f4e57a9d426905c88ffef
		interstitialID:9edf613fe0c44bfab5fb29362117251c
		splashID:58a469f76d9a4a53aa651b875c4e2775
		nativeID：8b4baa87708a403eaed3c59614174882

##游戏数据：（碰碰球）	
	


##VIVO广告接入注意事项
	1.vivo支持banner(banner)、interstitial(插屏)、splash(闪屏)、native(原生)4种广告类型  
	2.native广告类型：就是根据广告id调用vivo的api获取数据显示在自己本地的view视图上，并根据返回的数据字段做不同展示形式和交互
	3.vivo目前不支持视频广告
	4.目前闪屏广告只支持全屏，并且为竖屏
	5.在自定义Application或游戏主Activity的onCreate里初始化都行
	6.AndroidManifest.xml中有2处要替换包名  
		<!--如果targetSdkVersion设置值>=24，则需要添加provider申明，否则不需要添加，注意需要替换包名-->
        <provider
            android:name="com.baidu.mobads.openad.FileProvider"
            android:authorities="com.jd.game.onetpet.vivo.bd.provider"
            android:exported="false"
            android:grantUriPermissions="true">
            <meta-data
                android:name="android.support.FILE_PROVIDER_PATHS"
                android:resource="@xml/bd_file_paths"/>
        </provider>  
		
        <!-- targetSDKVersion >= 24时才需要添加这个provider。provider的authorities属性的值为${packageName}.fileprovider，请开发者根据自己的${applicationId}来设置这个值 -->
        <provider
            android:name="android.support.v4.content.FileProvider"
            android:authorities="com.jd.game.onetpet.vivo.fileprovider"
            android:exported="false"
            android:grantUriPermissions="true">
            <meta-data
                android:name="android.support.FILE_PROVIDER_PATHS"
                android:resource="@xml/gdt_file_path"/>
        </provider>
	4.显示闪屏广告时要做6.0版本以上权限兼容处理,详情见ADVIVOSplashActivity 
	5.vivo_adsdk_v2.4.1.jar中包含assets目录，需要将其解压出来放到工程或配置的assets目录，再将jar包里assets目录删除。   
	6.vivo广告会根据广告后台检验当前广告位参数所对应的包名是否对应，如果不对应则拉去广告失败。


##接入问题
	1.点击插屏广告"点击安装" 没有反应，sdk有红色error报错