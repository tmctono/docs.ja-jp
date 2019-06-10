---
title: ジェネリック インターフェイスの分散 (C#)
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: a2d0bcc049d62978930b4e5cdef7920349e3b894
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66815965"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="1c2b0-102">ジェネリック インターフェイスの分散 (C#)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-102">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="1c2b0-103">.NET Framework 4 では、既存のいくつかのジェネリック インターフェイスに対して、分散のサポートが導入されています。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="1c2b0-104">分散のサポートにより、これらのインターフェイスを実装するクラスの暗黙的な変換が可能になりました。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> 

<span data-ttu-id="1c2b0-105">.NET Framework 4 以降では、次のインターフェイスがバリアントです。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-105">Staring with .NET Framework 4, the following interfaces are variant:</span></span>

- <span data-ttu-id="1c2b0-106"><xref:System.Collections.Generic.IEnumerable%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="1c2b0-107"><xref:System.Collections.Generic.IEnumerator%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="1c2b0-108"><xref:System.Linq.IQueryable%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="1c2b0-109"><xref:System.Linq.IGrouping%602> (`TKey` と `TElement` は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="1c2b0-110"><xref:System.Collections.Generic.IComparer%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="1c2b0-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="1c2b0-112"><xref:System.IComparable%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-112"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="1c2b0-113">.NET Framework 4.5 以降では、次のインターフェイスがバリアントです。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-113">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <span data-ttu-id="1c2b0-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T is covariant)</span></span>

- <span data-ttu-id="1c2b0-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T is covariant)</span></span>

<span data-ttu-id="1c2b0-116">共変性により、メソッドの戻り値の型の派生を、インターフェイスのジェネリック型パラメーターで定義されている型よりも強くすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-116">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="1c2b0-117">ここでは、共変性機能について説明するために、`IEnumerable<Object>` および `IEnumerable<String>` というジェネリック インターフェイスについて考えます。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-117">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="1c2b0-118">`IEnumerable<String>` インターフェイスは、`IEnumerable<Object>` インターフェイスを継承しません。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-118">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="1c2b0-119">ただし、`String` 型は `Object` 型を継承します。場合によっては、これらのインターフェイスのオブジェクトを、相互に割り当てる必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-119">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="1c2b0-120">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-120">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="1c2b0-121">.NET Framework の以前のバージョンでは、C# ではこのコードを実行するとコンパイル エラーが発生し、Visual Basic では `Option Strict` がオンの場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-121">In earlier versions of the .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="1c2b0-122">今後は、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスが共変になったので、上記の例のように、`objects` の代わりに `strings` を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-122">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="1c2b0-123">反変性により、メソッドの引数の型の派生を、インターフェイスのジェネリック パラメーターで指定されている型よりも弱くすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-123">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="1c2b0-124">ここでは、反変性について説明するために、`BaseClass` クラスのインスタンスを比較するための `BaseComparer` クラスを作成した場合について考えます。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-124">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="1c2b0-125">`BaseComparer` クラスは、`IEqualityComparer<BaseClass>` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-125">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="1c2b0-126"><xref:System.Collections.Generic.IEqualityComparer%601> インターフェイスが反変になったので、`BaseComparer` を使用して、`BaseClass` クラスを継承するクラスのインスタンスを比較することができます。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-126">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="1c2b0-127">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-127">This is shown in the following code example.</span></span>

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

<span data-ttu-id="1c2b0-128">詳しくは、「[ジェネリック コレクションに対するインターフェイスでの分散の使用 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-128">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="1c2b0-129">ジェネリック インターフェイスでの分散がサポートされるのは参照型だけです。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-129">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="1c2b0-130">値型は変性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-130">Value types do not support variance.</span></span> <span data-ttu-id="1c2b0-131">たとえば、整数は値型によって表されるため、`IEnumerable<int>` を暗黙的に `IEnumerable<object>` に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-131">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="1c2b0-132">また、バリアント インターフェイスを実装するクラスは、現在でもインバリアントであることを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="1c2b0-133">たとえば、<xref:System.Collections.Generic.List%601> が共変インターフェイス <xref:System.Collections.Generic.IEnumerable%601> を実装しても、`List<Object>` を `List<String>` に暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="1c2b0-134">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="1c2b0-134">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="1c2b0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c2b0-135">See also</span></span>

- [<span data-ttu-id="1c2b0-136">ジェネリック コレクションに対するインターフェイスでの分散の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-136">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="1c2b0-137">バリアント ジェネリック インターフェイスの作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-137">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [<span data-ttu-id="1c2b0-138">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c2b0-138">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="1c2b0-139">デリゲートの分散 (C#)</span><span class="sxs-lookup"><span data-stu-id="1c2b0-139">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
