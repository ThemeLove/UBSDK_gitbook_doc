##拇指玩渠道
	1.开放平台:http://open.muzhiwan.com/
	





##拇指玩渠道接入注意事项 
	1.拇指玩包名要求：.mzw结尾，有闪屏，不需要加角标
	1.拇指玩渠道要求游戏的主Activity必须有横竖屏配置   
	2.AndroidManifest.xml中的mzw_channel、mzw_cps元数据为默认值不用修改。 
        <meta-data
            android:name="mzw_channel"
            android:value="mzw" />
        <meta-data
            android:name="mzw_cps"
            android:value="mzw" /> 
	3.初始化需要放在主线程进行，初始化接口需要传递游戏方向，并且要在初始化之前进行动态权限兼容。 
	4.拇指玩要求支付前必须先登录，必须要有登录态才能完成支付。
	5.支付金额最小为1元，否则微信支付调不起来。 
	



##打包前注意修改事项 

	



