---
title: 宣言型コードと命令型コードの混在のバグ (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: f12b1ab4-bb92-4b92-a648-0525e45b3ce7
ms.openlocfilehash: 369fae59516df785ac686645d47e74e69a8f1457
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331646"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-visual-basic"></a><span data-ttu-id="59086-102">宣言型コードと命令型コードの混在のバグ (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59086-102">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="59086-103">には、XML ツリーを直接変更できるさまざまなメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59086-103">contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="59086-104">たとえば、要素の追加、要素の削除、要素の内容の変更、属性の追加などの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59086-104">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="59086-105">このプログラミングインターフェイスについては、「 [XML ツリーの変更 (LINQ to XML)」 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59086-105">This programming interface is described in [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span> <span data-ttu-id="59086-106">いずれかの軸 (<xref:System.Xml.Linq.XContainer.Elements%2A> など) を反復処理する場合に、その過程で XML ツリーを変更すると、見慣れないバグが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="59086-106">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="59086-107">この問題は、"ハロウィーン問題" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="59086-107">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="59086-108">問題の定義</span><span class="sxs-lookup"><span data-stu-id="59086-108">Definition of the Problem</span></span>  
 <span data-ttu-id="59086-109">コレクションを反復処理するコードを LINQ を使用して記述する場合は、宣言型スタイルでコードを記述することになります。</span><span class="sxs-lookup"><span data-stu-id="59086-109">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="59086-110">この場合、*どのように*処理するかではなく、*何が*必要かを記述します。</span><span class="sxs-lookup"><span data-stu-id="59086-110">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="59086-111">たとえば、1) 最初の要素を取得する、2) この要素を何らかの条件に対してテストする、3) この要素を変更する、4) この要素をリストに戻す、というコードを記述した場合、それは命令型のコードです。</span><span class="sxs-lookup"><span data-stu-id="59086-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="59086-112">必要な処理を*どのように*行うかをコンピューターに指示しています。</span><span class="sxs-lookup"><span data-stu-id="59086-112">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="59086-113">この 2 つのスタイルのコードが同じ操作に混在していると、問題の原因になります。</span><span class="sxs-lookup"><span data-stu-id="59086-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="59086-114">次のような項目を考慮します。</span><span class="sxs-lookup"><span data-stu-id="59086-114">Consider the following:</span></span>  
  
 <span data-ttu-id="59086-115">3 つの項目 (a、b、および c) を含むリンク リストがあるとします。</span><span class="sxs-lookup"><span data-stu-id="59086-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="59086-116">このリンク リスト内を移動しながら 3 つの新しい項目 (a'、b'、および c') を追加して、</span><span class="sxs-lookup"><span data-stu-id="59086-116">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="59086-117">次のようなリンク リストが生成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="59086-117">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="59086-118">ここで、リストを反復処理して各項目の後ろに新しいアイテムを追加するコードを記述した場合、</span><span class="sxs-lookup"><span data-stu-id="59086-118">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="59086-119">その結果は、コードによって最初に `a` 要素が検出され、その後ろに `a'` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="59086-119">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="59086-120">その後、リストの次のノードに移動しますが、それは既に `a'` になっています。</span><span class="sxs-lookup"><span data-stu-id="59086-120">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="59086-121">そのため、新しい項目として `a''` がリストに追加されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="59086-121">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="59086-122">現実にこのような問題が発生したら、どうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="59086-122">How would you solve this in the real world?</span></span> <span data-ttu-id="59086-123">まず、元のリンク リストをコピーして、まったく新しいリストを作成する方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="59086-123">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="59086-124">また、純粋な命令型のコードを記述するのであれば、最初の項目を検出し、新しい項目を追加したら、リンク リストの 2 つ先 (追加した要素を越えた先) に移動するという方法もあります。</span><span class="sxs-lookup"><span data-stu-id="59086-124">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="59086-125">反復処理と追加</span><span class="sxs-lookup"><span data-stu-id="59086-125">Adding While Iterating</span></span>  
 <span data-ttu-id="59086-126">たとえば、ツリーのすべての要素に対してその複製となる要素を作成するコードを記述するとします。</span><span class="sxs-lookup"><span data-stu-id="59086-126">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
