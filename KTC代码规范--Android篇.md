# KTC代码规范--Android篇

#### 前言
> **宗旨原则**：尊重技术，敬畏代码；代码虽然是给机器运行的，但却是给人读的！
> **编写目的**：在实际开发中，每个程序员所写的代码却经常自成一套，没有统一的标准规范，导致代码阅读理解困难，影响团队的开发效率及系统的质量等。对于编程开发有两点最基本的准则，首先要求是业务逻辑必须正确，能够按照设计预定功能去运行；其次是要求代码必须清晰易懂，使自己和其他的程序员能够很容易地理解代码所执行的功能等。
> 因此，一份完整并被工程师认可且严格执行的开发规范是非常必要的。此规范参考自业界标准编程规范并结合我司多年编程经验、习惯等制定，希望能对我司代码质量管控起到积极作用，同时帮助各位工程师养成良好的编程习惯，也希望各位工程师能够共同参与到该规范的完善优化计划中，将自己的开发经验等增补进去，尊重技术，敬畏代码，共同努力维护我们的代码环境。



#### 版本
| 修订日期 | 版本 | 更新内容 | 作者 |
| :---: | :---: | :---: | :---: |
| 2021.1.18 | V1.0.0 | 初始化基本的编程规范 | 杨振华 |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 
## 一、命名规范
### 基本原则
> - 对包、类、接口、方法、变量、字段等不得使用汉语拼音等进行命名
> - 避免使用长名字（最好不超过 25 个字母）
> - 避免使用相似或者仅在大小写上有区别的名字
> - 避免使用数字，但可用2代替to，用4代替for等，如：go2Jsp



### 1、包命名规范


> 包名一般以项目或模块名命名，少用缩写和长名，一律小写，连续的单词只是简单地连接起来，不使用下划线

- 确定基本包：{com.ktc}作为我司的所有客户端基本包，所有模块包、文件都从属于此包
- 包名按如下规则组成：{基本包}.{项目名}.{模块名}.{子模块名}...
> 如：
> com.ktc.filemanager
> com.ktc.filemanager.activity
> com.ktc.filemanager.fragment

- 禁止将类直接定义在基本包下，所有项目中的类、接口等都当定义在各自的项目和模块包中



### 2、类、接口命名规范


> 类、接口定义语法规范：
> [可见性][('abstract'|'final')] [Class|Interface] class_name [('extends'|'implements')][父类或接口名]{
> }
> 如：
> public class LoginActivity extends BaseActivity implemnets ActionListener {
> }

- 文件名当与其类严格相同，类名须使用能确切反映该类、接口含义、功能等的名词；接口可带前缀I或后缀able、ible、er等，但不是必须的
- 采用大驼峰式命名法，即每个单词的首字母大写。
- 尽量避免单词缩写，除非该缩写是众所周知的，比如HTML、URL等通用标识；如果类名称包含单词缩写，则单词缩写的每个字母均应大写。
- 另外类名定义同时注意区分各个组件类型，如：MainMenuActivity、SoftwareUpdateService等
- 类中方法的声明顺序（建议）：
> 构造方法
静态公共方法静态私有方法受保护方法私有方法> 继承自Object的方法



### 3、方法命名规范


> **原则**：良好的程序设计应该尽可能减小类与类之间耦合，尽量限制成员函数的可见性。
> 如果成员函数没必要公有 (public)，就定义为保护 (protected)；没必要保护 (protected)，就定义为私有 (private)
> **语法规范**：
> [可见性][('abstract'|'final')] ['synchronized'][返回值类型] method_name(参数列表)[('throws')][异常列表]{
> // 功能模块
> }
> 如：public List getList4AllUsers() throws IOException{
> }
> 若有toString(),equals(),hashCode(),colone()等重载自Object的方法，应将其放在类的最后。

- 方法的命名应采用完整的英文描述符，大小写混合使用
- 采用小驼峰命名法，即除第一个单词之外,其他单词首字母大写，方法名称的第一个单词通常采用一个有强烈动作色彩的动词
- 取值类方法使用get前缀，设值类方法使用set前缀，判断类方法使用is(has)前缀，回调类方法使用on前缀...



