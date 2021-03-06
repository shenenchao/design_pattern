**模式定义**：当一个对象内在状态改变时允许其改变行为，这个对象看起来像改变了其类。状态模式的核心是封装，状态的变更，引起了行为的变更。从外部看就好像这个对象对应的类发生了改变一样。

例子：电梯的状态转变

**环境角色有两个不成文的规定**：

* 将状态对象声明为静态变量，有几个状态对象就声明几个静态变量。
* 环境角色具有状态抽象定义角色的所有行为，具体执行用委托方式

优点：

* 结构清晰
* 遵循设计原则，封装性好

缺点：

* 子类太多，状态多，类膨胀

**使用场景：**

* **行为随状态改变而改变的场景**这也是状态模式的根本出发点，例如**权限设计，人员的状态不同即使执行相同的行为结果也会不同**，在这种情况下需要考虑使用状态模式。

*  **条件、分支判断语句的替代者**

**注意：**

状态模式适用于当**某个对象在它的状态发生改变时，它的行为也随着发生比较大的变化**，也就是说在**行为受状态约束的情况**下可以使用状态模式，而且使用时对象的状态最好不要超过 5 个。

#### 状态模式和策略模式PK

对比策略模式的类型会发现和状态模式的类图很类似，但实际上有很大的区别，具体体现在concrete class上。策略模式**通过Context产生唯一一个策略作用于代码**中，而状态模式则是**通过context组织多个状态流转** 形成一个状态转换图来实现业务逻辑。

状态模式的核心是**封装，将状态以及状态转换逻辑封装到类的内部来实现**，也很好的体现了“开闭原则”和“单一职责原则”。每一个状态都是一个子类，不管是修改还是增加状态，只需要修改或者增加一个子类即可。在我们的应用场景中，状态数量以及状态转换远比上述例子复杂，通过“状态模式”避免了大量的if-else代码，让我们的逻辑变得更加清晰。同时由于状态模式的良好的封装性以及遵循的设计原则，让我们在复杂的业务场景中，能够游刃有余地管理各个状态。