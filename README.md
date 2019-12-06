# STUDY MESSAGE
1.springmvc配置详情（配置文件）------http://www.cnblogs.com/superjt/p/3309255.html

2.maven+spring+springmvc--------http://www.cnblogs.com/csonezp/p/3642817.html

3.web.xml配置----------------------http://blog.csdn.net/guihaijinfen/article/details/8363839

4.Maven的安装、配置及使用入门-------------http://blog.csdn.net/minword/article/details/9036459

5.禅道系统--------------------------------http://www.zentao.net/book/zentaoprohelp/122.html

6.了解springmvc 运行原理--------------http://blog.csdn.net/zhuanzhe117/article/details/45313347

7.NoClassDefFoundError: javax/servlet/jsp/jstl/core/Config问题解决----------------http://bu-choreography.iteye.com/blog/1216151

8.如果遇到copy的项目总是运行源文件的情况时，记得去检查项目properties中的web project settings 中的context root

9.jquery（jsp中script脚本）【弹出提示框的】
   <script type="text/javascript" src="jquery路径，一般放在WEB-INF中的js文件下"/>
   <script type="text/javascript">
    $(document).ready(function(){
      alert(11);
    });
   </script>

10.Maven的安装、配置及使用入门-------------http://blog.csdn.net/minword/article/details/9036459

11.禅道系统--------------------------------http://www.zentao.net/book/zentaoprohelp/122.html

