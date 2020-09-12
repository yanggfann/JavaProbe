## 面向对象的概念

#### What

* **对象**(Object)：对具象的抽象

  * 状态(state)
  * 行为(behavior)

* **类**：抽象的抽象Abstract

  * 属性(Property)
  * 方法(method)

* 怎么抽象？

  * 上下文(context)
  * 领域(domain)
  * 数据模型(Data Model)
  * 业务模型()
  * 技术模型()
  * 业务场景(User Case)
  * 逻辑(Logic)

* OO思想

  * 抽象(abstract)：建模

  * 封装(Encapsulation)：模块化

    * access control
      * private
      * protected
      * public
    * property protect
      * getter/setter
    * implementing hide

  * 继承(inherit)：复用和层次化

    * 复用(Reuse)

    * 层次化(Hierarchical)

    * **Abstract Class** vs **Interface**

  * 多态(Polymorphism)：可扩展性

    概念：同一操作作用于不同的对象，可以有不同的解释，产生不同的执行结果，这就是多态性。简单的说:"一个接口，多种实现"

* Overloading & Overriding

  * Overloading：方法签名（输入参数类型）不同
  * Overriding：方法签名相同

* Inner Class

* Class vs Type

* Class vs Generic

#### Why

- decoupling
- readable
- modulization
- understanding

## 面向对象编程(Programming)

* A Class
* toString、hashcode、equals

#### 类

* Initial Order
* 静态：只初始化一次
* 初始化顺序：静态，非静态，构造器，先构造父类再构造子类；
* super()

#### 对象

* Life Cycle

  created -> in use -> unreachable(不可达) -> collected -> finalized -> De-Allocated

#### OO Programming Principle

* 单一职责(SRP)Single Responsibility Principle
* 开放封闭(OCR)Open Closed Principle
* 里氏替换(LSP)Liskov Substitution Principle
* 接口隔离原则(ISP)InterFace Segregation Principle
* 依赖置换原则(DIP)Dependency Inversion Principle
* 迪米特(LOD)-最少知识原则 Law of Demeter

#### [UML 类图](https://www.draw.io/)

* 依赖关系
* 聚合关系
* 组合关系
* 关联关系

#### 设计模式

​	通过设计模式设计符合OO Programming Principle的程序。
