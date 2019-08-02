 


 # 1启动 provider

 ## 1.1先启动[Nacos](https://github.com/alibaba/nacos) 

  

 ## 1.2新增配置

| 名称| 配置 |
| --- | --- |
| Data ID | provider.properties   |
| Group | DEFAULT_GROUP |
| 配置格式 | Properties |
| 内容 | successTips=ok |

------------------





## 1.3 使用

```text
## 返回ok,  可修改nacos中successTips 内容后再试
http://localhost:11111/block 
## 返回3
http://localhost:11111/divide?a=6&b=2


```





# 2启动 Customer



```text
## 当  provider 服务正常时：
 
http://localhost:22222/block   ## 返回ok, 

http://localhost:22222/divide?a=6&b=2  ## 返回3


## 当 provider 服务宕机时

http://localhost:22222/block   ## 返回  default block

http://localhost:22222/divide?a=6&b=2 ## 返回   -2000


```



[Sentinel启动](https://github.com/alibaba/Sentinel/wiki/%E6%8E%A7%E5%88%B6%E5%8F%B0#2-%E5%90%AF%E5%8A%A8%E6%8E%A7%E5%88%B6%E5%8F%B0)



```shell 
java -Dserver.port=8080 -Dcsp.sentinel.dashboard.server=localhost:8080 -Dproject.name=sentinel-dashboard -jar sentinel-dashboard.jar

## 账号密码： sentinel/ sentinel
```



