##UBTool打包相关常用命令 
	ubsdk.keystore 
  	MD5: 6B:25:19:9E:BE:4D:75:AF:D9:60:E1:B6:8F:60:65:86
  	SHA1: 7E:16:F8:31:50:D2:D0:1C:01:72:E3:26:40:0B:84:B3:8F:D4:73:BC
    SHA256: D5:D6:6F:FE:AB:55:B2:2E:58:2D:BF:8D:44:9B:E2:C8:8E:CD:88:14:CF:E2:DB:EE:0A:EC:AA:75:B6:60:49:3D
    签名算法名称: SHA256withRSA
    版本: 3

	MD5:6B25199EBE4D75AFD960E1B68F606586 
	SHA1:7E16F83150D2D01C0172E326400B84B38FD473BC 
	SHA256:D5D66FFEAB55B22E582DBF8D449BE2C88ECD8814CFE2DBEE0AECAA75B660493D 
#### ============================================
	home_debug.keystore 
	MD5: 71:5D:C9:EC:BE:70:2A:DC:73:54:5F:8F:CA:81:5C:00
 	SHA1: 3F:53:D6:14:50:ED:53:3B:59:45:E4:63:8A:C5:71:4F:F2:8E:AF:F3
 	SHA256:
	68:13:7C:91:5D:FC:97:E5:6E:6D:DA:8B:7E:16:36:0A:67:E2:16:2D:13:41:39:82:1D:3C:6C:CA:4E:7B:6A:26
 	签名算法名称: SHA1withRSA 
	版本：1 

	MD5:715DC9ECBE702ADC73545F8FCA815C00 
	SHA1:3F53D61450ED533B5945E4638AC5714FF28EAFF3 SHA256:68137C915DFC97E56E6DDA8B7E16360A67E2162D134139821D3C6CCA4E7B6A26 
#### ============================================
	company_debug.keystore 
 	MD5: 47:39:02:9F:16:47:0F:AE:B2:FA:34:E4:D4:09:3D:CA
 	SHA1: D0:02:87:75:6E:E6:F9:38:04:27:47:E8:F3:B9:5C:E7:9C:C8:34:93
 	SHA256: 59:4C:7A:74:DD:01:18:F0:43:8D:8E:CF:24:C6:36:6F:4E:B8:37:1F:0E:62:AE:E0:45:D6:71:2F:69:20:1C:14
 	签名算法名称: SHA256withRSA
 	版本: 3 
	
	MD5:4739029F16470FAEB2FA34E4D4093DCA
	SHA1:D00287756EE6F938042747E8F3B95CE79CC83493 
	SHA256:594C7A74DD0118F0438D8ECF24C6366F4EB8371F0E62AEE045D6712F69201C14 
#### ============================================
	android的debug默认证书信息：
	keystore name: “debug.keystore”
	keystore password: “android”
	key alias: “androiddebugkey”
	key password: “android”
	CN: “CN=Android Debug,O=Android,C=US”
	
###获取apk的签名信息  
	1.直接获取apk的签名信息  
	  keytool -printcert -jarfile [apk目录] 
![keytool-apk-command](https://i.imgur.com/LrQT7GE.png)
	2.获取.keystore文件的签名信息 （需先安装jdk，并且需要输入秘钥库口令）
	  keytool -list -v -keystore [签名文件目录]				 
![keytool-keystore-command](https://i.imgur.com/UdlDthv.png)
	 