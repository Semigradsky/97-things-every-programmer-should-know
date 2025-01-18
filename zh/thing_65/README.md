# 优先使用领域特定类型而非原始类型

1999年9月23日，价值3.276亿美元的火星气候轨道器在进入火星轨道时失联，原因是地球上的一个软件错误。这个错误后来被称为*公制混淆*。地面站软件使用的是磅，而航天器预期的是牛顿，导致地面站低估了航天器推进器的功率，误差达到了4.45倍。

这是许多软件故障中的一个例子，如果应用了更强且更领域特定的类型系统，这些故障本可以避免。这也是Ada语言中许多特性背后的一个例证，Ada的主要设计目标之一是实现嵌入式安全关键软件。Ada具有强类型系统，并对原始类型和用户定义类型进行静态检查：

```ada
type Velocity_In_Knots is new Float range 0.0 .. 500.00;

type Distance_In_Nautical_Miles is new Float range 0.0 .. 3000.00;

Velocity: Velocity_In_Knots;

Distance: Distance_In_Nautical_Miles;

Some_Number: Float;

Some_Number:= Distance + Velocity; -- 编译器会捕获这个类型错误。
```

在要求不那么严格的领域中，开发者也可以从应用更多领域特定类型中受益，否则他们可能会继续使用语言及其库提供的原始数据类型，如字符串和浮点数。在Java、C++、Python和其他现代语言中，抽象数据类型被称为类。使用诸如`Velocity_In_Knots`和`Distance_In_Nautical_Miles`这样的类，可以在代码质量方面带来很多好处：

- 代码变得更易读，因为它表达了领域的概念，而不仅仅是浮点数或字符串。
- 代码变得更易测试，因为代码封装了易于测试的行为。
- 代码促进了跨应用程序和系统的重用。

这种方法对于静态类型语言和动态类型语言的用户同样有效。唯一的区别是，使用静态类型语言的开发者可以从编译器获得一些帮助，而使用动态类型语言的开发者则更可能依赖他们的单元测试。检查的方式可能不同，但动机和表达风格是相同的。

结论是，为了开发高质量的软件，开始探索领域特定类型是值得的。

作者：[Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)