12.想让数据在服务器和页面之间传输不出乱码，要保证传输过程中数据编码的一致性
   jsp页面用“UTF-8”，服务器也要用“UTF-8”编码。
   (get方法下的修改方法)服务器编码修改方式如下：tomcat----conf-----server.xml----connector标签下加上URIEconding="UTF-8"
  （常用处理乱码方式）在web.xml中加入<filter>详见springMVC5
   <!--中文乱码过滤器  -->
 <filter>
 <filter-name>encodingFilter</filter-name>
 <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
 <init-param>
  <param-name>encoding</param-name>
  <param-value>UTF-8</param-value>
 </init-param>
 <!-- 是否强制转码 -->
 <init-param>
  <param-name>forceEncoding</param-name>
  <param-value>true</param-value>
 </init-param>
 </filter>
 <!-- encoding  filter for jsp-->
 <filter-mapping>
   <filter-name>encodingFilter</filter-name>
   <url-pattern>/*</url-pattern>
 </filter-mapping>
  
13.json格式 {age："11"}
   jquery原理：在文档加载完成后动态绑定一些事件，一般用
   $(document).ready(function(){....});触发事件。获取通过id和class，class是. id是#
   获取组件<input type="text" id="text" value="...">的数据是通过 $("#text").attr("value")方式。
  前台用json传输数据，调用ajax的success回调函数
  <script type="text/javascript" src="../../js/jquery.min.js"></script>
  <script type="text/javascript">
   $(document).ready(function(){
	 $("#add").click(function(){
		var userName=$("#userName").val();
		var age=$("#age").val();
		var user={userName:userName,age:age};
		$.ajax({  //ajax使用方法
		   url:"/springMVC6/user/data/addUserJson",
		   type:"post",
		   data:user,
		   success:function(data){
				alert("userName--->"+data.userName+"age--->"+data.age);
				},
			});
	      });
    });
  </script>
  后台用接受数据后返回前台
  public void addUserJson(User user,HttpServletRequest request,HttpServletResponse response){//也可以直接用String写
    	//使用printWriter out 来吧json格式传递出去{"userName":"userName","age":"age"}
    	String result="{\"userName\":\""+user.getUserName()+"\",\"age\":\""+user.getAge()+"\"}";
    	PrintWriter out=null;
    	response.setContentType("application/json");
    	try {
			out=response.getWriter();
			out.write(result);
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

14.ajax ------------------http://tool.oschina.net/apidocs/apidoc?api=jquery

15.上传文件时spring mvc 要用到两个包commons-fileupload-1.3.1.jar和commons-io-2.4.jar

16.scrum 敏捷————————http://www.scrumcn.com/agile/scrum-knowledge-library/scrum.html#tab-id-7

17.禅道用户手册：————————http://www.zentao.net/book/zentaopmshelp.html

18.Java多线程系列--“JUC原子类”02之 AtomicLong原子类 - ----------http://www.tuicool.com/articles/uY3qIbB

19.jQuery Pagination分页插件------------http://www.zhangxinxu.com/jq/pagination_zh/

20.junit学习之junit的基本介绍-----------http://huihai.iteye.com/blog/1986568

21.Node.js Web开发（一）从零开始--------http://www.tuicool.com/articles/VzUNna

22.AngularJS 教程-----------------------http://www.runoob.com/angularjs/angularjs-tutorial.html

23.NodeJS学习资料----------------------http://sjpsega.iteye.com/blog/1698149

24.可定制的分页组件 Pagination.js-----------http://www.oschina.net/p/pagination-js

25.MyBatis学习-----------------------http://www.cnblogs.com/xdp-gacl/p/4264425.html

26.赫老师提供的底层包---------------------https://github.com/puras/mooko-common

27.http://tom.grade1986.blog.163.com/blog/static/36033556201241514731684/
   http://cloud.51cto.com/art/201411/457354.htm---------Eclipse+Maven+Spring+CXF 构建webservice 服务

28.SpringMvc注解解释-------------http://aijuans.iteye.com/blog/2160141

29.mybatis sql语句配置------------http://outofmemory.cn/code-snippet/1583/mybatis-sql-statement-configuration/

30.MyBatis实现根据输入值是否为空进行动态组合查询条件 --------------------------http://blog.sina.com.cn/s/blog_757b0e130101f95d.html
   ibatis中的方法-------------------------------http://blog.csdn.net/jzy23682891/article/details/7094788
   例如：select * from Person表  
        <dynamic prepend="where">  
                <isNotNull property="name" prepend="and">  
                    name=#name#  
                </isNotNull>  
                <isNotNull property="sex" prepend="and">  
                    sex=#sex#  
                </isNotNull>                
        </dynamic>  


31.Linux系统基本操作语句------------------------------http://www.knowsky.com/441767.html

32.Hibernate Validation各注解的用法--------------------http://tcrct.iteye.com/blog/1329823
                                                       http://ljhzzyx.blog.163.com/blog/static/38380312201342405647961/
http://docs.jboss.org/hibernate/annotations/3.4/reference/zh_cn/html/validator.html
http://my.oschina.net/zhaoqian/blog/118458

33.专门针对初学者的Node.js教程-------------------------http://www.csdn.net/article/2013-08-28/2816731-absolute-beginners-guide-to-nodejs
   [1. 配置nodejs command代理
	在nodejs command命令框里输入
	npm config set proxy http://[用户名]:[密码]@xxxx.com:8080
	[用户名][密码]为自己的东软上网代理密码，即邮箱名，密码
    2. 安装nodejs插件
	安装完nodejs需要安装相应的插件，(进入nodejs安装目录下)执行命令分别为
	npm install express -g
       （4.x版本要运行， npm install -g express-generator）
	npm install jade
	npm install mysql
	
	具体安装过程，参见：http://www.cnblogs.com/pigtail/archive/2013/01/08/2850486.html
    3. 安装grunt编译工具
	cmd 命令框中输入
	npm install grunt-cli -g
	在nodejs command 命令框下，切换到指定的工程目录下，运行npm install --save-dev
	将工程编译后，启动grunt，在浏览器打开指定端口即可访问网站
	
	npm start 
	
	具体参见：http://jingyan.baidu.com/article/93f9803fe354ede0e46f5585.html
	
    4. 服务层启动服务采取的方式是启动Application的方式
	即，运行ursa-discount/src/main/java/com/neusoft/ursa/discount/Application.java]

34.nodejs和sublime
   在sublime中选择tools--->build system--->new build system ,新建Node.sublime-build
   内容：{ "cmd": ["node", "$file"],
          "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
          "selector": "source.js",
          "shell":true,
          "encoding": "utf-8",
          "windows":
            {
              "cmd": ["node", "$file"]
             },
          "linux":
            {
              "cmd": ["killall node; node", "$file"] }
           }
    保存，退出后重新进入sublime，新建.js文件，然后ctrl+b运行。

25.postman用post方法时要添加Content-Type   application/json

26.Java代码规范、格式化和checkstyle检查配置文档------------------http://www.blogjava.net/amigoxie/archive/2014/05/31/414287.html

27.AngularJs2---------https://angular.io/

28.Linux系统ISO镜像下载地址-----------------http://www.52z.com/jiaocheng/46583.html

29.beta----------------http://ionicframework.com/docs/v2/

30.Ionic 项目启动流程：
   第一步：在NodeJs COMMAND中连接代理 npm config set proxy http://[用户名]:[密码]@xxxx.com:8080
   第二步：确认电脑           里是不是安装了python,检查方式cmd中输入Python看看是否跳转。
   第三步：npm install -g ionic@beta (如果失败找到node的安装目录node_modules/npm/npmrc编辑器打开在后面添加国内的npm镜像
           registry= http://registry.cnpmjs.org)[记得装python的时候设置系统变量C:\Python27;C:\Python27\Scripts;]
错误分析：-------------------http://www.codesec.net/view/196363.html
                             http://www.ionic.wang/start-index.html
   第四步：到指定的文件夹目录下运行 ionic serve --address IP 指定IP地址启动 ionic

31.TypeScript在Eclipse在线安装跟使用教程------------http://www.myexception.cn/eclipse/1603236.html

32.SpringMVC介绍之Validation-----------------------http://haohaoxuexi.iteye.com/blog/1812584

33.Spring3.1 对Bean Validation规范的新支持(方法级别验证)-----------------http://blog.csdn.net/majian_1987/article/details/41389157

34.Java Code Examples for javax.validation.Valid----------------------http://www.programcreek.com/java-api-examples/javax.validation.Valid

35.vi命令--------------http://wenku.baidu.com/link?url=V50o048eLkzmOoNyfZ8AkbFQkFrnuT46DhtAVEfaJ-RPxoggAya4UKTFY1Jtlr-yBukDM_bQ8wJA_G7cKHJ4oe0lzAgEXUrMk3JDSUA0EVC

36.spring MVC配置详解-----------------http://www.cnblogs.com/superjt/p/3309255.html

37.SecureCRT常用命令----------------http://blog.sina.com.cn/s/blog_61adc5aa0100ty5n.html

38.API接口规范-------------http://10.10.144.154/hegq/specification/blob/master/API%E6%8E%A5%E5%8F%A3%E8%A7%84%E8%8C%83.md

39.android ADT----------------http://blog.csdn.net/cayre/article/details/29624477

40. (一） 在 adb shell 模式下执行以下命令
     sqlite3 /data/data/com.android.providers.settings/databases/settings.db "INSERT INTO system VALUES(99,'http_proxy','10.10.26.252:1080')"
　　 在 adb shell 模式下执行查询命令
　　 sqlite3 /data/data/com.android.providers.settings/databases/settings.db "SELECT * FROM system"
　　 重新启动Android模拟器，程序可以登录http网站。
　　 备注:删除刚刚写入的配置信息方法：sqlite3 /data/data/com.android.providers.settings/databases/settings.db "DELETE FROM system WHERE _id=99"
   （二） adb shell-》getprop  （getprop会列出系统当前的各项属性）-》setprop net.dns1 192.168.1.1

41.大神的网站------------------------http://blog.csdn.net/dc_726/article/details/42784275

42.swagger 网站------------------https://github.com/swagger-api/swagger-core/wiki/Annotations#apiresponses-apiresponse

43.Android SDK Android NDK Android Studio 官方下载地址------------------------http://www.cnblogs.com/yaotong/archive/2011/01/25/1943615.html

44.Rxjava + retrofit + dagger2 + mvp搭建Android框架-----------------http://www.aichengxu.com/view/24568437

45.Rxjava + retrofit + dagger2 + mvp搭建Android框架github-----------------https://github.com/baiiu/ZhihuDaily

46.RxJoke:一个集成Rxjava,Retrofit,MVP及Dagger2的开源项目----------------http://www.open-open.com/lib/view/open1461503869624.html

47.Retrofit 2.0: The biggest update yet on the best HTTP Client Library for Android----------------https://inthecheesefactory.com/blog/retrofit-2.0/en

48. Android Annotations浅析 ------------------http://blog.csdn.net/ljphhj/article/details/37601173

49. android studio配置AndroidAnnotations ----------------http://blog.csdn.net/wa991830558/article/details/41647781

50.AndroidAnnotations简明指南--------------------http://www.cnblogs.com/onespieces/p/5398390.html

51.android 图表 --------------------------------https://github.com/PhilJay/MPAndroidChart
               ---------------------------------http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2014/0506/1614.html

52。android tabwidget 颜色-------------------http://www.tuicool.com/articles/zIjqeq

53.android日期选择器 -----------------------http://blog.csdn.net/wwj_748/article/details/38778631

54.timePicker 带秒----------------------------https://github.com/IvanKovac/TimePickerWithSeconds

55. Android中ViewPager的简单使用（底部圆点）------------------------------http://blog.csdn.net/buptdavid/article/details/42737275

56.android状态栏一体化(沉浸式状态栏)--------------------------http://blog.csdn.net/jdsjlzx/article/details/41643587

57.android 学习searchView-风格调整----------------http://www.cnblogs.com/zhangshuli-1989/p/zhangshuli_searchview_1568131.html

58.BlurBehind 磨砂玻璃效果：------------------https://github.com/faradaj/BlurBehind

59.android 小红点提示----------------------------https://github.com/jgilfelt/android-viewbadger

60。 mvp框架学习实战代码（配合retrofit+dagger2+rxjava）------------------http://blog.csdn.net/sw5131899/article/details/51860922

61。MVPArms--------------------https://github.com/JessYanCoding/MVPArms/wiki

62。Android 自定义View修炼-仿QQ5.0 的侧滑菜单效果的实现----------------------http://www.cnblogs.com/JczmDeveloper/p/4178227.html

63。收集android上开源的酷炫的交互动画和视觉效果：Interactive-animation-----------http://www.open-open.com/lib/view/open1411443332703.html

64.rxJava---------https://zhuanlan.zhihu.com/p/23584382
