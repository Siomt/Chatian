# Java部分
## 1.GC是什么? 为什么要有GC?

GC是垃圾收集的意思（Gabage Collection）,内存处理是编程人员容易出现问题的地方，忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java 提供的GC功能可以自动监测对象是否超过作用域从而达到自动回收内存的目的，Java语言没有提供释放已分配内存的显示操作方法。

## 2.XML包括哪些解释技术，区别是什么？ 

DOM和SAX
DOM将文档解析成一颗文档树，可在节点上进行遍历、增加、修改和删除。一次性读入内存，对内存消耗大。
SAX至上而下解析文档，以事件进行驱动。不会一次性读入内存，对内存消耗小，不能任意读取节点，并且不能对节点进行增加、修改和删除。

## 3.switch语句能否作用在byte上，能否作用在long上，能否作用在String上? 

switch能作用在byte、char、short和int上，JDK1.7后可以作用在String上。

## 4.”==”和equals方法究竟有什么区别？ 

==和equals都可以比较地址。==是运算符，equals是方法，方法可以通过重写改变其行为，如String的equals就是比较字符串内容。

## 5.构造方法能否被重写和重载？ 

构造方法不能被重写但是能被重载。

## 6.面向对象的特征有哪些？ 

封装、继承、多态和抽象。

## 7.抽象类和接口的区别？ 

1).抽象类是abstract class修饰，接口是interface修饰。
2).抽象类可以有任意类型的属性，接口只能有静态常量修饰的属性。
3).抽象类可以有普通方法和抽象法方法，接口的方法都是抽象方法。
4).抽象类和接口都不能实例化，但是抽象类有构造方法，接口没有构造方法。
5).抽象类只能单根继承，接口可以多重实现。

## 8.内部类可以引用它的包含类的成员吗？有没有什么限制？

可以引用。如果需要指定当前类时要用外部类.this来引用。如果引用局部变量，需要将局部变量指定为final。

## 9.String s = new String(“xyz”);创建了几个String Object? 二者之间有什么区别？

2个对象。”xyz”创建在字符串常量池中，new String()创建在堆中。

## 10.try {}里有一个return语句，那么紧跟在这个try后的finally {}里的code会不会被执行，什么时候被执行，在return前还是后?

会在return前执行。

## 11.Integer与int的区别

Integer为包装类，int是基本数据类型。包装类拥有方法和属性，基本数据类型不具备。包装类可以通过intValue来转换成基本数据类型，也可以通过new Integer()将基本数据类型转换为包装类。在JDK1.5后，包装类和基本数据类型可以实现自动转换。

## 12.sleep()和wait()有什么区别?

sleep是Thread类的方法，wait是Object类的方法。
sleep是自动唤醒，wait需要其他线程来唤醒。
sleep不会释放同步锁，wait会释放同步锁。
sleep可以用在任意方法中，wait只能用在同步方法或同步块中。
Sleep（）不会释放对象锁到时自动恢复， wait（）会释放对象锁 进入等待此对象的等待锁定池 发出notify（）方法后 才进入等待锁定池准备对象锁的获 取进入运行状态

## 13.同步和异步有何异同，在什么情况下分别使用他们？

同步指同一时间只能一个线程执行该方法，其他线程需要等待。异步指多个线程可以同时执行某个方法，并共享同一资源。
同步可以让访问的资源具有安全性，因为同一时间只能一个线程对其进行访问。但是效率不高。
异步对访问的资源会造成不稳定性，比如多个线程同时访问一个资源，一个在修改、一个在删除、一个在读取，这样可能会造成资源的混乱。但是由于同时运行， 执行效率得到提高。

## 14.启动一个线程是用run()还是start()?

start()方法启动线程，run方法是线程执行的主方法。

## 15.java中有几种类型的流？JDK为每种类型的流提供了一些抽象类以供继承，请说出他们分别是哪些类？

