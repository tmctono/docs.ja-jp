---
title: ジェネリック インターフェイス (Visual Basic) の変性
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: 93e169f658a855e3b271e3e3affeadac5d7e5032
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642381"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="cca48-102">ジェネリック インターフェイス (Visual Basic) の変性</span><span class="sxs-lookup"><span data-stu-id="cca48-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="cca48-103">.NET Framework 4 では、既存のいくつかのジェネリック インターフェイスに対して、変性のサポートが導入されています。</span><span class="sxs-lookup"><span data-stu-id="cca48-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="cca48-104">変性のサポートにより、これらのインターフェイスを実装するクラスの暗黙的な変換が可能になりました。</span><span class="sxs-lookup"><span data-stu-id="cca48-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="cca48-105">次のインターフェイスは、新たにバリアントになりました。</span><span class="sxs-lookup"><span data-stu-id="cca48-105">The following interfaces are now variant:</span></span>  
  
- <span data-ttu-id="cca48-106"><xref:System.Collections.Generic.IEnumerable%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="cca48-107"><xref:System.Collections.Generic.IEnumerator%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="cca48-108"><xref:System.Linq.IQueryable%601> (T は共変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="cca48-109"><xref:System.Linq.IGrouping%602> (`TKey` と `TElement` は共変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
- <span data-ttu-id="cca48-110"><xref:System.Collections.Generic.IComparer%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
- <span data-ttu-id="cca48-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
- <span data-ttu-id="cca48-112"><xref:System.IComparable%601> (T は反変です)</span><span class="sxs-lookup"><span data-stu-id="cca48-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="cca48-113">共変性により、メソッドの戻り値の型の派生を、インターフェイスのジェネリック型パラメーターで定義されている型よりも強くすることができます。</span><span class="sxs-lookup"><span data-stu-id="cca48-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="cca48-114">ここでは、共変性機能について説明するために、`IEnumerable(Of Object)` および `IEnumerable(Of String)` というジェネリック インターフェイスについて考えます。</span><span class="sxs-lookup"><span data-stu-id="cca48-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="cca48-115">`IEnumerable(Of String)` インターフェイスは、`IEnumerable(Of Object)` インターフェイスを継承しません。</span><span class="sxs-lookup"><span data-stu-id="cca48-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="cca48-116">ただし、`String` 型は `Object` 型を継承します。場合によっては、これらのインターフェイスのオブジェクトを、相互に割り当てる必要が生じることもあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="cca48-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="cca48-117">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cca48-117">This is shown in the following code example.</span></span>  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 <span data-ttu-id="cca48-118">このコードで .NET Framework の以前のバージョンと Visual Basic でコンパイル エラーが発生`Option Strict On`します。</span><span class="sxs-lookup"><span data-stu-id="cca48-118">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="cca48-119">今後は、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスが共変になったので、上記の例のように、`objects` の代わりに `strings` を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cca48-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="cca48-120">反変性により、メソッドの引数の型の派生を、インターフェイスのジェネリック パラメーターで指定されている型よりも弱くすることができます。</span><span class="sxs-lookup"><span data-stu-id="cca48-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="cca48-121">ここでは、反変性について説明するために、`BaseClass` クラスのインスタンスを比較するための `BaseComparer` クラスを作成した場合について考えます。</span><span class="sxs-lookup"><span data-stu-id="cca48-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="cca48-122">`BaseComparer` クラスは、`IEqualityComparer(Of BaseClass)` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="cca48-122">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="cca48-123"><xref:System.Collections.Generic.IEqualityComparer%601> インターフェイスが反変になったので、`BaseComparer` を使用して、`BaseClass` クラスを継承するクラスのインスタンスを比較することができます。</span><span class="sxs-lookup"><span data-stu-id="cca48-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="cca48-124">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cca48-124">This is shown in the following code example.</span></span>  
  
```vb  
' Simple hierarchy of classes.  
Class BaseClass  
End Class  
  
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
' Comparer class.  
Class BaseComparer  
    Implements IEqualityComparer(Of BaseClass)  
  
    Public Function Equals1(ByVal x As BaseClass,  
                            ByVal y As BaseClass) As Boolean _  
                            Implements IEqualityComparer(Of BaseClass).Equals  
        Return (x.Equals(y))  
    End Function  
  
    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _  
        Implements IEqualityComparer(Of BaseClass).GetHashCode  
        Return obj.GetHashCode  
    End Function  
End Class  
Sub Test()  
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer  
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to   
    ' IEqualityComparer(Of DerivedClass).  
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer  
End Sub  
```  
  
 <span data-ttu-id="cca48-125">例については、次を参照してください。 [(Visual Basic) のジェネリック コレクションに対するインターフェイスでの変性の使用](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)します。</span><span class="sxs-lookup"><span data-stu-id="cca48-125">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="cca48-126">ジェネリック インターフェイスでの変性がサポートされるのは参照型だけです。</span><span class="sxs-lookup"><span data-stu-id="cca48-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="cca48-127">値型は変性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cca48-127">Value types do not support variance.</span></span> <span data-ttu-id="cca48-128">たとえば、整数は値型によって表されるため、`IEnumerable(Of Integer)` を暗黙的に `IEnumerable(Of Object)` に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="cca48-128">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
```vb  
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)  
' The following statement generates a compiler error  
' with Option Strict On, because Integer is a value type.  
' Dim objects As IEnumerable(Of Object) = integers  
```  
  
 <span data-ttu-id="cca48-129">また、バリアント インターフェイスを実装するクラスは、現在でもインバリアントであることを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="cca48-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="cca48-130">たとえば、<xref:System.Collections.Generic.List%601> が共変インターフェイス <xref:System.Collections.Generic.IEnumerable%601> を実装しても、`List(Of Object)` を `List(Of String)` に暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="cca48-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="cca48-131">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cca48-131">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca48-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="cca48-132">See also</span></span>

- [<span data-ttu-id="cca48-133">ジェネリック コレクションに対するインターフェイスでの変性の使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca48-133">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="cca48-134">バリアント ジェネリック インターフェイスの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca48-134">Creating Variant Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [<span data-ttu-id="cca48-135">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cca48-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="cca48-136">デリゲートの変性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca48-136">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
