##Lenovo渠道接入流程
	1.联想开发者平台注册开发者账号，创建应用获取OPENAPPID(渠道sdk和广告sdk公用)；开发者平台： http://open.lenovo.com/developer/lenovoReg.jspx  
	2.发送邮箱和公司全称给联想商务申请联想子账号，子账号用户在爱贝支付后台申请支付参数，爱贝支付后台： http://www.iapppay.com/ 


##Lenovo渠道注意事项
	1. AndroidManifest.xml中配置项，游戏接入时这里不用改，如果是应用接入需要替换token值  
		<!-- 游戏接入时请直接复制此项内容；其他应用此处填写分配给应用的token -->
        <meta-data
            android:name="lenovo:applicationToken"
            android:value="PQY0Q8VH2888" />  
	2.请务必在您的主界面或者调用支付模块的界面在AndroidManifest.xml设置如下属性，否则调起支付时可能会  
	  因为横竖屏切换引起crash  
		android:configChanges="screenSize|orientation|keyboard|navigation|layoutDirection"  
	3.在游戏主界面Activity的onCreate方法里初始化，注意要正确传入游戏是横屏还是竖屏:  
		横屏：IAppPay.PORTRAIT;竖屏：IAppPay.LANDSCAPE  
		IAppPay.init(mActivity,IAppPay.PORTRAIT, mLenovoAppID);