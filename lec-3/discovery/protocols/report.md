***Team Member***

Yuan Gao
Bei Xia
Wenhui Zhang
chenghuhe
Maotong Xu
zhangwei

***Capabilities of your system***

1. Add conversion to the Discovery Server when the conversion server start up.
2. Remove conversion from the Discovery Server when the conversion server shut down.
3. Look up conversions from the Discovery Server.
4. Check the duplication when register new servers.

***Protocols***

1. Add new conversion to the Discovery Server by using command "add unit1 unit2 xxx.xxx.xxx.xxx yyyy"

  Success: Servers Updated!

  Failure: Failure: Duplication of Conversion!

2. Remove ip&port of the conversion from the Discovery Server by using command "remove xxx.xxx.xxx.xxx yyyy"

  Success: Servers Updated!

  Failure: Failture: not exists!(There is no server you can remove)

3. Look up conversion from the Discovery Server by using command "lookup unit1 unit2"

  Return: "xxx.xxx.xxx.xxx yyyy" or "None"(There is no existed server support this conversion)
  
ALL COMMANDS ARE NOT CASE SENSITIVE!

***Test***
1. javac DiscoveryServer.java
  
  java DiscoveryServer

2. javac ConvServer.java

  java ConvServer
  
3. javac ProxyServer.java

  java ProxyServer
