##VIVO渠道接入流程
	1.注册VIVO账号  
[开放平台](https://developer.vivo.com.cn/)  
	2.在管理后台创建游戏，注意包名以.vivo结尾，获取appID、cp-ID、appKey参数
	3.VIVO后台游戏截图要求竖图480*800,3-5张
	4.视频横屏：1920*1080，视频竖屏：1080*1920，要求时长为1-2分钟，不超过50M
	








##VIVO渠道接入注意事项
	1.在开发者后台创建应用，获取appID、cp-ID、appKey参数
	2.包名要求：.vivo 结尾
	3.微信直付必接，支付宝支付和收银台支付必选一种接入，我们接入微信直接和支付宝直接。
	4.微信支付支持：需要将WXPayEntryActivity.java放到 包名.wxapi的包下。
	5.手Q支付支持：需要修改AndroidManifest.xml文件的VivoQQPayResultActivity中
	intent-filter的data属性，属性值为"qwallet"+包名
	6.商品价格需要精确到小数点后两位，单位为元，如商品价格为6元，则要传"6.00",传"6"或者"6.0"会报错
	7.vivo测试的时候包名必须与vivo后台配置的包名一致，否则支付会提示验签失败

##API调用
	1.初始化：Application的onCreate方法里调用（在主进程调用）
		VivoUnionSDK.initSdk(application,VIVOAppID, false);//debug,正式版本设为false 

	2.退出
	VivoUnionSDK.exit(mActivity, new VivoExitCallback() {
			@Override
			public void onExitConfirm() {
			//				同步给出退出回调
				UBSDK.getInstance().getUBExitCallback().onExit();
			}
			@Override
			public void onExitCancel() {
			//				同步给出取消回调
				UBSDK.getInstance().getUBExitCallback().onCancel("user cancel", null);
			}
		});

	3.支付:(我们接入微信直接和支付宝直接)
		a.VIVO订单推送接口:先将“商品信息”连同“商户生成的订单号”传递到vivo服务器生成transNo、vivoSignature、price参数
		b.用transNo、vivoSignature、price参数拼装VivoPayInfo再调用支付api进行支付
			VivoUnionSDK.payNow(Activity activity, VivoPayInfo payInfo,VivoPayCallback callback，int payType) 

##待完善
	1.客户端sp里缓存订单号，每次初始化的时候订单查询之前的支付状态，以免漏单

