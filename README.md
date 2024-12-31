# torisourmmanage
java：186 基于SSM的旅游攻略管理系统
> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

旅游攻略网站主要建立一个功能完整的旅游网站。

​

游客可以通过访问本网站，来获取所需要信息，主要功能有旅游景点介绍，景点风景图片的发表，旅游线路信息的发布，自驾游攻略设计，酒店介绍。

管理员对网站后台的管理等。

用户可以通过编号、标题、景点缩略图、景点介绍等查看旅游景点；可以通过旅游路线查看各种旅游线路，其中包括路线中的编号、标题、路线所需价格、路线类型、所需的路线介绍等，以便选择自己喜欢的路线；还可以通过网站查询酒店信息和内容，其中包括通过酒店的编号、酒店名称、酒店星级、酒店位置、酒店介绍、酒店缩略图等查找到自己满意的酒店。

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：jsp

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)


# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/baf14b3a0cdeb94f30f9c8b116e56018.png)

![image20241217002008313](https://i-blog.csdnimg.cn/img_convert/99147c9eace128273c245edd5a915a78.png)

### 项目截图

前台

![ssm147旅游攻略网站设计jsp4](https://i-blog.csdnimg.cn/img_convert/6ead2553f147533770fc6af2db933433.png)

![ssm147旅游攻略网站设计jsp5](https://i-blog.csdnimg.cn/img_convert/f46c4c03c356edb1cca9a5da2f20f353.png)

![img](https://i-blog.csdnimg.cn/img_convert/7b6f69580e2e844d63c8ce2267498ba4.jpeg)

后台

![ssm147旅游攻略网站设计jsp1](https://i-blog.csdnimg.cn/img_convert/98e8f964704c6671290aabe2b599a08d.png)

![ssm147旅游攻略网站设计jsp2](https://i-blog.csdnimg.cn/img_convert/62c3a9c1d2cbc6ce9dc8f2c0f6ecf94e.png)

![ssm147旅游攻略网站设计jsp3](https://i-blog.csdnimg.cn/img_convert/70aed83694885f301306914a9199751b.png)

### 代码

```
@RequestMapping("/lists")
    public R list( StoreupEntity storeup){
       	EntityWrapper<StoreupEntity> ew = new EntityWrapper<StoreupEntity>();
      	ew.allEq(MPUtil.allEQMapPre( storeup, "storeup")); 
        return R.ok().put("data", storeupService.selectListView(ew));
    }

	 /**
     * 查询
     */
    @RequestMapping("/query")
    public R query(StoreupEntity storeup){
        EntityWrapper< StoreupEntity> ew = new EntityWrapper< StoreupEntity>();
 		ew.allEq(MPUtil.allEQMapPre( storeup, "storeup")); 
		StoreupView storeupView =  storeupService.selectView(ew);
		return R.ok("查询收藏表成功").put("data", storeupView);
    }
```
