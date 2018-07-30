##游戏母包处理过程  
####1.将母包拖动到ReBuildApkTool.bat批处理进行处理，特别注意work为工作目录。
####2.进入到work/temp目录下，注意处理res资源目录、AndroidManifest.xml、apktool.yml  
	a:res目录处理: 
		（1）：检查res目录是否是多资源目录，如果是，最好重新出母包 
		（2）：检查各个drawable和drawable-v4目录的重复图片资源 
		（3）：如果有values-v21/style.xml文件，注意检查其中的style属性
	b:AndroidManifest.xml:  
		（1）：修改根节点属性为：platformBuildVersionCode="23" platformBuildVersionName="6.0-2438415"
		（2）：检查application是否为：android:name="com.umbrella.game.ubsdk.ui.UBApplication"； 
			  删除application节点的android:banner="@drawable/app_banner"、android:isGame="true" 节点; 
		（3）：检查启动activity是否为android:name="com.umbrella.plugin.storebridge.UmbrellaActivity"； 
			  并配置属性： 
			  android:configChanges="orientation|screenSize|keyboardHidden"
              android:launchMode="singleTop"
              android:screenOrientation="portrait" 
	c.apktool.yml修改： 
		（1）：修改sdkInfo:一般minSdkVersion=14、targetSdkVersion=23 
		（2）：修改versionInfo为合适的值 
####3.回编：用和反编译时对应apktool版本执行回编apktool b [temp目录]，生成的未签名的apk在temp/dist/xxx.apk