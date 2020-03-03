# Java dairy
## --------------git---------------------
	clone
	pull(fetch merge)
	commit
	push
	checkout (new branch) //切换分支到工作台。 
	checkout -- filename // 恢复文件
	branch
	git fetch origin develop:develop   //取回所有分支（branch）的更新。如果只想取回特定分支的更新，可以指定分支名
	merge origin/master
	rebase origin/master
	remote -v //查看远端url

## ---------------JavaLang---------------
	@Override	//检查该方法是否是重写方法。如果发现其父类，或者是引用的接口中并没有该方法时，会报编译错误
	@Deprecated  //标记过时方法。如果使用该方法，会报编译警告
	@SuppressWarnings //指示编译器去忽略注解中声明的警告
	@Retention //标识这个注解怎么保存，是只在代码中，还是编入class文件中，或者是在运行时可以通过反射访问。
	@Documented //标记这些注解是否包含在用户文档中
	@Target //标记这个注解应该是哪种 Java 成员
	@Inherited // 标记这个注解是继承于哪个注解类(默认 注解并没有继承于任何子类)
	
	
## --------------Naming------------------
	class TT
	variant tT
	interface TT
	Method tT
	
## --------------springboot--------------
	@Scope

	@Component 	
	@Service
	
	
	
	@Resource	
		默认按照名称装配，当找不到与名称匹配的bean才会按照类型装配，可以通过name属性指定，如果没有指定name属性，当注解标注在字段上，即默认取字段的名称作为bean名称寻找依赖对象，当注解标注在属性的setter方法上，即默认取属性名作为bean名称寻找依赖对象. 
		注意：如果没有指定name属性，并且按照默认的名称仍然找不到依赖的对象时候，会回退到按照类型装配，但一旦指定了name属性，就只能按照名称装配了. 
		建议使用@Resource。 
		
	@Qualifier("classname")
	@Autowired 默认按照类型装配，默认情况下它要求依赖对象必须存在如果允许为null，可以设置它required属性为false，如果我们想使用按照名称装配，可以结合@Qualifier注解一起使用


	@ComponentScan
	@SpringBootApplication

	@Controller
	@RestController
	@RequestMapping
	@ResponseBody
	@RequestParam

	@Configuration
	@Bean

	@value
	@Profile               //指定使用那套配置
	
	@ContextConfiguration
	@Import 					//合并其他的Config类
	@Slf4j 															//private  final Logger logger = LoggerFactory.getLogger(当前类名.class);
	
	@PathVariable						
			- @GetMapping("/resetPwd/{userId}")
			- public String resetPwd(@PathVariable("userId") Long userId, ModelMap mmap)
			- {
			- mmap.put("user", userService.selectUserById(userId));
			- return prefix + "/resetPwd";
			- }
	
	
	@PostMapping
	@GetMapping
	@RequestParam(required,defaultvalue,value)
	@CookieValue
	@RequestHeader
	@ModelAttribute绑定请求参数到命令对象
	
	
## --------------JUnit-----------------------
	@RunWith
	@Test
	
## --------------springredis-----------------
	@EnableRedisHttpSession

## --------------springcloud------------------
	@HystrixCommand 
	@EnableHystrix
	@EnableDiscoveryClient
	@LoadBalanced


## ---------------maven----------------
	repositories
	pluginRepository

	modules
	parent

	scope - (compile test runtime provided system import )

## --------------组件-----------------
	Consul	
	Erueka
	Hystrix
	
	Feign
	Ribbon
	LoadBalancerClient
	RestTemplate
	
	
## -------------lombok----------------
	@Data //注解在类上, 为类提供读写属性, 此外还提供了 equals()、hashCode()、toString() 方法
	@NonNull //: 注解在参数上, 如果该类参数为 null , 就会报出异常,  throw new NullPointException(参数名)
	@Setter @Getter //注解在类上, 为类提供读写属性
	@ToString  //注解在类上, 为类提供 toString() 方法
	@NotNull
	@NoArgsConstructor, @RequiredArgsConstructor, @AllArgsConstructor : 注解在类上, 为类提供无参,有指定必须参数, 全参构造函数




## -------------Swagger----------------
	@ApiModel
	@ApiModelProperty


## ---------------CAP-----------------
	Consensus
	Available
	Partition


## ----------------Erueka---------------
	@EnableEurekaClient
	@EnableEurekaServer

## ---------------Hystrix---------------
	@EnableHystrix
	@RestTemplate
	

## ---------------kafka-----------------
	
	
	
## --------------ELK--------------------
	ElasticSearch
	LogStash
	Kibana
	FileBeat
	
	
## ---------------GateWay-------------

	
	
	
## ---------------Java Lang-----------
	interface default
	
	
