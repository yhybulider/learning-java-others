# Notes for c++ learning

[TOC]



**程序根据什么特征来区分调用哪个重载函数?**
只能靠参数而不能靠返回值类型的不同来区分重载函数。
编译器根据参数为每个重载函数产生不同的内部标识符

* 在Visual Studio .Net开发环境中，在代码编辑器内输人对象的名称后将自动显示出对应的属性、方法、事件列表，以方便选择和避免书写错误，这种技术被称为_智能感知_
* 一个解决方案可以有多个项目
* CLR是公共语言运行库
* 跟踪句柄——（gcnew）相当于c语言的指针
* 引用不分配内存——不能为空，因为不是定义一个变量，只表示是该用户名是目标变量名的一个别名。 引用前面用&符号，引用使用很简单比较指针（某一变量的位置）。 引用是给某一变量多取一个别名，当建立引用时，程序用另一个变量或对象目标的名字初始化它。缺点是定义之后不能改变8
* 托管代码和非托管代码：为CLR而编写以及使用CLR服务的代码叫"托管代码"，而那些未使用CLR服务的代码（也就是你多年以来一直编写的代码），依赖于平台和语言叫"非托管代码"。
* rand()_生成伪随机数；rand()%max表示产生0-max的随机数；a+rand()%(b-a+1)表示产生【a,b】之间的整数。产生不重复的随机数
* array与arraylist:array是本地的程序组件或者数据结构，但是arraylist是一个来自Java集合类的类，一个接口（API）；array仅提供一个length属性来告诉你array里有多少个插槽，例如可以存储多少个元素。但arraylist提供一个size（）方法来告诉你当前时间点存储了多少个元素；array还可以设置多维数组，但是arraylist并不支持你指定维度。
* 值类型的对象包含的是自身的数据内容。引用是引用对象的跟踪句柄，包含的是对象的地址
* 面向对象：类的几个特殊函数：类的构造函数、复制构造函数、析构函数、终结器，构造函数：C++规定，一个类的构造函数必须与相应的类同名，它可以带参数，也可以不带参数，与一般的成员函数定义相同，可以重载，也可以有默认的形参值。构造函数不能指定函数返回值的类型，也不能指定为void类型。默认构造函数：实际上，在类定义时，如果没有定义任何构造函数，则编译自动为类隐式生成一个不带任何参数的默认构造函数，由于函数体是空块，因此默认构造函数不进行任何操作，仅仅为了满足对象创建时的语法需要。
* **与构造函数相对应的是析构函数。**析构函数是另一个特殊的C++成员函数，它只是在类名称前面加上一个“～”符号（逻辑非），以示与构造函数功能相反。_每一个类只有一个析构函数，没有任何参数，也不返回任何值。_
* 析构函数的功能是用来释放一个对象，在对象删除前，用它来做一些清理工作，它与构造函数的功能正好相反。在_C++/CLI_中，还提供另一种清理机制，称为finalizer（译为“终结器”）。定义终结器的方式与定义析构函数的方式类似，定义类的终结器的方式与定义析构函数的方式类似，其区别在于需要通过“!”符号来代替析构函数中的“～”符号。
* 几个特殊函数调用顺序：
**1．对象的创建：开始之初，调用构造函数，构造对象
2、默认构造函数：
3、对象的析构：使用完毕、调用析构函数，释放对象所占用空间
4、终结器函数：终结器是在销毁该引用类对象时由垃圾回收器自动调用的。
5、复制构造函数（拷贝构造函数）：管理复制对象时的空间**

* 接口实现多继承:比类的内涵更广。
  
* 9.20
* 虚函数——virtual<函数类型>《函数名》（形参表）{函数体}：为了实现某一功能而假设的函数
* 在一个派生类中重新定义基类的虚函数是函数重载的另一种特殊形式，但它不同于一般的函数重载。一般的函数重载，只要函数名相同即可，函数的返回类型及所带的参数可以不同。要求所带的参数可以区分是调用哪个重载函数。当重载一个虚函数时，即在派生类中重新定义此虚函数时，则要求函数名、返回类型、参数个数、参数类型以及参数的顺序都与基类中虚函数原型完全相同，不能有任何的不同。虚函数在调用的时候根据当前对象，优先调用对象本身的虚成员函数。这有点像名字支配规律，不过虚函数是动态绑定的，是在执行期“间接”调用实际上欲绑定的函数。也就是说程序运行到此处才动态确定。
  
* 10.19

* show()方法显示窗体后，不影响该程序其他窗体的使用。显示窗体后，后面的代码会继续执行
showDialog()方法显示窗体后，只能在此窗体上进行操作。只有当窗体关闭之后，后面的代码才会继续执行。
* nullptr是一个字面值常量，类型为std::nullptr_t,空指针常数可以转换为任意类型的指针类型。
* Trim（）功能：删除字符串中多余的空格，但会在英文字符串中保留一个作为词与词之间分隔的空格。