### 4、常量、变量命名规范


- 常量命名：采用完整的英文大写单词，在词与词之间用下划线连接，并且用final static修饰。
> 例如：private static final  String DEFAULT_VALUE= "abc";

- 成员变量和临时变量命名：采用小驼峰命名法，第一个单词首字母小写其它单词首字母大写
> 例如：字符串使用strXXX、boolean使用isXXX、hasXXX等等



### 5、控件资源id命名规范


> 命名原则：以{驼峰首部缩写}_{逻辑名称}格式命名，力求见名知意

常见View控件及其缩写如下：



| 控件 | 缩写 |
| :---: | :---: |
| LinearLayout | ll |
| RelativeLayout | rl |
| TextView | tv |
| Button | btn |
| ImageButton | imgbtn |
| ImageView | iv |
| CheckBox | cb |
| RadioButton | rb |
| DatePicker | dtpk |
| EditText | et |
| TimePicker | tmpk |
| ProgressBar | probar |
| Spinner | spn |
| ScollView | sv |
| ListView | lv |
| RecycleView | rv |
| ViewPager | vp |
| ... | ... |

### 6、res资源文件命名规范


#### 1. 布局文件命名规范
> 全部采用小写，采用下划线连接命名法



- activity layout：_activity__{名称}
> 例如：activity_videoplayer.xml

- fragment layout：_fragment__{名称}
> 例如：fragment_bluetooth.xml

- dialog layout：_dialog__{名称}
> 例如：dialog_rename.xml

- adapter item layout：item_{名称}
> 例如：item_app.xml

- view  layout：view___{名称}
> 例如：view_loading.xml

- widget layout：_widget__{名称}
> 例如：widget_weather.xml



#### 2. 图片及XML文件命名规范


- 背景图片/XML：bg_{类型}_{名称}.png或bg_{类型}_{名称}.xml
> 例如：bg_dialog_rename.png或bg_dialog_rename.xml

- 图标：ic_{类型}_{名称}png
> 例如：ic_network_wifi.png

- shape类型：shape_{类型}_{名称}.xml
> 例如：shape_btn_cancel_focus.xml

- selector类型：selector_{类型}_{名称}.xml
> 例如：selector_btn_cancle.xml

- anim类型：anim_{名称}.xml
> 例如：anim_enter_in.xml

- 其他xml类型：{类型}_{名称}.xml



#### 3. 字符串和字符串数组命名规范


- 字符串：str_{模块名称}_{名称}
> 例如：str_dialog_btn_cancel

- 字符串数组：strarr_{模块名称}_{名称}
> 例如：straar_timesetting_week

- 颜色：color_{模块名称}_{名称}
> 例如：color_dialog_tv_focus

- 尺寸：dimen_{模块名称}_{名称}
> 例如：dimen_dialog_width

- 其它资源参考上述命名规则



## 二、代码风格


### 1、类编写建议
> 原则：尽量避免使用大类和长方法

- 类的划分粒度，不可太大，造成过于庞大的单个类，也不可太细，从而使类的继承太深，为便于阅读和理解，单个函数的有效代码长度当尽量控制在100行以内（不包括注释行），当一个功能模块过大时往往造成阅读困难，因此应当使用子函数将相应功能抽取出来，这也有利于提高代码的重用度
- 单个类不宜过大，当出现此类情况时当将相应功能的代码重构到其他类中，通过组合等方式来调用，建议单个类的长度包括注释行不超过1500行
- 多使用设计模式，随时重构
- 多个类中使用相同方法时可将其方法提取到一个接口中或使用抽象类，尽量做到面向接口的设计，以提高系统的可扩展性
- 将不希望被继承的类声明成final，例如某些实用类，但不要滥用final，否则会对系统的可扩展性造成影响
- 将不希望被实例化的类的缺省构造方法声明成private
### 2、方法编写建议

