###本章节主要记录UBSDK各家渠道广告sdk接入过程中的细节和注意事项  
	1. 各种广告回调的时候，UBAD.getInstance().getUBADCallback()这个一定要判空，否则不能正确回调或空指针。