## ---------------mybatis-plus--------
	@TableName(value="tb_employee")
	@TableId(value = "id",type = IdType.AUTO)

	//若没有开启驼峰命名，或者表中列名不符合驼峰规则，可通过该注解指定数据库表中的列名，exist标明数据表中有没有对应列
	@TableField(value ="last_name" ,exist=true)
	DAO BaseMapper<Employee>

	insert
	update(ById, AllConlumnById, )
	Select(ById, One ,ByMap, BatchIds, Page ,List)
	Delete(ById,ByMap,BatchIds)

	EntityWrapper<Employee>(eq|orderby|last|or|and|between|lt|gt|
	@TableField(fill = FieldFill.INSERT_UPDATE)//插入和更新时填充

	MetaObjectHandler 
		insertFill
		updateFill
		
	AutoSqlInjector 
		inject


	ActiveRecord
		Model
		
	代码逆向，自动生成自动生成Entity，DAO，


## -------------------application.properties-------------------------------------
	优先级
	命令行
	boosttrap
	application
	
	
## -------------------http-------------------------------------------------------
	
	### GET&POST
		GET产生一个TCP数据包；
		POST产生两个TCP数据包。
		对于GET方式的请求，浏览器会把http header和data一并发送出去，服务器响应200（返回数据）；
		而对于POST，浏览器先发送header，服务器响应100 continue，浏览器再发送data，服务器响应200 ok（返回数据）。
		
		GET请求会被浏览器主动cache，而POST不会，除非手动设置。
		
		Get 请求中有非 ASCII 字符，会在请求之前进行转码，POST不用，因为POST在Request body中，通过 MIME，也就可以传输非 ASCII 字符。
		
		在网络环境好的情况下，发一次包的时间和发两次包的时间差别基本可以无视。而在网络环境差的情况下，两次包的TCP在验证数据包完整性上，有非常大的优点。但并不是所有浏览器都会在POST中发送两次包，Firefox就只发送一次
		
		首先是"GET方式提交的数据最多只能是1024字节"，因为GET是通过URL提交数据，那么GET可提交的数据量就跟URL的长度有直接关系了。而实际上，URL不存在参数上限的问题，HTTP协议规范没有对URL长度进行限制。这个限制是特定的浏览器及服务器对它的限制。IE对URL长度的限制是2083字节(2K+35)。对于其他浏览器，如Netscape、FireFox等，理论上没有长度限制，其限制取决于操作系统的支持。
		
		
	### PUT & POST
		PUT 不用等待
		POST 需要等待
		而HTTP中的GET，POST，PUT，DELETE就对应着对这个资源的查，改，增，删4个操作


## ----------------------rabbit mq-------------------------------------------------
	connection (host,port,virtual_host,channel_max,frame_max,heartbeat,socket_timeout,blocked_connection_timeout,credential)
	channel
	exchange
	ruote_key
	queue
	body


## -------------------------fastjson-1.2.56.jar! com.alibaba.fastjson.JSON------------
	parseObject:259  //String 转 对象
	
	
	
	
	
	
	
	
	
## -------------------------nginx ------------------------------
	调试选项:
		worker_processes  1;    
		error_log  logs/error.log debug; #  记录调试日志   
		master_process  off;             #  单进程模式  
		daemon          off;  
		
	语法规则：location [=|~|~*|^~] /uri/ { … }
		= 开头表示精确匹配
		^~ 开头表示uri以某个常规字符串开头，理解为匹配 url路径即可。nginx不对url做编码，因此请求为/static/20%/aa，可以被规则^~ /static/ /aa匹配到（注意是空格）。以xx开头
		~ 开头表示区分大小写的正则匹配                     以xx结尾
		~* 开头表示不区分大小写的正则匹配                以xx结尾
		!~和!~*分别为区分大小写不匹配及不区分大小写不匹配 的正则
		/ 通用匹配，任何请求都会匹配到。
	
	
	在nginx的location和配置中location的顺序没有太大关系。正location表达式的类型有关。相同类型的表达式，字符串长的会优先匹配。
	以下是按优先级排列说明：
		等号类型（=）的优先级最高。一旦匹配成功，则不再查找其他匹配项。
		^~类型表达式。一旦匹配成功，则不再查找其他匹配项。
		正则表达式类型（~ ~*）的优先级次之。如果有多个location的正则能匹配的话，则使用正则表达式最长的那个。
		常规字符串匹配类型。按前缀匹配。
		
		
## ------------------------openssl----------------------------------------------

	#公钥加密私钥解密，私钥签名公钥验签

	openssl genrsa -out  private.pem 1024 ##product private key
	openssl rsa -in private.pem -pubout -out public.pem ##product public key according private key
	
	
	##file encryption
	
	openssl rsautl -encrypt -in test.txt -inkey private.pem -out encrypted.txt ##	rsa
	openssl rsautl -encrypt -in test.txt -inkey -pubin public.pem -out encrypted.txt ## rsa public only
	#解密的话只要将 －encrypt 改为 －decrypt就好，当然文件对象改变一下 
	
	
	


## --------------------------golang-------------------------------------------
	第一步：现在自己的GOPATH的src目录下创建golang.org/x目录
	第二步：在终端/cmd中cd到GOPATH/src/golang.org/x目录下
	第三步：执行git clone https://github.com/golang/tools.git tools命令
	第四步：执行git clone https://github.com/golang/lint.git命令
	第五步：按下Ctrl/Command+Shift+P再次执行Go:Install/Update Tools命令，在弹出的窗口全选并点击确定，这一次的安装都会SUCCESSED了。

## ------------------------ffmpeg---------------------------------------------
	参数
	-i input
	-b:v
	-r
	-c:v
	-s
## --------------------------Linux--------------------------------------------
	### python：
		wget https://bootstrap.pypa.io/get-pip.py 
		sudo python3 get-pip.py