- 当方法参数过多时当在每个参数后（逗号后）换行并对齐
```java
//参数对齐
public Connection getConnection(String url,
                            String userName,
                            String password)
                            throws SQLException,IOException{
    //方法执行
}
```

- 一个方法只完成一项功能，方法应尽可能的缩小其可见性。
- 避免用一个类是实例去访问其静态变量和方法
- 避免在一个较长的方法里提供多个出口，如下：
```java
//不要使用这钟方式，当处理程序段很长时将很难找到出口点
if(condition){
	return A;
}else{
	return B;
}

//建议使用如下方式
String result = null;
if(condition){
	result = A;
}else{
	result = B;
}
return result;	
```


### 3、参数和返回值编写建议

- 避免过多的参数列表，尽量控制在5个以内，若需要传递多个参数时，当使用一个容纳这些参数的对象进行传递，以提高程序的可读性和可扩展性。
- 参数类型和返回值尽量接口化，以回调形式传递状态，屏蔽具体的实现细节，提高系统的可扩展性，例如：
```java
public void joinGroup(List userList){}
public List listAllUsers(){}
```


### 4、单例类编写建议
单例类使用如下方式声明，并将其缺省构造方法声明成private：
```java
public class Singleton{
    private static Singleton instance = new Singleton();
    // 私有缺省构造方法，避免被其他类实例化
    private Singleton(){
    	//do something
    }
    
    public static Singleton getInstance(){
        if(null == instance){
        	instance = new Singleton;
        }
        return instance;
    }
}//EOC Singleton
```
单例类若需要实现序列化，则必须提供readResolve()方法，以使反序列化出来的类仍然是唯一的实例。
### 5、基本语法编写建议

- 变量定义最好通过添加空格形成对齐，同一类型的变量应放在一起
```java
//变量对齐
int count = 100;
int length = 0;
String strUserName = null;
Integer[] porductCode = new Integer(2); 
```


- 当控制语句或循环语句中的条件比较长时当换行（操作符前）、对齐并注释各条件
```java
//条件对齐
if( Condition1 //当条件一
    && Condition2 //并且条件二
    || Condition3){ //或者条件三
}
```


- 括号
1. {} 中的语句应该单独作为一行，左括号"{"当紧跟其语句后，右括号"}"永远单独作为一行且与其匹配行对齐
1. 不要在程序中出现不必要的括号，但有时为了增加可读性和便于理解，当用括号限定相应项
1. 左括号是否换行等随个人习惯而定，若换行则当与其前导语句首字符对齐



- 作用域控制符
> 若没有足够理由，不要把实例或类中变量声明为公有（public），公共(public)和保护(protected)的可见性应当尽量避免，所有的实例或变量字段都建议置为私有(private)，由获取和设置成员函数（Getter、Setter）访问。



- 控制语句

尽量不使用三目条件判断
所有if语句必须用{}包括起来,即便是只有一句：
```java
if (true){
//do something......
}

//不要使用这种
if (true)
	i = 0; 
```
当有多个else分句时请将其转成switch语句或使用子函数，
每当一个case顺着往下执行时(因为没有break语句)，通常应在break语句的位置添加注释。如：
```java
switch (condition) {
    case ABC:
        //statements;
        //继续下一个CASE
    case DEF:
        //statements;
        break;
    case XYZ:
        //statements;
        break;
    default:
        //statements;
        break;
}
```


- 循环语句

循环中必须有终止循环的条件或语句，避免死循环。
当在for语句的初始化或更新子句中使用逗号时，避免因使用三个以上变量，而导致复杂度提高。若需要，可以在for循环之前(为初始化子句)或for循环末尾(为更新子句)使用单独的语句。
因为循环条件在每次循环中多会执行一次，故尽量避免在其中调用耗时或费资源的操作，比较一下两种循环的差异：
```java
//不推荐方式：每次循环都会执行getCount()
while(index < products.getCount()){
    /*每此都会执行一次getCount()方法，
    *若此方法耗时则会影响执行效率
    *而且可能带来同步问题，若有同步需求，请使用同步块或同步方法
    */
}

//推荐方式：将操作结构保存在临时变量里，减少方法调用次数
final int count = products.getCount();
while(index < count){
    //do something
}
```


