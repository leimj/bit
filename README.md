# bit


聚集索引和非聚集索引
--
SQL SERVER提供了两种索引：聚集索引和非聚集索引。其中聚集索引表示表中存储的数据按照索引的顺序存储，检索效率比非聚集索引高，但对数据更新影响较大。非聚集索引表示数据存储在一个地方，索引存储在另一个地方，索引带有指针指向数据的存储位置，非聚集索引检索效率比聚集索引低，但对数据更新影响较小


Collections.<String> emptyList()
--
使用：List<Person> emptyPersonList = Collections.emptyList();
如果你想 new 一个空的 List ，而这个 List 以后也不会再添加元素，那么就用 Collections#emptyList() 好了。 new ArrayList() 或者 new LinkedList() 在创建的时候有会有初始大小，多少会占用一内存。

作者：高辉
链接：


this.getClass().getClassLoader().getResourceAsStream("stencilset.json");
--
获取编译路径下指定的配置文件
InputStream stencilsetStream = this.getClass().getClassLoader().getResourceAsStream("stencilset.json");
		try {
			return IOUtils.toString(stencilsetStream, "utf-8");
		} catch (Exception e) {
			throw new ActivitiException("Error while loading stencil set", e);
		}

SLF4J
--
在你的代码中使用SLF4J写日志语句的主要出发点是使得你的程序独立于任意特定的日志类库，依赖于特定类可能需要不同与你已有的配置，并且导致更多维护的麻烦。但除此之外，还要一个SLF4J API的特性使得我坚持使用SLF4J而抛弃我长期间钟爱的Lof4j的理由，是被称为占位符(place holder)，在代码中表示为“{}”的特性。


一个键多个值
--
MultiValueMap


getResourceAsStream用法
--
//使用绝对路径，否则无法读取config.properties
//InputStream inStream=new FileInputStream("F:\\android\\test\\src\\com\\ljq\\test\\resource\\config.properties");

 //ReflectTest.class.getClassLoader().getResourceAsStream(String path): 默认则是从ClassPath根下获取，path不能以’/'开头，最终是由ClassLoader获取资源。 

//InputStream inStream = ReflectTest.class.getClassLoader().getResourceAsStream("com/ljq/test/resource/config.properties");


 // ReflectTest.class.getResourceAsStream(String path)： path不以’/'开头时默认是从此类所在的包下取资源，以’/'开头则是从ClassPath根下获取。
 //其只是通过path构造一个绝对路径，最终还是由ClassLoader获取资源。
 //InputStream inStream = ReflectTest.class.getResourceAsStream("/com/ljq/test/resource/config.properties");

26 //config.properties配置文件所在目录是ReflectTest类所在子目录，才可以；否则报空指针异常
27 InputStream inStream = ReflectTest.class.getResourceAsStream("resource/config.properties");


InputStream read 三种用法
--
InputStream in = Test.class.getClassLoader().getResourceAsStream("1.xml");
		byte[]tt=new byte[in.available()];
		  int z;
		  while((z=in.read(tt, 0, tt.length))!=-1){
		   System.out.println(new String(tt,"utf-8"));
		  }

