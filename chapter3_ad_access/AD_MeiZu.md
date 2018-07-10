##MeiZu广告接入流程
	魅族广告后台：user.isqhy.com








##MeiZu渠道接入注意事项
	1.参数申请：魅族后台创建广告位参数
	2.包名要求：.mz 结尾 
	3.onComplete激励视频回调给出时机   
	即播放完成再退出：激励视频广告播放中途退出广告不会给出onComplete回调
	魅族激励视频广告在播放时一直屏蔽了物理返回键（包括倒计时完毕），切没有关闭按钮，只能等倒计时完毕广告sdk回调onComplete,之后出现"关闭"按钮，点击关闭按钮，广告sdk回调onClosed，这时我们同步给cp回调onClose和onComplete回调（cp接受到可以给用户发奖励）
		
	