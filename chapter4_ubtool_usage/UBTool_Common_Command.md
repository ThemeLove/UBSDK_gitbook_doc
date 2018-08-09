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
###获取apk的签名信息  
	1.直接获取apk的签名信息  
	  keytool -printcert -jarfile [apk目录] 
![keytool-apk-command](https://i.imgur.com/LrQT7GE.png)
	2.获取.keystore文件的签名信息 （需先安装jdk，并且需要输入秘钥库口令）
	  keytool -list -v -keystore [签名文件目录]				 
![keytool-keystore-command](https://i.imgur.com/UdlDthv.png)
	 