- 错误与异常
> 已检查异常必须捕捉并做相应处理，不能将已检查异常抛到系统之外去处理。
对可预见的运行时异常应当进行捕捉并处理，比如空指针等。通常，对空指针的判断不是使用捕捉NullPointException的方式，而是在调用该对象之前使用判断语句进行直接判断，如：
```java
//若不对list是否为null进行检查，则在其为null时会抛出空指针异常
if(null != list && 0 < list.size()){
    for(int i = 0; i < list.size(); i++){
        //do something
    }
}
```
另外，捕捉异常是为了处理它，不要捕捉了却什么都不处理而抛弃之，最低限度当向控制台输出当前异常，如果你不想处理它，请将该异常抛给它的调用者，建议对每个捕捉到的异常都调用printStackTrace()输出异常信息，避免因异常的湮没。
多个异常应分别捕捉并处理，避免使用一个单一的catch来处理。如：
```java
try {
	//do something
}catch(IllegalStateException IllEx){
	IllEx.printStackTrace();
	//deal with IllEx
}catch(SQLException SQLEx){
	SQLEx.printStackTrace();
	throw SQLEx; //抛给调用者处理
}finally{
	//释放资源
}
```


## 三、常见编码问题


> 性能的提升并不是一蹴而就的，而是由良好的编程积累的，虽然任何良好的习惯和经验所提升的性能都十分有限，甚至微乎其微，但良好的系统性能却是由这些习惯等积累而成，不积细流，无以成江海！



- String与StringBugffer

不要使用如下String初始化方法：
```java
String str = new String("abcdef");
```
这将产生两个对象，应当如下直接赋值：
```java
String str = "abcdef";
```
在处理可变 String 的时候要尽量使用 StringBuffer 类，StringBuffer 类是构成 String 类的基础。String 类将 StringBuffer 类封装了起来，（以花费更多时间为代价）为开发人员提供了一个安全的接口。当我们在构造字符串的时候，我们应该用 StringBuffer 来实现大部分的工作，当工作完成后将 StringBuffer 对象再转换为需要的 String 对象。比如：如果有一个字符串必须不断地在其后添加许多字符来完成构造，那么我们应该使用 StringBuffer 对象和她的 append() 方法。如果我们用 String 对象代替 StringBuffer 对象的话，将会花费许多不必要的创建和释放对象的 CPU 时间。


- 集合

避免使用Vector和HashTable等旧的集合实现，这些实现的存在仅是为了与旧的系统兼容，而且由于这些实现是同步的，故而在大量操作时会带来不必要的性能损失。在新的系统设计中不当出现这些实现，使用ArrayList代替Vector，使用HashMap代替HashTable。
若却是需要使用同步集合类，当使用如下方式获得同步集合实例：
```java
Map map = Collections.synchronizedMap(new HashMap());
```
由于数组、ArrayList与Vector之间的性能差异巨大，故在能使用数组时不要使用ArrayList，尽量避免使用Vector。


- 对象
1. 避免在循环中频繁构建和释放对象。
1. 不再使用的对象应及时销毁。
1. 如无必要，不要序列化对象。



- synchronized关键字
1. 在不需要同步操作时避免使用同步操作类
1. 尽量少用同步方法，避免使用太多的 synchronized 关键字
1. 尽量将同步最小化，即将同步作用到最需要的地方，避免大块的同步块或方法等



- final关键字
1. 将参数或方法声明成final可提高程序响应效率，故此：

注意绝对不要仅因为性能而将类、方法等声明成final，声明成final的类、方法一定要确信不再被继承或重载！

2. 不需要重新赋值的变量（包括类变量、实例变量、局部变量）声明成final
2. 所有方法参数声明成final
2. 私有(private)方法不需要声明成final
2. 若方法确定不会被继承，则声明成final



