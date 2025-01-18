# 多态性的缺失机会

多态性是面向对象编程（OO）中的核心思想之一。这个词源自希腊语，意思是“多”（*poly*）种“形式”（*morph*）。在编程的上下文中，多态性指的是某一类对象或方法的多种形式。但多态性不仅仅是关于替代实现。如果谨慎使用，多态性可以创建微小的局部执行上下文，使我们无需冗长的 *if-then-else* 块即可工作。处于上下文中允许我们直接做正确的事情，而处于上下文之外则迫使我们重建上下文，以便我们能够做正确的事情。通过谨慎使用替代实现，我们可以捕获上下文，从而帮助我们生成更少、更易读的代码。这一点最好通过一些代码来展示，比如以下（不切实际的）简单的购物车：

```java
public class ShoppingCart {
    private ArrayList<Item> cart = new ArrayList<Item>();
    public void add(Item item) { cart.add(item); }
    public Item takeNext() { return cart.remove(0);  }
    public boolean isEmpty() { return cart.isEmpty(); }
}
```

假设我们的网店提供可以下载的商品和需要邮寄的商品。让我们构建另一个对象来支持这些操作：

```java
public class Shipping {
    public boolean ship(Item item, SurfaceAddress address) { ... }
    public boolean ship(Item item, EMailAddress address) { ... }
}
```

当客户完成结账时，我们需要发货：

```java
while (!cart.isEmpty()) {
    shipping.ship(cart.takeNext(), ???);
}
```

这里的 *???* 参数并不是某种新的花哨的 Elvis 操作符，而是在问：我应该通过电子邮件还是普通邮件发送这个商品？回答这个问题所需的上下文已经不存在了。我们可以用一个布尔值或枚举来捕获发货方式，然后使用 *if-then-else* 来填充缺失的参数。另一种解决方案是创建两个类，它们都继承自 `Item`。让我们称它们为 `DownloadableItem` 和 `SurfaceItem`。现在让我们编写一些代码。我将把 `Item` 提升为一个支持单一方法 `ship` 的接口。为了发货购物车中的内容，我们将调用 `item.ship(shipper)`。类 `DownloadableItem` 和 `SurfaceItem` 都将实现 `ship` 方法。

```java
public class DownloadableItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getEmailAddress());
    }
}

public class SurfaceItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getSurfaceAddress());
    }
}
```

在这个例子中，我们将与 `Shipping` 交互的责任委托给了每个 `Item`。由于每个商品都知道如何最好地发货，这种安排使我们能够继续工作，而无需使用 *if-then-else*。这段代码还展示了两种经常配合使用的模式：命令模式和双重分派模式。这些模式的有效使用依赖于对多态性的谨慎使用。当这种情况发生时，我们代码中的 *if-then-else* 块的数量将会减少。

虽然在某些情况下使用 *if-then-else* 比多态性更实用，但更多情况下，更具多态性的编码风格将产生更小、更易读且更不易出错的代码库。错失的机会的数量可以通过我们代码中的 *if-then-else* 语句的简单计数来衡量。

作者：[Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine)