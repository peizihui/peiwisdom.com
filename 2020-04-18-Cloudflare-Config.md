#  2020-04-18 Cloudflare Config
Cloudflare以向客户提供网站安全管理、性能优化及相关的技术支持为主要业务。通过基于反向代理的内容分发网络(CDN, Content Delivery Network)、任播(Anycast)技术<sup> [1]</sup>  、基于nginx+lua架构的Web应用防火墙(WAF, Web Application Firewall)<sup> [2]</sup>  及分布式域名解析服务(Distributed Domain Name Server)等技术，Cloudflare可以帮助受保护站点抵御包括分布式拒绝服务攻击(DDoS, Distributed Denial of Service)在内的大多数网络攻击，确保该网站长期在线，同时提升网站的性能、访问速度以改善访客体验。

##  作用：


#  1. 注册   
[http://cloudflare.com/](http://cloudflare.com/)

# 2. Account Home

![image.png](https://upload-images.jianshu.io/upload_images/8922740-12df544dca6e3cf1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 3.  Basic Function


![image.png](https://upload-images.jianshu.io/upload_images/8922740-58ac0d6ca24fc86e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#  4. DNS


![image.png](https://upload-images.jianshu.io/upload_images/8922740-3c7c634b2443aaff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


# 5. Caching


![image.png](https://upload-images.jianshu.io/upload_images/8922740-ad8b8625b9f5e209.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 ## 5.1 cache level 文档


[cache level](https://support.cloudflare.com/hc/zh-cn/articles/200168256-Cloudflare-%E7%9A%84%E7%BC%93%E5%AD%98%E7%BA%A7%E5%88%AB%E6%98%AF%E4%BB%80%E4%B9%88-)



![image.png](https://upload-images.jianshu.io/upload_images/8922740-7aa0abcdc8a7334a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 5.2 Always Online

![image.png](https://upload-images.jianshu.io/upload_images/8922740-bcc5572f782a7f31.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 6. page rule


![image.png](https://upload-images.jianshu.io/upload_images/8922740-7acc329eaae397db.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![image.png](https://upload-images.jianshu.io/upload_images/8922740-cae885f9ec05864f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 7.  域名托管配置步骤；

## 7.1   Add DNS Record;
![image.png](https://upload-images.jianshu.io/upload_images/8922740-1f14219df62de9ed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 7.2   confif nginx server name ;

![image.png](https://upload-images.jianshu.io/upload_images/8922740-d893504875808c80.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



7.3 修改 DNS配置；把域名换成cloudflare的域名；


cleo.ns.cloudflare.com

nadia.ns.cloudflare.com

![image.png](https://upload-images.jianshu.io/upload_images/8922740-a64f6a179451b864.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#8 自动重写成https

若https 没有配置，则不能使用

![image.png](https://upload-images.jianshu.io/upload_images/8922740-7ee3cfe76492e020.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 9. cloudflare 证书


https://support.cloudflare.com/hc/zh-cn/articles/115000479507

## 9.1  



![image.png](https://upload-images.jianshu.io/upload_images/8922740-b119cb267eeaa6d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 9.2  生成证书，证书被cloudflare管理，无需再次在nginx配置；

![image.png](https://upload-images.jianshu.io/upload_images/8922740-40175875df891ba7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![image.png](https://upload-images.jianshu.io/upload_images/8922740-17cce07f08066cb8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##9.3 访问验证,查看证书

![image.png](https://upload-images.jianshu.io/upload_images/8922740-c3dac55b2f338a90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


# 总结

当初为了提高网站访问速度也摸索了很久，希望对各位能有帮助，若有疑问可以留言，可以一起学习交流。