- 垃圾收集和资源释放
1. 不要过分依赖JVM的垃圾收集机制，因为你无法预测和知道JVM在什么时候运行GC。
1. 尽可能早的释放资源，不再使用的资源请立即释放。
1. 可能有异常的操作时必须在try的finally块中释放资源，如数据库连接、IO操作等：
```java
Connection conn = null;
try{
	//do something
}catch(Exception e){ //异常捕捉和处理
	e.printStackTrack();
}finally{
    //判断conn等是否为null
    if(null != conn){
    	conn.close();
    }
}
```


## 四、代码注释规范说明


### 1、类和接口注释


```java
/**  
* @Description: 调试信息工具文件
* @author: Arvin  
* @date: 2021-1-18
*/
```


### 2、方法注释：功能描述、输入参数、返回值


```java
/**
* @Description: 调试工具类实例获取方法
* @pmarm Context
* @return: LogcatUtil
*/
public static LogcatUtil getInstance(Context mContext) {
    if(null == mLogcatUtil) {
        mLogcatUtil = new LogcatUtil(mContext);
    }
    return mLogcatUtil;
}
```


### 4、 成员变量、常量注释：对应的功能定义


```java
/**
* 是否输出打印信息开关
* true：输出打印信息
* false：不输出打印信息
*/
private final static boolean DEBUG_ENABLE = false;

/**
* 默认输出log信息的Tag标识
*/
private final static String DEBUG_TAG = "k_debug";
```


### 5、 Bug修改注释格式


```java
//{{{修改人.修改日期 	修改问题说明  	start
代码片段
//修改人.修改日期 	修改问题说明  	end}}}

例如：
//{{{Arvin.20210115 	更新xxxxx  	start
代码片段
//Arvin.20210115  	更新xxxxx  	end}}}
```


## 五、文档编码格式


> 文档编码格式统一采用UTF-8格式



## 六、调试信息添加


> 添加调试信息统一采用LogUtil类中的方法来添加，主要是为了能通过开关，统一打开或关闭代码中的调试信息，方便使用。

```java
import android.util.Log;

import java.lang.reflect.Method;

/**
* @Description: 调试信息工具文件
* @author Arvin
* @date 2021.01.18
*/
public class LogUtil {
	
	private static final String TAG = "LogUtil_";

	private static boolean isEnableLog(){
		return getBoolean("ktc.log" , false);
	}

	/**
	 * @param tag , String msg
	 * @return void
	 */
	public static void i(String tag , String msg){
		if(isEnableLog()){
			Log.i(TAG + tag, msg);
		}
	}
	
	/**
	 * @param tag , String msg
	 * @return void
	 */
	public static void d(String tag , String msg){
		if(isEnableLog()){
			Log.d(TAG + tag, msg);
		}
	}
	
	/**
	 * @param tag , msg
	 * @return void
	 */
	public static void w(String tag , String msg){
		if(isEnableLog()){
			Log.w(TAG + tag, msg);
		}
	}
	
	/**
	 * @param tag , String msg
	 * @return void
	 */
	public static void e(String tag , String msg){
		if(isEnableLog()){
			Log.e(TAG + tag, msg);
		}
	}

	/**
	 * @param tag , String msg
	 * @return void
	 */
	public static void p(String tag , String msg){
		Log.i(TAG + tag, msg);
	}

	/**
	 * @description 获取boolean类型属性
	 * @param key,def
	 * @return boolean
	 */
	private static boolean getBoolean(final String key, final boolean def) {
		boolean value = false;
		try {
			Class c = Class.forName("android.os.SystemProperties");
			Method get = c.getMethod("getBoolean", String.class, boolean.class);
			value = (boolean)(get.invoke(c, key, def));
		} catch (Exception e) {
			Log.e(TAG, "getBoolean error: " + e.toString());
			e.printStackTrace();
		}
		return value;
	}
}


```
