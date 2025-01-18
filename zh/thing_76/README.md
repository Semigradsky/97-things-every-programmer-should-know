# 单一职责原则

良好设计的最基本原则之一是：

> 将因相同原因而变化的事物聚集在一起，将因不同原因而变化的事物分开。

这一原则通常被称为*单一职责原则*（Single Responsibility Principle，简称SRP）。简而言之，它指出一个子系统、模块、类，甚至一个函数，都不应该有超过一个改变的理由。经典的例子是一个类包含了处理业务规则、报告和数据库的方法：

```java
public class Employee {
  public Money calculatePay() ...
  public String reportHours() ...
  public void save() ...
}
```

一些程序员可能会认为将这三个函数放在同一个类中是合适的。毕竟，类应该是操作共同变量的函数集合。然而，问题在于这三个函数因完全不同的原因而变化。`calculatePay` 函数会在计算薪酬的业务规则发生变化时改变。`reportHours` 函数会在有人想要不同的报告格式时改变。`save` 函数会在数据库管理员更改数据库模式时改变。这三个变化的原因结合在一起，使得 `Employee` 类非常不稳定。它会因其中任何一个原因而改变。更重要的是，任何依赖于 `Employee` 的类都会受到这些变化的影响。

良好的系统设计意味着我们将系统分离为可以独立部署的组件。独立部署意味着如果我们更改一个组件，我们不需要重新部署其他任何组件。然而，如果 `Employee` 被其他组件中的许多类广泛使用，那么每次对 `Employee` 的更改都可能导致其他组件需要重新部署；从而否定了组件设计（或如果你更喜欢时髦的名称，SOA）的主要优势。

```java
public class Employee {
  public Money calculatePay() ...
}

public class EmployeeReporter {
  public String reportHours(Employee e) ...
}

public class EmployeeRepository {
  public void save(Employee e) ...
}
```

上面展示的简单划分解决了这些问题。每个类都可以放在自己的组件中。或者更准确地说，所有与报告相关的类可以放在报告组件中。所有与数据库相关的类可以放在存储库组件中。所有业务规则可以放在业务规则组件中。

敏锐的读者会发现，上述解决方案中仍然存在依赖关系。`Employee` 仍然被其他类依赖。因此，如果 `Employee` 被修改，其他类可能也需要重新编译和重新部署。因此，`Employee` 不能被修改后独立部署。然而，其他类可以被修改并独立部署。对其中一个类的修改不会强制其他类重新编译或重新部署。甚至 `Employee` 也可以通过谨慎使用*依赖倒置原则*（Dependency Inversion Principle，DIP）来独立部署，但这是[另一本书](http://www.amazon.com/dp/0135974445/)的主题。

谨慎应用 SRP，将因不同原因而变化的事物分开，是创建具有独立可部署组件结构的设计的关键之一。

作者：[Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)