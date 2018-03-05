## 面向对象
下面列出了面向对象软件开发的优点：
(1) 代码开发模块化，更易维护和修改。
(2) 代码复用。
(3) 增强代码的可靠性和灵活性。
(4) 增加代码的可理解性。
面向对象编程有很多重要的特性，比如：封装，继承，多态和抽象

## Java面向对象的三个特征与含义
一、继承：
1.概念：继承是从已有的类中派生出新的类，新的类能吸收已有类的数据属性和行为，并能扩展新的能力
2.好处：提高代码的复用，缩短开发周期。
二、多态：
1.概念：多态（Polymorphism）按字面的意思就是“多种状态，即同一个实体同时具有多种形式。一般表现形式是程序在运行的过程中，同一种类型在不同的条件下表现不同的结果。多态也称为动态绑定，一般是在运行时刻才能确定方法的具体执行对象，这个过程也称为动态委派。
2.好处：
1）将接口和实现分开，改善代码的组织结构和可读性，还能创建可拓展的程序。
2）消除类型之间的耦合关系。允许将多个类型视为同一个类型。
3）一个多态方法的调用允许有多种表现形式
三、封装：
1.概念：就是把对象的属性和操作（或服务）结合为一个独立的整体，并尽可能隐藏对象的内部实现细节。
 2.好处：
(1)隐藏信息，实现细节。让客户端程序员无法触及他们不应该触及的部分。
(2)允许可设计者可以改变类内部的工作方式而不用担心会影响到客户端程序员。


## Overload 和 Override
Overload 是重载的意思，Override 是覆盖的意思，也就是重写。
**重载 Overload** 表示**同一个类**中可以有多个名称相同的方法，但这些方法的参数列表各不相同（即参数个数或类型不同）。
**重写 Override** 表示**子类**中的方法可以与**父类**中的某个**方法的名称和参数完全相同**，通过子类创建的实例对象调用这个方法时，将调用子类中的定义方法，这相当于把父类中定义的那个完全相同的方法给覆盖了，这也是面向对象编程的多态性的一种表现。**子类覆盖父类的方法时，只能比父类抛出更少的异常，或者是抛出父类抛出的异常的子异常**，因为子类可以解决父类的一些问题，不能比父类有更多的问题。**子类方法的访问权限只能比父类的更大，不能更小**。如果**父类的方法是 private 类型，那么，子类则不存在覆盖的限制**，相当于子类中增加了一个全新的方法。
  至于 Overloaded 的方法是否可以改变返回值的类型这个问题，要看你倒底想问什么呢？这个题目很模糊。如果几个 Overloaded 的方法的参数列表不一样，它们的返回者类型当然也可以不一样。但我估计你想问的问题是：如果两个方法的参数列表完全一样，是否可以让它们的返回值不同来实现重载 Overload。这是不行的，我们可以用反证法来说明这个问题，因为我们有时候调用一个方法时也可以不定义返回结果变量，即不要关心其返回结果，例如，我们调用 map.remove(key) 方法时，虽然 remove 方法有返回值，但是我们通常都不会定义接收返回结果的变量，这时候假设该类中有两个名称和参数列表完全相同的方法，仅仅是返回类型不同，Java 就无法确定编程者倒底是想调用哪个方法了，因为它无法通过返回结果类型来判断。

Override 可以翻译为覆盖，从字面就可以知道，它是覆盖了一个方法并且对其重写，以求达到不同的作用。对我们来说最熟悉的覆盖就是对接口方法的实现，在接口中一般只是对方法进行了声明，而我们在实现时，就需要实现接口声明的所有方法。除了这个典型的用法以外，我们在继承中也可能会在子类覆盖父类中的方法。**在覆盖要注意以下的几点**：
**1、覆盖的方法的标志必须要和被覆盖的方法的标志完全匹配，才能达到覆盖的效果；**
**2、覆盖的方法的返回值必须和被覆盖的方法的返回一致,或者是其子类（协变返回类型)；**
**3、覆盖的方法所抛出的异常必须和被覆盖方法的所抛出的异常一致，或者是其子类；**
**4、被覆盖的方法不能为 private，否则在其子类中只是新定义了一个方法，并没有对其进行覆盖。**

