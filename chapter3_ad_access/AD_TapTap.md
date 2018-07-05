##TapTap广告接入流程
	1.TapTap没有自家的广告sdk,需要cp自己找广告厂商合作。  
	这里我们选择Yomobsdk
	2.开放平台：https://yomob.com/home/zh  

	

##测试参数：  
	2.广告id:
		bannerID:
		interstitialID:
		splashID:
		nativeID：

##游戏数据：（碰碰球）	
	


##广告接入注意事项
	1.Yomobsdk 支持激励视频广告、插屏静态广告、插屏视频广告  
	2.Android7.0权限适配  
	a.    在 AndroidManifest.xml 中的 Application 标签中添加 provider 标签，接入代码如下所示：

	<application>
    <!-- targetSDKVersion >= 24时才需要添加这个provider。provider的authorities属性的值为${applicationId}.fileprovider，请开发者根据自己的${applicationId}来设置这个值 -->
    <provider
        android:name="android.support.v4.content.FileProvider"
        android:authorities="${applicationId}.fileprovider"
        android:exported="false"
        android:grantUriPermissions="true">
        <meta-data
            android:name="android.support.FILE_PROVIDER_PATHS"
            android:resource="@xml/gdt_file_path" />
    </provider>

    <provider
            android:name="com.lm.listener.FileProvider"
            android:authorities="${applicationId}.fileprovider"
            android:grantUriPermissions="true"
            android:exported="false">
        </provider>
    ... ...
	</application>

	需要注意的是 provider 的 authorities 值为 ${applicationId}.fileprovider，对于每一个开发者而言，这个值都是不同的，${applicationId} 在代码中和 Context.getPackageName() 值相等，是应用的唯一id。例如GDTUnionDemo示例工程中的applicationId为"com.qq.e.union.demo"。

    b.在项目结构下的res目录下添加一个xml文件夹，再新建一个gdt_file_path.xml的文件，文件内容如下：

	<paths xmlns:android="http://schemas.android.com/apk/res/android">
   		 <!-- 这个下载路径不可以修改，必须是GDTDOWNLOAD -->
    	<external-path name="gdt_sdk_download_path" path="GDTDOWNLOAD" />
    	<root-path name="download" path="" />
	</paths>    

	c.如果项目中已经存在 FileProvider 只需要将一下代码添加到 FileProvider 对应的xml文件中
    <?xml version="1.0" encoding="utf-8"?>
    <paths xmlns:android="http://schemas.android.com/apk/res/android">
        <!-- 这个下载路径不可以修改，必须是GDTDOWNLOAD -->
        <external-path name="gdt_sdk_download_path" path="GDTDOWNLOAD" />
        <root-path name="download" path="" />
        <external-files-path
            name="external_files_path"
            path="Download" />
    </paths>

	2.YomobSDK 要读取渠道信息，可以在初始化接口中传入渠道编号，或者在AndroidManifest.xml中配置，  
		二者选其一，TapTap对应的渠道编号为10053  
	3.测试接入时可以试用测试接口播放广告：TGSDK.showTestView(activity,"Your scene id from Yomob")  
		来替代正式环境下的播放接口  
		TGSDK.showAd(activity,"Your scene id from Yomob")  
		

	 
