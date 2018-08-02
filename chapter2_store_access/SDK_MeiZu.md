##魅族渠道 version=2.0.1
	1.开发者后台：http://game.developer.flyme.cn/console/apps/game/list
	2.包名要求：.mz结尾
	

##碰碰球参数：
	appID:3194768
	appKey:799dbf67e35841028df83495a1eb84e4
	appSecret:7Oknf5UaAlUce0JPnk0dgChQW2jnRP8v


##魅族渠道接入注意事项 
	1.魅族要继承MzGameApplication，我们采取代理方式实现，或者参考魅族Demo中的GameApplication1 
	  的方式自己实现 
	2.AndroidManifest.xml中有大量Activity和其他配置要替换成游戏的packageName 
	3.注意根据游戏方向来处理sdk中配置Activity的方向。
	4.魅族sdk中Activity用到appcompat-v7-25.3.1的主题资源，AndroidManifest.xml中配置的也是 
	  android:theme="@style/Theme.AppCompat"，所以要注意将appcompat-v7对应资源拷贝进去。 
	5.appcompat-v7-25.3.1中需要用sdk>=25版本以上编译才可以，不然有资源报错。Android SDK Build Tools也要更新对应版本








##魅族渠道打包注意事项 
	1.由于appcompat-v7-25.3.1中资源文件众多，考虑到表现上只有AndroidManifest.xml中sdk的Activity的style属性  
	  用到android:theme="@style/Theme.AppCompat",所以将sdk中所有android:theme="@style/Theme.AppCompat" 
	  用android:theme="@android:style/Theme.Translucent.NoTitleBar.Fullscreen"来替换实现，经过demo测试 
	  并不影响功能。