java中有三种流，分别是字节流（InputStream、OutputStream）、字符流（Reader、Writer）、对象流（ObjectInputStream、 ObjectOutputStream）。

## 16.字节流与字符流的区别？

字节流用于读取或写出二进制数据，比如图片、影像等数据。
字符流用于读取或写出字符数据，比如传输字符串。
所有的数据都可以通过字节流来进行处理，不过如果是字符数据，用字节流还需要进行转换后传输，如果使用字符流可以方便数据的转换。

## 17.error和exception有什么区别?

error是系统错误，代码不能处理的错误，比如内存溢出、堆栈溢出等。
exception是程序异常，可以通过代码try-catch进行处理，比如空指针异常，数组越界等。

## 18.谈谈final,finally,finalize的区别？

final是修饰符，可以修饰类（不能被继承）、属性（常量）、和方法（不能被重写）。
finally是异常处理块中的代码块，表示无论如何都会执行的代码块。
finalize是Object类的方法，该方法在对象被垃圾回收之前执行的方法。

## 19.当一个线程进入一个对象的一个synchronized方法后，其它线程是否可进入此对象的其它方法?

如果其他方法没有加synchronized的话是可以进入的。

## 20.当一个对象被当作参数传递到一个方法后，此方法可改变这个对象的属性，并可返回变化后的结果，那么这里到底是值传递还是引用传递?

java中只有值传递，如果传递的对象，实际也是传递该对象的地址。

## 21.作用域public,private,protected,以及不写时的区别

public公共修饰符，表示任意类都可以访问。
protected为受保护的修饰符，表示同类、同包以及不同包但是父子关系的是可以访问。
不写表示默认修饰符，或者称为package修饰符，该修饰符表示只有同类或同包下的类可以访问，出了这个包就不能访问了。
private为私有修饰符，表示只有同类中可以访问，出了这个类就不能访问了。

## 22.用最有效率的方法算出2乘以8等於几 2《 3

将2的二进制向左移3位。java中用<<来移位。

## 23.heap和stack有什么区别。

heap表示堆，stack表示栈。堆中放对象，栈中放引用变量。
堆空间是一个无序的空间，栈是先进后出的结构。

## 24.运行时异常与一般异常有何异

运行时异常是指继承于RuntimeException的异常，这些异常在编译时可以不进行处理，当运行时如果出现问题才会抛出。如NullPointException、 ArrayIndexOutOfBoundsException
一般异常也称为编译时异常，这些异常是继承Exception但又不属于RuntimeException的子类，如果程序中出现这些异常，在编译时必须进行捕获或抛出，否 则编译无法通过。如IOException、FileNotFoundException

## 25.垃圾回收的优点和原理。并考虑2种回收机制

Java语言中一个显著的特点就是引入了垃圾回收机制，使c++程序员最头疼的内存管理的问题迎刃而解，它使得Java程序员在编写程序的时候不再需要考虑内存 管理。由于有个垃圾回收机制，Java中的对象不再有”作用域”的概念，只有对象的引用才有”作用域”。垃圾回收可以有效的防止内存泄露，有效的使用可以使用 的内存。垃圾回收器通常是作为一个单独的低级别的线程运行，不可预知的情况下对内存堆中已经死亡的或者长时间没有使用的对象进行清楚和回收，程序员不能 实时的调用垃圾回收器对某个对象或所有对象进行垃圾回收。回收机制有分代复制垃圾回收和标记垃圾回收，增量垃圾回收。

## 26.描述一下JVM加载class文件的原理机制?

JVM中类的装载是由ClassLoader和它的子类来实现的,Java ClassLoader 是一个重要的Java运行时系统组件。它负责在运行时查找和装入类文件的类。

## 27.是否可以从一个static方法内部发出对非static方法的调用？

不能，除非先创建非static方法所在类的对象。

## 28.什么是java序列化，如何实现java序列化？

