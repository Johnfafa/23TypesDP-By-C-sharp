#### c#的23种设计模式

> 面向对象设计需要考虑：`封装、粒度、对象依赖、灵活性、性能、演化、复用...`
>
> 面向对象设计原则：
>
> - 针对接口编程，而不是针对实现编程
> - 优先使用对象组合，而不是类继承

#### 设计模式分类

> **一、目的准则：模式依据其目的性可分为<u>创建型</u>、<u>结构型</u>、<u>行为型</u>。<u>创建型</u>模式与对象的创建有关；<u>结构型</u>模式处理类或对象的组合；<u>行为型</u>模式对类或对象怎样进行交互和分配职责进行描述。**
>
> **二、范围准则：如下图1，模式用于类还是对象，类模式处理类和子类之间的关系，这些关系通过继承建立，是<u>静态</u>的，在编译的时候就确定下来了；对象模式处理对象之间的关系，这些关系在运行时是可以变化的，更具<u>动态性</u>。**
>
>
> - 创建型类模式将对象的部分创建工作延迟到子类，而创建型对象模式则将它延迟到另一个对象中
>
> - 结构型类模式使用继承机制来组合类，而结构型对象模式则描述了对象的组装方式
>
> - 行为型类模式使用继承描述算法和控制流，而行为型对象模式则描述了一组对象怎么协作完成单个对象所无法完成的任务
> 

|      |      | 目的                                                        |                                                              |                                                              |
| ---- | ---- | ----------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
|      |      | 创建型                                                      | 结构型                                                       | 行为型                                                       |
| 范围 | 类   | Factory Method                                              | Adapter(类)                                                  | Interpreter<br />Template Method                             |
|      | 对象 | Abstract Factory<br />Builder<br />Prototype<br />Singleton | Adapter(对象)<br />Bridge<br />Composite<br />Decorator<br />Facade<br />Flyweight<br />Proxy | Chain of Responsibility<br />Command<br />Iterator<br />Mediator<br />Memento<br />Observer<br />State<br />Strategy<br />Visitor |

​																												 图1：设计模式空间

![relation](assets/设计模式之间的关系.png)

​																													图2：设计模式之间的关系图

#### 设计模式意图

>每个设计模式的名称都与它所指向的意图关联
>
>- Abstract Factory（抽象工厂）：提供一个创建一系列相关或相互依赖对象的接口，而无需指定它们具体的类。
>- Adapter（适配器）：将一个类的接口转换成客户希望的另一个接口。Adapter模式使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。
>- Bridge（桥接）：将抽象部分与它的实现部分分离，使它们都可以独立地变化。
>- Builder（生成器）：将一个复杂对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示。
>- Chain of Responsibility（职责链）：为解除请求的发送者和接受者之间的耦合，而使多个对象都有机会处理这个请求。将这些对象连城一条链，并沿着这条链传递该请求，直到有一个对象处理它。
>- Command（命令）：将一个请求封装成一个对象，从而使你可用不同的请求对客户进行参数化；对请求排队或记录请求日志，以及支持可取消的操作。
>- Composite（组合）：将对象组合成树形结构以表示“部分-整体”的层次结构。Composite使得客户对单个对象和复合对象的使用更具一致性。
>- Decorator（装饰）：动态地给一个对象添加一些额外的职责。就扩展功能而言，Decorator模式比生成子类方式更为灵活。
>- Facade（外观）[fəˈsɑːd]：为子系统中的一组接口提供一个一致的界面，Facade模式定义了一个高层接口，这个接口使得这一子系统更加容易使用。
>- Factory Method（工厂方法）：定义一个用于创建对象的接口，让子类决定将哪一个类实例化。Factory Method使一个类的实例化延迟到了其子类。
>- Flyweight（享元）：运用共享技术有效地支持大量细粒度的对象。
>- Interpreter（解释器）[ɪnˈtɜrprətər]：给定一个语言，定义它的文法的一种表示，并定义一个解析器，该解释器使用该表示来解释语言中的句子。
>- Iterator（迭代器）：提供一个方法顺序访问一个聚合对象中的各个元素，而又不需要暴露该对象的内部表示。
>- Mediator（中介者）：用一个中介对象来封装一系列的对象交互。中介者使各个对象不需要显式地互相引用，从而使其耦合松散，二分切可以独立地改变它们之间的交互。
>- Memento（备忘录）[məˈmentoʊ]：在不破坏封装性的前提下，捕获一个对象的内部状态，并在该对象之外保存这个状态，这样以后就可以将该对象恢复到保存的状态。
>- Observer（观察者）：定义对象间的一种一对多的依赖关系，以便每一个对象的状态发生改变时，所有依赖于它的对象都得到通知并自动刷新。
>- Prototype（原型）：用原型实例指定创建对象的种类，并通过拷贝这个原型来创建新的对象。
>- Proxy（代理）：为其他对象提供一个代理以控制对这个对象的访问。
>- Singleton（单例）：保证一个类仅有一个实例，并提供一个访问它的全局访问点。
>- State（状态）：允许一个对象在其内部状态发生改变时改变它的行为。对象看起来似乎修改了它所属的类。
>- Strategy（策略）：定义一系列的算法，把它们一个个封装起来，并且使它们可以相互替换。本模式使得算法的变化可独立于使用它的客户。
>- Template Method（模板方法）：定义一个操作中的算法骨架，而将一些步骤延迟到子类中。Template Method使得子类可以不改变一个算法的结构即可重定义该算法的某些特定步骤。
>- Visitor（访问者）：表示一个作用于某对象结构中的个元素的操作。它能使你可以在不改变各元素的前提下定义作用于这些元素的新操作。