springmvc @RequestMapping(value = "${adminPath}/act/task") ${adminPath} 是如何赋值的
--
@Controller
@RequestMapping(value = "${adminPath}/cms/link")
public class LinkController extends BaseController {

这是因为你配置了propertyholder 那个属性bean引入了属性文件 这个${xxx}会在属性文件里面查，因为先启动spring 再启动springMVC 所以那个propertys属性文件是能够获取的 ，最好的一个例子是@value 注入属性文件中的值到字段里面


@ExceptionHandler
--
spring MVC 中的@ExceptionHandler可以对web的服务器端运行错误， 做统一的处理，使得http status code 从原本的500改成200， 
并去执行用@ExceptionHandler注解的方法。  前提是实现了这个方法的Class被 那个访问的Controller 继承了。

绕过web.xml中如下配置
web.xml


@InitBinder
--
springmvc表单初始化绑定



SpringContextHolder.getBean(SystemService.class);作用
--
如何取得Spring管理的bean 3种
1、servlet方式加载时，
【web.xml】
2、listener方式加载时：
【web.xml】
3、以静态变量保存Spring ApplicationContext, 可在任何代码任何地方任何时候中取出ApplicaitonContext.

@Transactional(readOnly = false)
--
oracle 只读事宜 与 没有事务
http://www.baba.io/article/66384.html
概念：从这一点设置的时间点开始（时间点a）到这个事务结束的过程中，其他事务所提交的数据

，该事务将看不见！（查询中不会出现别人在时间点a之后提交的数据）
 
应用场合：
如果你一次执行单条查询语句，则没有必要启用事务支持，数据库默认支持SQL执行期间的读一致

性； 
如果你一次执行多条查询语句，例如统计查询，报表查询，在这种场景下，多条查询SQL必须保证

整体的读一致性，否则，在前条SQL查询之后，后条SQL查询之前，数据被其他用户改变，则该次

整体的统计查询将会出现读数据不一致的状态，此时，应该启用事务支持。
【注意是一次执行多次查询来统计某些信息，这时为了保证数据整体的一致性，要用只读事务】


StringEscapeUtils类的转义与反转义方法
--
http://www.cnblogs.com/luoruiyuan/p/6025925.html
1.HTML

转义

1
System.out.println(StringEscapeUtils.escapeHtml4("<div></div>"));
输出：&lt;div&gt;&lt;/div&gt;

反转义

1
System.out.println(StringEscapeUtils.unescapeHtml4("<div></div>"));
输出：<div></div>




getBytes()
--
http://blog.sina.com.cn/s/blog_6d3fcc7e0101a4pn.html
String的getBytes()方法是得到一个系统默认的编码格式的字节数组
getBytes("utf-8")  得到一个UTF-8格式的字节数组
把String转换成bytes，各种编码转换成的bytes不同，比如UTF-8每个汉字转成3bytes，而GBK转

成2bytes，所以要说明编码方式，否则用缺省编码。


fmt:formatDate
--
<fmt:formatDate>标签用于使用不同的方式格式化日期。
<fmt:formatDate
  value="<string>"
  type="<string>"
  dateStyle="<string>"
  timeStyle="<string>"
  pattern="<string>"
  timeZone="<string>"
  var="<string>"
  scope="<string>"/>
附：http://www.runoob.com/jsp/jstl-format-formatdate-tag.html



My97DatePicker用法 
--
<input id="d11" type="text" onClick="WdatePicker()"/>


validate jquery 用法
--
http://www.cnblogs.com/hejunrex/archive/2011/11/17/2252193.html


Spring注解@Component、@Repository、@Service、@Controller区别
--
http://blog.csdn.net/zhang854429783/article/details/6785574

spring getBean
--
getBean是用来获取applicationContext.xml文件里bean的



@ModelAttribute
--
http://blog.csdn.net/li_xiao_ming/article/details/8349115



读写分离架构
--
对于数据库的读写分离，即是把所有的增、删、改操作发送到主数据库，所有查询操作发送到从

数据库，通过增加从数据库实例个数以提升查询性能。当然也可以使用noSql数据库(如

mongodb,hbase等)、搜索引擎（如lucene）等技术来做查询，关系数据库做核心数据保存，这种

方式也是基于读写分离架构。

唯一性约束 AK
--
数据库:唯一性约束 

