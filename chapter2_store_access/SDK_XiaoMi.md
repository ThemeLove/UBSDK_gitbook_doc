##小米渠道接入流程
	1.在小米开放平台注册开发者账号：
[http://dev.xiaomi.com/doc/?p=90](http://dev.xiaomi.com/doc/?p=90)   
    2.在开发者后台创建游戏并申请AppID、AppKey、AppSecret
	3.在开发者后台配置计费方式、计费点、回调地址和计费单位

##碰碰球游戏测试数据
	appID:2882303761517707344
	appKey:5961770733344
	appSecret:BdKSyuOQQD5OcpoDhRhGcg==

	计费点：test001 ,remove_ads

##小米渠道接入注意事项
	1.copy jar包资源到libs目录下
	2.包名要求.mi结尾
	2.配置AndroidManifest.xml
	3.支付方式分为微信、支付宝、qq支付方式。单机一般在后台申请计费点信息。不用再单独集成计费点sdk.