#### 怎样选择设计模式

> 1. 熟悉每个设计模式的意图
> 2. 考虑你的设计中可变的部分，设计模式中允许独立变化的方面，参考表2

| 目的 | 设计模式                                                     | 可变的方面                                                   |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 创建 | Abstract Factory<br />Builder<br />Factory Method<br />Prototype<br />Singleton | 产品对象家族<br />如何创建一个组合对象<br />被实例化的子类<br />被实例化的类<br />一个类的唯一实例 |
| 结构 | Adapter<br />Bridge<br />Composite<br />Decorator<br />Facade<br />Flyweight<br />Proxy | 对象的接口<br />对象的实现<br />一个对象的结构和组成<br />对象的职责，不生成子类<br />一个子系统的接口<br />对象的存储开销<br />如何访问一个对象；该对象的位置 |
| 行为 | Chain of Responsibility<br />Command<br />Interpreter<br />Iterator<br />Mediator<br />Memento<br />Observer<br />State<br />Strategy<br />Template Method<br />Visitor | 如何满足一个请求的对象<br />何时、怎样满足一个请求<br />一个语言的文法及解释<br />如何遍历、访问一个聚合的各元素<br />对象之间怎样交互、和谁交互<br />一个对象中哪些私有信息存放在该对象之外，以及在什么时候进行存储<br />多个对象依赖于另外一个对象，而这些对象又如何保持一致<br />对象的状态<br />算法<br />算法中的某些步骤<br />某些可作用与一个（组）对象上的操作，但不修改这些对象的类 |

#### `UML` 类图解读

![uml](assets/UML类图.png)

- 泛化关系
	`泛化关系用一条带空心箭头的实线表示，泛化关系的代码表现为继承非抽象类。`
	![generalize](assets/泛化关系.png)
	
- 实现关系
	`实现关系用一条带空心箭头的虚线表示，实现关系的代码表现为继承抽象类或接口。`
	![realize](assets/实现关系.png)

- 聚合关系

	`聚合关系用一条带空心菱形箭头的实线表示，聚合关系不是强依赖的，比如学生和班级，班级取消了，学生不会消失，他们依然存在。聚合关系的代码实现表现为成员变量，变量为类或类的集合。`
	![aggregation](assets/聚合关系.png)
	
- 组合关系

	`组合关系用一条带实心菱形箭头的实线表示，组合关系是强依赖的，部分和整体拥有相同的生命周期（同生共死）。组合关系的代码实现表现为成员属性，属性为类。`
	![composition](assets/组合关系.png)
	
- 关联关系

	`关联关系用一条带箭头的实线表示，一般用来定义对象之间静态的、天然的结构，如：乘机人和机票、学生和学校等。关联关系在代码实现中表现为成员变量。`
![association](assets/关联关系.png)

- 依赖关系

	`依赖关系用一条带箭头的虚线表示，依赖关系在运行中产生，并随着运行时变化。依赖关系在代码实现中表现为类构造方法及类方法的参数。`
![dependency](assets/依赖关系.png)