    所谓唯一性约束（unique constraint）不过是数据表内替代键的另一个名称而已。替代键（

alternate key）可以是数据表内不作为主键的其他任何列，只要该键对该数据表唯一即可。换句

话说，在唯一列内不允许出现数据重复的现象。比方说，你可以用车辆识别代号（VIN）作为汽车

（Automobile）数据表的替代键，在汽车数据表里，主键是汽车识别号（Automobile 

Identification），这是一种由系统自动生成的ID。你可以在汽车表内对VIN施加唯一性约束，同

时再创建一个需要VIN的表。在这个新表内可以声明外键指向汽车表。这样，只要汽车表内有VIN

输入数据库就会检验VIN输入结果。这就是保证数据库内数据完整性的另一种有效的措施。 

http://www.cnblogs.com/Jaryleely/archive/2010/02/08/1665856.html


REST详解
--

SpringContextHolder 静态持有SpringContext的引用
--
该工具类主要用于：那些没有归入spring框架管理的类却要调用spring容器中的bean提供的工具

类。

java Class<?> clazz
--
Class 类的实例表示正在运行的 Java 应用程序中的类和接口。枚举是一种类，注释是一种接口

。每个数组属于被映射为 Class 对象的一个类，所有具有相同元素类型和维数的数组都共享该 

Class 对象。基本的 Java 类型（boolean、byte、char、short、int、long、float 和 double

）和关键字 void 也表示为 Class 对象。



元素据
--
元数据就是用来定义数据的数据


@Target 注解
--
Annotation（注解）就是Java提供了一种元程序中的元素关联任何信息和着任何元数据

（metadata）的途径和方法。
http://www.cnblogs.com/peida/archive/2013/04/23/3036035.html
http://www.cnblogs.com/olmlo/p/3566778.html
http://www.cnblogs.com/peida/archive/2013/04/26/3038503.html


jsr303 validator
--
https://www.ibm.com/developerworks/cn/java/j-lo-jsr303/index.html


FIFO 、LRU、LFU三种算法
--
提到缓存，有两点是必须要考虑的：
（1）缓存数据和目标数据的一致性问题。
（2）缓存的过期策略（机制）。
     其中，缓存的过期策略涉及淘汰算法。常用的淘汰算法有下面几种：
（1）FIFO：First In First Out，先进先出
（2）LRU：Least Recently Used，最近最少使用
（3）LFU：Least Frequently Used，最不经常使用
      注意LRU和LFU的区别。LFU算法是根据在一段时间里数据项被使用的次数选择出最少使用的

数据项，即根据使用次数的差异来决定。而LRU是根据使用时间的差异来决定的。
        一个优秀的缓存框架必须实现以上的所有缓存机制。例如：Ehcache就实现了上面的所有

策略。


ehcache 页面缓存
--
这样说吧，几乎所有的网站的首页都是访问率最高的，而首页上的数据来源又是非常广泛的，大

多数来自不同的对象，而且有可能来自不同的db ，所以给首页做缓存是很必要的。那么主页的缓

存策略应该怎样设计呢？我认为应该是某个固定时间之内不变的，比如说2分钟更新一次。那么这

个缓存应该做在什么地方呢？让我们来看一下，当前我们的的应用的结构一般是是page-filter-

action-service-dao-db ，这个过程中的- 的地方都是可以做缓存的地方，根据页面缓存的特征

，应该把页面缓存做到尽量靠近客户的地方，就是在page 和filter 之间，这样的优点就是第一

个用户请求之后，页面被缓存，第二个用户再来请求的时候，走到filter 这个请求就结束了，无

需再走后面的action-service-dao-db 。带来的好处是服务器压力的减低和客户段页面响应速度

的加快。了解了这些之后我们开始介绍重点。
http://www.cnblogs.com/jianjianyang/p/4953157.html


javacompiler
--
javax.tools 包是一种添加到 Java SE 6 的标准 API，可以实现 Java 源代码编译，使您能够添

加动态功能来扩展静态应用程序。


JAXB注解使用
--
http://www.cnblogs.com/fragranting/archive/2012/03/25/xml--jaxb.html


dozer
--
Dozer 是一个对象转换工具。
http://blog.csdn.net/caolaosanahnu/article/details/7928183


POJO
--
POJO的内在含义是指那些没有从任何类继承、也没有实现任何接口，更没有被其它框架侵入的

java对象。


@Aspect 注解
--
@AspectJ注解使用AspectJ切点表达式语法进行切点定义，可以通过切点函数、运算符、通配符等

高级功能进行切点定义，拥有强大的连接点描述能力。
http://blog.csdn.net/zcywell/article/details/7174746










