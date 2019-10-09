# Java dairy
## --------------git---------------------
	clone
	pull(fetch merge)
	commit
	push
	checkout (new branch)
	branch
	
## --------------Naming------------------
	class TT
	variant tT
	interface TT
	Method tT
	
## --------------springboot--------------
	@Scope

	@Component 
	@Autowired
	@Service
	@Resource
	@Qualifier


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
	@Slf4j 															//private  final Logger logger = LoggerFactory.getLogger(当前类名.class);
	
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
	@Data
	@Setter @Getter
	@ToString
	@NotNull


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