```  
  
 <span data-ttu-id="59086-127">このコードは、無限ループに入ります。</span><span class="sxs-lookup"><span data-stu-id="59086-127">This code goes into an infinite loop.</span></span> <span data-ttu-id="59086-128">`foreach` ステートメントは、`Elements()` 軸を反復処理して `doc` 要素に新しい要素を追加しますが、</span><span class="sxs-lookup"><span data-stu-id="59086-128">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="59086-129">追加した要素も反復処理されることになります。</span><span class="sxs-lookup"><span data-stu-id="59086-129">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="59086-130">ループが繰り返されるたびに新しいオブジェクトが割り当てられるため、最後には使用可能なメモリがすべて消費されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="59086-130">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="59086-131">この問題を修正するには、次のように、標準クエリ演算子の <xref:System.Linq.Enumerable.ToList%2A> を使用してコレクションをメモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="59086-131">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="59086-132">これで、コードが機能するようになります。</span><span class="sxs-lookup"><span data-stu-id="59086-132">Now the code works.</span></span> <span data-ttu-id="59086-133">結果の XML ツリーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="59086-133">The resulting XML tree is the following:</span></span>  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="59086-134">反復処理と削除</span><span class="sxs-lookup"><span data-stu-id="59086-134">Deleting While Iterating</span></span>  
 <span data-ttu-id="59086-135">特定のレベルのノードをすべて削除する場合、次のようなコードを記述することが考えられます。</span><span class="sxs-lookup"><span data-stu-id="59086-135">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="59086-136">しかし、これでは目的の操作は行われません。</span><span class="sxs-lookup"><span data-stu-id="59086-136">However, this does not do what you want.</span></span> <span data-ttu-id="59086-137">最初の要素 A を削除すると、ルートに含まれる XML ツリーから A が削除されるため、反復処理を行っている Elements メソッド内のコードが次の要素を見つけられなくなります。</span><span class="sxs-lookup"><span data-stu-id="59086-137">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="59086-138">上のコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="59086-138">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="59086-139">この問題を解決するには、先ほどと同じように、<xref:System.Linq.Enumerable.ToList%2A> を呼び出してコレクションを具体化します。</span><span class="sxs-lookup"><span data-stu-id="59086-139">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="59086-140">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="59086-140">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="59086-141">他の方法として、親要素で <xref:System.Xml.Linq.XElement.RemoveAll%2A> を呼び出して、反復処理を完全に取り除くこともできます。</span><span class="sxs-lookup"><span data-stu-id="59086-141">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
root.RemoveAll()  
Console.WriteLine(root)  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="59086-142">この問題が LINQ で自動的に処理されない理由</span><span class="sxs-lookup"><span data-stu-id="59086-142">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="59086-143">まず、レイジー評価を行う代わりに常にすべてをメモリに読み込む方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="59086-143">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="59086-144">しかし、この方法では、パフォーマンスとメモリ使用量のコストが非常に高くなります。</span><span class="sxs-lookup"><span data-stu-id="59086-144">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="59086-145">実際、仮に LINQ (LINQ to XML) でこの方法を使用したとしても、現実には使いものにならないでしょう。</span><span class="sxs-lookup"><span data-stu-id="59086-145">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="59086-146">その他に、ある種のトランザクション構文を LINQ に追加して、コンパイラがコードを分析して特定のコレクションを具体化する必要があるかどうかを特定するようにする方法も考えられます。</span><span class="sxs-lookup"><span data-stu-id="59086-146">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="59086-147">しかし、副作用のあるコードをすべて特定しようとすると非常に複雑になります。</span><span class="sxs-lookup"><span data-stu-id="59086-147">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="59086-148">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="59086-148">Consider the following code:</span></span>  
  
```vb  
Dim z = _  
    From e In root.Elements() _  
    Where (TestSomeCondition(e)) _  
    Select DoMyProjection(e)  
```  
  
 <span data-ttu-id="59086-149">このような分析コードで副作用のあるコードの有無を特定するには、TestSomeCondition および DoMyProjection の 2 つのメソッドと、これらが呼び出すすべてのメソッドを分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59086-149">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="59086-150">しかし、その分析コードでは、ただ副作用のあるコードを探すだけでなく、</span><span class="sxs-lookup"><span data-stu-id="59086-150">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="59086-151">この状況では、`root` の子要素に対して副作用があるコードのみを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59086-151">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="59086-152">LINQ to XML ではこのような分析は行われません。</span><span class="sxs-lookup"><span data-stu-id="59086-152">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="59086-153">これらの問題は、開発者が回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59086-153">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="59086-154">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="59086-154">Guidance</span></span>  
 <span data-ttu-id="59086-155">第 1 に、宣言型のコードと命令型のコードを混在させないようにします。</span><span class="sxs-lookup"><span data-stu-id="59086-155">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="59086-156">仮に、コレクションのセマンティクスと、XML ツリーを変更するメソッドのセマンティクスを正確に把握していて、このカテゴリの問題を巧妙に回避するコードを記述できたとしても、将来そのコードの保守を行う別の開発者が同じようにこの問題に通じているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="59086-156">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="59086-157">宣言型と命令型のコーディング スタイルが混在していると、コードが不安定になります。</span><span class="sxs-lookup"><span data-stu-id="59086-157">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="59086-158">これらの問題を回避するためにコレクションを具体化するコードを記述する場合は、コードを保守するプログラマが問題を把握できるように、必要に応じてコメントを付けるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="59086-158">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="59086-159">第 2 に、パフォーマンスやその他の事情が許すのであれば、宣言型のコードのみを使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="59086-159">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="59086-160">既存の XML ツリーは変更せずに、</span><span class="sxs-lookup"><span data-stu-id="59086-160">Don't modify your existing XML tree.</span></span> <span data-ttu-id="59086-161">新しいツリーを生成します。</span><span class="sxs-lookup"><span data-stu-id="59086-161">Generate a new one.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
Dim newRoot As XElement = New XElement("Root", _  
    root.Elements(), root.Elements())  
Console.WriteLine(newRoot)  
```  
  
## <a name="see-also"></a><span data-ttu-id="59086-162">参照</span><span class="sxs-lookup"><span data-stu-id="59086-162">See also</span></span>

- [<span data-ttu-id="59086-163">高度な LINQ to XML プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59086-163">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