Overload 对我们来说可能比较熟悉，可以翻译为重载，它是指我们可以定义一些名称相同的方法，通过定义不同的输入参数来区分这些方法，然后再调用时，VM 就会根据不同的参数样式，来选择合适的方法执行。在使用**重载要注意**以下的几点：
**1、在使用重载时只能通过不同的参数样式。**例如，不同的参数类型，不同的参数个数，不同的参数顺序（当然，同一方法内的几个参数类型必须不一样，例如可以是 fun(int,float)，但是不能 fun(int,int)）；
 **2、不能通过访问权限、返回类型、抛出的异常进行重载**；
**3、方法的异常类型和数目不会对重载造成影响**；


## 接口和抽象类的区别
Java 提供和支持创建抽象类和接口。它们的实现有共同点，不同点在于：
1,接口中所有的**方法**隐含的都是抽象的。而抽象类则可以同时包含抽象和非抽象的方法。
2,类可以实现很多个接口，但是只能**继承**一个抽象类
3,类如果要**实现**一个接口，它必须要实现接口声明的所有方法。但是，类可以不实现抽象类声明的所有方法，当然，在这种情况下，类也必须得声明成是抽象的。
4,抽象类可以在不提供接口方法实现的情况下实现接口。
5,Java 接口中声明的**变量**默认都是 final 的。抽象类可以包含非 final 的变量。
6,Java 接口中的**成员函数**默认是 public 的。抽象类的成员函数可以是 private，protected 或者是 public 。
7,接口是绝对抽象的，不可以被实例化。抽象类也不可以被实例化，但是，如果它包含 main 方法的话是可以被调用的

## 接口
接口很重要，为了说明情况，这里稍微啰嗦点：
（1）接口用于描述系统对外提供的所有服务,因此接口中的成员常量和方法**都必须是公开(public)类型**的,确保外部使用者能访问它们；
（2）接口仅仅描述系统能做什么,但不指明如何去做,所以接口中的方法**都是抽象(abstract)方法**；
（3）接口不涉及和任何具体实例相关的细节,因此接口没有构造方法,不能被实例化,没有实例变量，**只有静态（static）变量**；
（4）接口的中的变量是所有实现类**共有的**，既然共有，肯定是不变的东西，因为变化的东西也不能够算共有。所以**变量是不可变(final)类型，也就是常量了**。
（5） 接口中不可以定义变量.如果接口可以定义变量，但是接口中的方法又都是抽象的，在接口中无法通过行为来修改属性。有的人会说了，没有关系，可以通过 实现接口的对象的行为来修改接口中的属性。这当然没有问题，但是考虑这样的情况。如果接口 A 中有一个public 访问权限的静态变量 a。按照 Java 的语义，我们可以不通过实现接口的对象来访问变量 a，通过 A.a = xxx; 就可以改变接口中的变量 a 的值了。正如抽象类中是可以这样做的，**那么实现接口 A 的所有对象也都会自动拥有这一改变后的 a 的值了，也就是说一个地方改变了 a，所有这些对象中 a 的值也都跟着变了**。这和抽象类有什么区别呢，怎么体现接口更高的抽象级别呢，怎么体现接口提供的统一的协议呢，那还要接口这种抽象来做什么呢？所以接口中 不能出现变量，如果有变量，就和接口提供的统一的抽象这种思想是抵触的。所以接口中的属性必然是常量，只能读不能改，这样才能为实现接口的对象提供一个统 一的属性。
通俗的讲，你认为是要变化的东西，就放在你自己的实现中，不能放在接口中去，接口只是对一类事物的属性和行为更高层次的抽象。对修改关闭，对扩展（不同的实现 implements）开放，接口是**对开闭原则**的一种体现。
所以：**接口的方法默认是 public abstract**；
接口中不可以定义变量即只能定义常量(加上final修饰就会变成常量)。**所以接口的属性默认是 public static final 常量，且必须赋初值**。
**注意**：final 和 abstract 不能同时出现。

