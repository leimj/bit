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










