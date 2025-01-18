# WET 稀释性能瓶颈

DRY 原则（Don't Repeat Yourself，不要重复自己）的重要性在于它编码了一个理念：系统中的每个知识片段都应该有一个单一的表示。换句话说，知识应该包含在一个单一的实现中。DRY 的反面是 WET（Write Every Time，每次都写）。当知识在多个不同的实现中被编码时，我们的代码就是 WET 的。当你考虑 DRY 和 WET 对性能分析的众多影响时，它们对性能的影响就变得非常明显。

让我们首先考虑系统中的一个特性，比如 *X*，它是一个 CPU 瓶颈。假设特性 *X* 消耗了 30% 的 CPU。现在假设特性 *X* 有十个不同的实现。平均而言，每个实现将消耗 3% 的 CPU。如果我们正在寻找快速获胜的机会，这种级别的 CPU 利用率并不值得担心，因此我们很可能会忽略这个特性是我们的瓶颈。然而，假设我们以某种方式识别出特性 *X* 是一个瓶颈。我们现在面临的问题是找到并修复每一个实现。使用 WET，我们有十个不同的实现需要找到并修复。使用 DRY，我们会清楚地看到 30% 的 CPU 利用率，并且我们只需要修复十分之一的代码。我有没有提到我们不必花时间寻找每个实现？

有一个用例我们经常违反 DRY 原则：我们对集合的使用。实现查询的常见技术是遍历集合，然后依次对每个元素应用查询：

```java
public class UsageExample {
    private ArrayList<Customer> allCustomers = new ArrayList<Customer>();
    // ...
    public ArrayList<Customer> findCustomersThatSpendAtLeast(Money amount) {
        ArrayList<Customer> customersOfInterest = new ArrayList<Customer>();
        for (Customer customer: allCustomers) {
            if (customer.spendsAtLeast(amount))
               customersOfInterest.add(customer);
        }
        return customersOfInterest;
    }
}
```

通过将这个原始集合暴露给客户端，我们违反了封装原则。这不仅限制了我们重构的能力，还迫使我们代码的用户通过重新实现可能相同的查询来违反 DRY 原则。这种情况可以通过从 API 中移除暴露的原始集合来轻松避免。在这个例子中，我们可以引入一个新的、特定领域的集合类型，称为 `CustomerList`。这个新类在语义上更符合我们的领域。它将作为我们所有查询的自然归宿。

拥有这个新的集合类型还将使我们能够轻松地看到这些查询是否是性能瓶颈。通过将查询纳入类中，我们消除了向客户端暴露表示选择（如 `ArrayList`）的需要。这使我们能够自由地更改这些实现，而不必担心违反客户端合同：

```java
public class CustomerList {
    private ArrayList<Customer> customers = new ArrayList<Customer>();
    private SortedList<Customer> customersSortedBySpendingLevel = new SortedList<Customer>();
    // ...
    public CustomerList findCustomersThatSpendAtLeast(Money amount) {
        return new CustomerList(customersSortedBySpendingLevel.elementsLargerThan(amount));
    }
}

public class UsageExample {
    public static void main(String[] args) {
        CustomerList customers = new CustomerList();
        // ...
        CustomerList customersOfInterest = customers.findCustomersThatSpendAtLeast(someMinimalAmount);
        // ...
    }
}
```

在这个例子中，遵循 DRY 原则使我们能够引入一个替代的索引方案，使用 `SortedList` 根据客户的消费水平进行索引。比这个特定例子的具体细节更重要的是，遵循 DRY 原则帮助我们找到并修复了一个性能瓶颈，如果代码是 WET 的，这个瓶颈将更难被发现。

作者：[Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine)