---
title: 名前空間の使用 - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 5193fc7aaae83cbc0c75e81835244eaaaece69a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700199"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="64172-102">名前空間の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="64172-102">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="64172-103">C# プログラム内では名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="64172-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="64172-104">最初の方法では、.NET Framework クラスで名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="64172-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="64172-105">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64172-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="64172-106">名前空間へのアクセス</span><span class="sxs-lookup"><span data-stu-id="64172-106">Accessing namespaces</span></span>

 <span data-ttu-id="64172-107">ほとんどの C# アプリケーションは `using` ディレクティブのセクションから始まります。</span><span class="sxs-lookup"><span data-stu-id="64172-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="64172-108">このセクションには、アプリケーションが頻繁に使用する名前空間がリストされ、包含されているメソッドが使用されるたびにプログラマが完全修飾名を指定しなくても済むようにします。</span><span class="sxs-lookup"><span data-stu-id="64172-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="64172-109">たとえば、次の行を記述したとします。</span><span class="sxs-lookup"><span data-stu-id="64172-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="64172-110">この場合、プログラムの開始位置で、以下のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64172-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="64172-111">次の表記の代わりに、</span><span class="sxs-lookup"><span data-stu-id="64172-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="64172-112">名前空間エイリアス</span><span class="sxs-lookup"><span data-stu-id="64172-112">Namespace aliases</span></span>

 <span data-ttu-id="64172-113">[`using` ディレクティブ](../../language-reference/keywords/using-directive.md)を使って、名前空間のエイリアスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="64172-113">You also can use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="64172-114">エイリアス化された名前空間のメンバーにアクセスするには、[名前空間エイリアス修飾子 `::`](../../language-reference/operators/namespace-alias-qualifier.md) を使います。</span><span class="sxs-lookup"><span data-stu-id="64172-114">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="64172-115">次の例では、名前空間エイリアスを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="64172-115">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="64172-116">名前空間を用いたスコープの制御</span><span class="sxs-lookup"><span data-stu-id="64172-116">Using namespaces to control scope</span></span>

 <span data-ttu-id="64172-117">`namespace` キーワードを使用して、スコープを宣言します。</span><span class="sxs-lookup"><span data-stu-id="64172-117">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="64172-118">プロジェクト内でスコープを作成すると、コードの編成が容易になり、グローバルに一意の型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="64172-118">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="64172-119">次の例では、入れ子関係にある 2 つの名前空間で `SampleClass` というクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="64172-119">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="64172-120">[メンバー アクセス `.` 演算子](../../language-reference/operators/member-access-operators.md#member-access-operator-)は、呼び出されるメソッドを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="64172-120">The [member access `.` operator](../../language-reference/operators/member-access-operators.md#member-access-operator-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="64172-121">完全修飾名</span><span class="sxs-lookup"><span data-stu-id="64172-121">Fully qualified names</span></span>

 <span data-ttu-id="64172-122">名前空間と型には、論理階層を示す完全修飾名で表された一意のタイトルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="64172-122">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="64172-123">たとえば、ステートメント `A.B` は、`A` が名前空間または型の名前であり、`B` はその内部で入れ子になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="64172-123">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="64172-124">入れ子になっているクラスと名前空間を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="64172-124">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="64172-125">完全修飾名は、各エンティティの後のコメントとして示されています。</span><span class="sxs-lookup"><span data-stu-id="64172-125">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="64172-126">上のコード セグメントの各要素の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64172-126">In the previous code segment:</span></span>  
  
- <span data-ttu-id="64172-127">名前空間 `N1` はグローバル名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="64172-127">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="64172-128">その完全修飾名は `N1` です。</span><span class="sxs-lookup"><span data-stu-id="64172-128">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="64172-129">名前空間 `N2` は `N1` のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="64172-129">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="64172-130">その完全修飾名は `N1.N2` です。</span><span class="sxs-lookup"><span data-stu-id="64172-130">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="64172-131">クラス `C1` は `N1` のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="64172-131">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="64172-132">その完全修飾名は `N1.C1` です。</span><span class="sxs-lookup"><span data-stu-id="64172-132">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="64172-133">クラス名 `C2` は、このコードでは 2 回使用されています。</span><span class="sxs-lookup"><span data-stu-id="64172-133">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="64172-134">ただし、完全修飾名は異なります。</span><span class="sxs-lookup"><span data-stu-id="64172-134">However, the fully qualified names are unique.</span></span> <span data-ttu-id="64172-135">`C2` の最初のインスタンスは `C1` 内で宣言されているため、その完全修飾名は `N1.C1.C2` となります。</span><span class="sxs-lookup"><span data-stu-id="64172-135">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="64172-136">`C2` の 2 つ目のインスタンスは名前空間 `N2` 内で宣言されているため、その完全修飾名は `N1.N2.C2` となります。</span><span class="sxs-lookup"><span data-stu-id="64172-136">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="64172-137">上のコード セグメントを使用して、次のように新しいクラス メンバー `C3` を名前空間 `N1.N2` に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="64172-137">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="64172-138">通常、[名前空間エイリアス修飾子 `::`](../../language-reference/operators/namespace-alias-qualifier.md) は名前空間エイリアスを参照するために使い、`global::` はグローバル名前空間を参照するために使います。`.` は型またはメンバーを修飾するために使います。</span><span class="sxs-lookup"><span data-stu-id="64172-138">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="64172-139">名前空間ではなく型を参照するエイリアスで `::` を使用するのは誤りです。</span><span class="sxs-lookup"><span data-stu-id="64172-139">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="64172-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="64172-140">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="64172-141">`global` という語は定義済みのエイリアスではないため、`global.X` には特別な意味がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64172-141">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="64172-142">`::` と共に使用したときにのみ特別な意味が与えられます。</span><span class="sxs-lookup"><span data-stu-id="64172-142">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="64172-143">`global::` は常にグローバル名前空間を参照し、エイリアスを参照しないので、global という名前のエイリアスを定義すると、コンパイラ警告 CS0440 が生成されます。</span><span class="sxs-lookup"><span data-stu-id="64172-143">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="64172-144">たとえば、次のコード行では警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="64172-144">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="64172-145">エイリアスで `::` を使用することをお勧めします。そうすれば、追加の型が予想外に導入されることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="64172-145">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="64172-146">たとえば、次の例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="64172-146">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="64172-147">このコードは動作しますが、`Alias` という名前の型が後で導入された場合、`Alias.` は代わりにその型にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="64172-147">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="64172-148">`Alias::Exception` を使用すれば、`Alias` は名前空間エイリアスとして扱われ、型と間違われることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="64172-148">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="64172-149">参照</span><span class="sxs-lookup"><span data-stu-id="64172-149">See also</span></span>

- [<span data-ttu-id="64172-150">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="64172-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="64172-151">名前空間</span><span class="sxs-lookup"><span data-stu-id="64172-151">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="64172-152">演算子 .</span><span class="sxs-lookup"><span data-stu-id="64172-152">. operator</span></span>](../../language-reference/operators/member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="64172-153">:: 演算子</span><span class="sxs-lookup"><span data-stu-id="64172-153">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="64172-154">extern エイリアス</span><span class="sxs-lookup"><span data-stu-id="64172-154">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