## 两个对象值相同(x.equals(y) == true)，但却可有不同的 hash code，这句话对不对？
答：不对，如果两个对象 x 和 y 满足 x.equals(y) == true，它们的哈希码（hash code）应当相同。
Java 对于 eqauls 方法和 hashCode 方法是这样规定的：
**(1)如果两个对象相同（equals 方法返回 true ），那么它们的 hashCode 值一定要相同**；
**(2)如果两个对象的 hashCode 相同，它们并不一定相同**。当然，你未必要按照要求去做，但是如果你违背了上述原则就会发现在使用容器时，相同的对象可以出现在 Set 集合中，同时增加新元素的效率会大大下降（对于使用哈希存储的系统，如果哈希码频繁的冲突将会造成存取性能急剧下降）。
**(3)如果对象的equals方法的比较操作所用到的信息没有被修改,那么对同一个对象调用多次,hashCode方法都必须始终如一地返回同一个整数**.

补充：关于 equals 和 hashCode 方法，很多 Java 程序都知道，但很多人也就是仅仅知道而已，在 Joshua Bloch 的大作《Effective Java》（很多软件公司，《Effective Java》、《Java 编程思想》以及《重构：改善既有代码质量》是 Java 程序员必看书籍，如果你还没看过，那就赶紧去亚马逊买一本吧）中是这样介绍 equals 方法的：首先 equals 方法必须满足自反性（x.equals(x) 必须返回true）、对称性（x.equals(y) 返回true时，y.equals(x) 也必须返回 true）、传递性（x.equals(y)和y.equals(z)都返回 true 时，x.equals(z)也必须返回true）和一致性（当x和y引用的对象信息没有被修改时，多次调用x.equals(y)应该得到同样的返回值），而且对于任何非 null 值的引用 x，x.equals(null) 必须返回 false。实现高质量的 equals 方法的**诀窍**包括：

    **使用 == 操作符检查“参数是否为这个对象的引用”**；
    **使用 instanceof 操作符检查“参数是否为正确的类型”**；
    **对于类中的关键属性，检查参数传入对象的属性是否与之相匹配**；
    **编写完 equals 方法后，问自己它是否满足对称性、传递性、一致性**；
    **重写 equals 时总是要重写 hashCode**；
    **不要将 equals 方法参数中的 Object 对象替换为其他的类型，在重写时不要忘掉 @Override 注解**。

## 是 AOP 和 OOP，IOC 和 DI
1）面向对象编程（Object Oriented Programming，OOP，面向对象程序设计）是一种计算机编程架构。AOP 是 OOP 的延续，是 Aspect Oriented Programming 的缩写，意思是面向方面编程。 将通用需求功能从不相关类之中分离出来；同时，能够使得很多类共享一个行为，一旦行为发生变化，不必修改很多类，只要修改这个行为就可以。AOP 就是这种实现分散关注的编程方法，它将“关注”封装在“方面”中

2）控制反转 IOC(Inversion of Control) 控制指的就是程序相关类之间的依赖关系.传统观念设计中,
通常由调用者来创建被调用者的实例, **在 Spring 里,创建被调用者的工作不再由调用者来完成,而是由 Spring 容器完成，依赖关系被反转了，称为控制反转，目的是为了获得更好的扩展性和良好的可维护性**。依赖注入(Dependency injection)创建被调用者的工作由 Spring 容器完成，然后注入调用者，因此也称依赖注入。控制反转和依赖注入是**同一个概念**。