序列化就是一种用来处理对象流的机制，所谓对象流也就是将对象的内容进行流化。可以对流化后的对象进行读写操作，也可将流化后的对象传输于网络之间。序 列化是为了解决在对对象流进行读写操作时所引发的问题。
序列化的实现：将需要被序列化的类实现Serializable接口，该接口没有需要实现的方法，implements Serializable只是为了标注该对象是可被序列化 的，然后使用一个输出流(如：FileOutputStream)来构造一个ObjectOutputStream(对象流)对象，接着，使用ObjectOutputStream对象的 writeObject(Object obj)方法就可以将参数为obj的对象写出(即保存其状态)，要恢复的话则用输入流。

## 29.Anonymous Inner Class(匿名内部类)是否可以extends(继承)其它类，是否可以implements(实现)interface(接口)？

匿名内部类可以继承类或实现接口，但不是显示的使用extends或implements来继承或实现。

## 30.ArrayList和Vector的区别,HashMap和Hashtable的区别？

ArrayList是JDK1.2的集合类并且线程不安全，Vector是1.0的集合类并且线程安全，二者用法类似。
HashMap线程不安全且能放空键或空值，Hashtable线程安全且不能放空键或空值。

## 31.String 和StringBuffer有什么差别？在什么情况下使用它们？

String字符串的基本类，该字符串是不可变的。StringBuffer是利用堆来存储字符串，并且可以对字符串的内容进行改变。

## 32.new一个类对象和使用类名创建一个对象有什么区别？二者使用时应该注意什么？

new对象是最常见的创建对象的方式，利用类模板是通过反射来创建对象。虽然new对象时在底层也会通过类模板来创建对象，但是new对象的效率要比直接通过类 模板创建对象的方式要高。
但是使用类模板的方式可以让程序的灵活性提高。

## 33.LinkedList和ArrayList的区别？

1）LinkedList是链表结构的集合，ArrayList数组结构的集合。
2）LinkedList在中间或前面增加或删除数据时效率比ArrayList高。
3）LinkedList在最后添加或删除数据时效率比ArrayList低。
4）遍历数据时ArrayList效率高于LinkedList。

## 34.介绍JAVA开发中常用的Collection FrameWork（集合框架）?

Java中集合框架分为Collection和Map接口，Collection接口下的集合每个元素都由一个值组成，Map接口下的集合类每个元素都是由键值对组成。
Collection接口下面有List和Set接口，List接口下常见的类有ArrayList、LinkedList、Vector。它们中的元素可以重复，并且是有序的。Set接口下常 见的类有HashSet、TreeSet。它们中的元素不能重复，并且是无序的。

## 35.在异常当中 throw和throws 有什么区别和联系？

throw是在代码中抛出一个异常，后面跟的是异常对象，虚拟机运行到这里时会立即引发一个异常。
throws是写在方法声明上的，表示声明该方法可能会抛出异常，后面跟的是异常类型。调用该方法的时候可以选择处理它或继续往外抛。

## 36.重载和重写的区别

重载是指在一个类中，两个或两个以上的方法具有相同方法名和不同参数列表，则表示这些方法为重载方法。
重写是指在父类和子类中，子类的方法和父类的方法具有相同方法名、相同参数列表、相同返回类型、子类的访问修饰符范围不小于父类的访问修饰符范围，异常 的类型和个数不大于或多于父类的异常类型和个数，则表示该方法为重写方法。换句话说重载方法是区分同一个类中相同方法名的方法，重写方法是找到父类相同 方法名的方法并重新改变方法的行为。

## 37.Java中try catch finally的执行顺序

先执行try中代码发生异常执行catch中代码，最后一定会执行finally中代码

## 38.内存泄露的原因：

