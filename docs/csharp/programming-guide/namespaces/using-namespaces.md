---
title: 名前空間の使用 - C# プログラミング ガイド
description: C# プログラミングで名前空間を使用する方法について説明します。たとえば、名前空間へのアクセス、名前空間エイリアス、名前空間を使用したスコープの制御などです。
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 86892f50e059c16ee9c133d7ba9f2716e11a8e56
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381698"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="e644e-103">名前空間の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e644e-103">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="e644e-104">C# プログラム内では名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="e644e-104">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="e644e-105">最初の方法では、.NET クラスで名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="e644e-105">Firstly, the .NET classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="e644e-106">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e644e-106">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="e644e-107">名前空間へのアクセス</span><span class="sxs-lookup"><span data-stu-id="e644e-107">Accessing namespaces</span></span>

 <span data-ttu-id="e644e-108">ほとんどの C# アプリケーションは `using` ディレクティブのセクションから始まります。</span><span class="sxs-lookup"><span data-stu-id="e644e-108">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="e644e-109">このセクションには、アプリケーションが頻繁に使用する名前空間がリストされ、包含されているメソッドが使用されるたびにプログラマが完全修飾名を指定しなくても済むようにします。</span><span class="sxs-lookup"><span data-stu-id="e644e-109">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="e644e-110">たとえば、次の行を記述したとします。</span><span class="sxs-lookup"><span data-stu-id="e644e-110">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="e644e-111">この場合、プログラムの開始位置で、以下のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e644e-111">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="e644e-112">これは次のコードの代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="e644e-112">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="e644e-113">名前空間エイリアス</span><span class="sxs-lookup"><span data-stu-id="e644e-113">Namespace aliases</span></span>

 <span data-ttu-id="e644e-114">[`using` ディレクティブ](../../language-reference/keywords/using-directive.md)を使って、名前空間のエイリアスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e644e-114">You can also use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="e644e-115">エイリアス化された名前空間のメンバーにアクセスするには、[名前空間エイリアス修飾子 `::`](../../language-reference/operators/namespace-alias-qualifier.md) を使います。</span><span class="sxs-lookup"><span data-stu-id="e644e-115">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="e644e-116">次の例では、名前空間エイリアスを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e644e-116">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="e644e-117">名前空間を用いたスコープの制御</span><span class="sxs-lookup"><span data-stu-id="e644e-117">Using namespaces to control scope</span></span>

 <span data-ttu-id="e644e-118">`namespace` キーワードを使用して、スコープを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e644e-118">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="e644e-119">プロジェクト内でスコープを作成すると、コードの編成が容易になり、グローバルに一意の型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e644e-119">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="e644e-120">次の例では、入れ子関係にある 2 つの名前空間で `SampleClass` というクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="e644e-120">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="e644e-121">[`.` トークン](../../language-reference/operators/member-access-operators.md#member-access-expression-)を使用して、呼び出されるメソッドを区別します。</span><span class="sxs-lookup"><span data-stu-id="e644e-121">The [`.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="e644e-122">完全修飾名</span><span class="sxs-lookup"><span data-stu-id="e644e-122">Fully qualified names</span></span>

 <span data-ttu-id="e644e-123">名前空間と型には、論理階層を示す完全修飾名で表された一意のタイトルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="e644e-123">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="e644e-124">たとえば、ステートメント `A.B` は、`A` が名前空間または型の名前であり、`B` はその内部で入れ子になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e644e-124">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="e644e-125">入れ子になっているクラスと名前空間を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="e644e-125">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="e644e-126">完全修飾名は、各エンティティの後のコメントとして示されています。</span><span class="sxs-lookup"><span data-stu-id="e644e-126">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="e644e-127">上のコード セグメントの各要素の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e644e-127">In the previous code segment:</span></span>  
  
- <span data-ttu-id="e644e-128">名前空間 `N1` はグローバル名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="e644e-128">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="e644e-129">その完全修飾名は `N1` です。</span><span class="sxs-lookup"><span data-stu-id="e644e-129">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="e644e-130">名前空間 `N2` は `N1` のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="e644e-130">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="e644e-131">その完全修飾名は `N1.N2` です。</span><span class="sxs-lookup"><span data-stu-id="e644e-131">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="e644e-132">クラス `C1` は `N1` のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="e644e-132">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="e644e-133">その完全修飾名は `N1.C1` です。</span><span class="sxs-lookup"><span data-stu-id="e644e-133">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="e644e-134">クラス名 `C2` は、このコードでは 2 回使用されています。</span><span class="sxs-lookup"><span data-stu-id="e644e-134">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="e644e-135">ただし、完全修飾名は異なります。</span><span class="sxs-lookup"><span data-stu-id="e644e-135">However, the fully qualified names are unique.</span></span> <span data-ttu-id="e644e-136">`C2` の最初のインスタンスは `C1` 内で宣言されているため、その完全修飾名は `N1.C1.C2` となります。</span><span class="sxs-lookup"><span data-stu-id="e644e-136">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="e644e-137">`C2` の 2 つ目のインスタンスは名前空間 `N2` 内で宣言されているため、その完全修飾名は `N1.N2.C2` となります。</span><span class="sxs-lookup"><span data-stu-id="e644e-137">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="e644e-138">上のコード セグメントを使用して、次のように新しいクラス メンバー `C3` を名前空間 `N1.N2` に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e644e-138">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="e644e-139">通常、[名前空間エイリアス修飾子 `::`](../../language-reference/operators/namespace-alias-qualifier.md) は名前空間エイリアスを参照するために使い、`global::` はグローバル名前空間を参照するために使います。`.` は型またはメンバーを修飾するために使います。</span><span class="sxs-lookup"><span data-stu-id="e644e-139">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="e644e-140">名前空間ではなく型を参照するエイリアスで `::` を使用するのは誤りです。</span><span class="sxs-lookup"><span data-stu-id="e644e-140">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="e644e-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e644e-141">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="e644e-142">`global` という語は定義済みのエイリアスではないため、`global.X` には特別な意味がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e644e-142">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="e644e-143">`::` と共に使用したときにのみ特別な意味が与えられます。</span><span class="sxs-lookup"><span data-stu-id="e644e-143">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="e644e-144">`global::` は常にグローバル名前空間を参照し、エイリアスを参照しないので、global という名前のエイリアスを定義すると、コンパイラ警告 CS0440 が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e644e-144">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="e644e-145">たとえば、次のコード行では警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e644e-145">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="e644e-146">エイリアスで `::` を使用することをお勧めします。そうすれば、追加の型が予想外に導入されることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e644e-146">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="e644e-147">たとえば、次の例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="e644e-147">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="e644e-148">このコードは動作しますが、`Alias` という名前の型が後で導入された場合、`Alias.` は代わりにその型にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e644e-148">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="e644e-149">`Alias::Exception` を使用すれば、`Alias` は名前空間エイリアスとして扱われ、型と間違われることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="e644e-149">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e644e-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="e644e-150">See also</span></span>

- [<span data-ttu-id="e644e-151">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e644e-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e644e-152">名前空間</span><span class="sxs-lookup"><span data-stu-id="e644e-152">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="e644e-153">メンバー アクセス式</span><span class="sxs-lookup"><span data-stu-id="e644e-153">Member access expression</span></span>](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [<span data-ttu-id="e644e-154">:: 演算子</span><span class="sxs-lookup"><span data-stu-id="e644e-154">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="e644e-155">extern エイリアス</span><span class="sxs-lookup"><span data-stu-id="e644e-155">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
