***Team Member***

Yuan Gao
Bei Xia
Wenhui Zhang
chenghuhe
Maotong Xu
zhangwei

***Capabilities of your system***

1. Add conversion servers to the Discovery Server when the conversion servers start up.
2. Remove servers from the Discovery Server when the conversion servers shut down.
3. Look up conversion servers from the Discovery Server.
4. Check the duplication when register new servers.
5. Remove the conversion when all of its servers got removed.

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

  (Default Port: 1111)

2. javac ConvServer.java

  java ConvServer
  
  (Default Port: 3333, this is $ <--> oz conversion)
  
  (ConvServer add into the DiscoveryServer)
  
3. javac ProxyServer.java

  java ProxyServer
  
  (Default Port: 2222)
  
4. telnet 127.0.0.1 2222

  input "$ oz"
  
  return ip&port of conversion "$ oz"
  
5. input q in the terminal of ConvServer

  (Server removed from the DiscoveryServer)
  
6. telnet 127.0.0.1 2222

  input "$ oz"
  
  return "None" (Because the server shut down)
