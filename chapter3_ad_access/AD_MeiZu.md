##MeiZu广告接入流程 Version=2.1
	魅族广告后台：user.isqhy.com








##MeiZu渠道接入注意事项
	1.广告sdk提供的ShenQiAd_Android_V2.1_20180725.jar里面有assets目录，需要把它解压出来然后放到  
	  工程或配置的assets目录下，再将jar包里的assets目录删除 
	2.MeiZu几种广告回调的不一定在主线程，比如闪屏的onFullScreenAdDismiss的回调是在JavaBridge线程；  
	  所以在处理各种广告回调的时候注意将其全部切换到主线程 
	3.6.0权限动态处理： 
	  a.android:name="android.permission.READ_PHONE_STATE"为广告显示必要权限，要做代码适配 
	  b.android:name="android.permission.WRITE_EXTERNAL_STORAGE"为视频广告显示必要权限，要做代码视频
	4.onComplete激励视频回调给出时机   
	即播放完成再退出：激励视频广告播放中途退出广告不会给出onComplete回调
	魅族激励视频广告在播放时一直屏蔽了物理返回键（包括倒计时完毕），切没有关闭按钮，只能等倒计时完毕广告sdk回调onComplete,之后出现"关闭"按钮，点击关闭按钮，广告sdk回调onClosed，这时我们同步给cp回调onClose和onComplete回调（cp接受到可以给用户发奖励）
		
	