资源对象没关闭。
如Cursor、File等资源。他们会在finalize中关闭，但这样效率太低。容易造成内存泄露。
SQLiteCursor，当数据量大的时候容易泄露
使用Adapter时，没有使用系统缓存的converView。
即时调用recycle（）释放不再使用的Bitmap。
适当降低Bitmap的采样率，如：
BitmapFactory.Options options = newBitmapFactory.Options();
options.inSampleSize = 2;//图片宽高都为原来的二分之一，即图片为原来的四分之一
Bitmap bitmap =BitmapFactory.decodeStream(cr.openInputStream(uri), null, options); preview.setImageBitmap(bitmap);
使用application的context来替代activity相关的context。
尽量避免activity的context在自己的范围外被使用，这样会导致activity无法释放。
注册没取消造成内存泄露
如：广播
集合中的对象没清理造成的内存泄露我们通常把一些对象的引用加入到了集合中，当我们不需要该对象时，并没有把它的引用从集合中清理掉，这样这个集合就会 越来越大。如果这个集合是static的话，那情况就更严重了。
Handler应该申明为静态对象， 并在其内部类中保存一个对外部类的弱引用。如下：

```

	static class MyHandler extends Handler{

 	WeakReference<Activity > mActivityReference;

	 MyHandler(Activity activity){ 
		  mActivityReference= new WeakReference<Activity>(activity);
	 }

	@Override
	public void handleMessage(Message msg){
	 	final Activity activity = mActivityReference.get();
	 		if (activity != null){
	  		 	mImageView.setImageBitmap(mBitmap);
			}
		}
	}


```
## 39.Iterator和Enumeration的不同

函数接口不同
Enumeration只有2个函数接口。通过Enumeration，我们只能读取集合的数据，而不能对数据进行修改。 Iterator只有3个函数接口。Iterator除了能读 取集合的数据之外，也能数据进行删除操作。
Iterator支持fail-fast机制，而Enumeration不支持。 Enumeration 是JDK 1.0添加的接口。使用到它的函数包括Vector、Hashtable等类，这些类 都是JDK 1.0中加入的，Enumeration存在的目的就是为它们提供遍历接口。Enumeration本身并没有支持同步，而在Vector、Hashtable实现 Enumeration时，添加了同步。而Iterator 是JDK 1.2才添加的接口，它也是为了HashMap、ArrayList等集合提供遍历接口。
Iterator是支持fail-fast 机制的：当多个线程对同一个集合的内容进行操作时，就可能会产生fail-fast事件。
ail-fast 机制是java集合(Collection)中的一种错误机制。当多个线程对同一个集合的内容进行操作时，就可能会产生fail-fast事件。例如：当某一个线 程A通过iterator去遍历某集合的过程中，若该集合的内容被其他线程所改变了；那么线程A访问集合时，就会抛出ConcurrentModificationException异 常，产生fail-fast事件。

## 40.接口的注意点

接口中的字段全部默认为 public static类型。
接口中的方法全部默认为 public类型。
接口中可以申明内部类，而默认为public static，正因为是static，只是命名空间属于接口，代码逻辑不属于接口。所以不违法接口定义。
接口本身可以申明为public或者缺省。
抽象类继承自某接口。如果在抽象类中实现了父类（接口）中的方法，在其子类可以不用实现，否则在子类必须实现。

## 41.final方法

将方法声明为final那有两个原因，第一就是说明你已经知道这个方法提供的功能已经满足你要求，不需要进行扩展，并且也不允许任何从此类继承的类来覆写这个方法，但是继承仍然可以继承这个方法，也就是说可以直接使用。第二就是允许编译器将所有对此方法的调用转化为inline调用的机制，它会使你在调用final方法时，直接将方法主体插入到调用处，而不是进行例行的方法调用，例如保存断点，压栈等，这样可能会使你的程序效率有所提高，然而当你的方法主体非常庞大时，或你在多处调用此方法，那么你的调用主体代码便会迅速膨胀，可能反而会影响效率，所以你要慎用final进行方法定义。