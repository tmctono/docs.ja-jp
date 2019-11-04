---
title: 部分クラスと部分メソッド - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 2df3492274c2abceebf1d37b87be9cc9bb455b5f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419181"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="b4d5c-102">部分クラスと部分メソッド (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b4d5c-102">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="b4d5c-103">[クラス](../../language-reference/keywords/class.md)、[構造体](../../language-reference/keywords/struct.md)、[インターフェイス](../../language-reference/keywords/interface.md)やメソッドの定義を複数のソース ファイルに分割できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-103">It is possible to split the definition of a [class](../../language-reference/keywords/class.md), a [struct](../../language-reference/keywords/struct.md), an [interface](../../language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="b4d5c-104">各ソース ファイルには型やメソッドの定義のセクションが含まれ、分割されたすべての部分はアプリケーションのコンパイル時に結合されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="b4d5c-105">部分クラス</span><span class="sxs-lookup"><span data-stu-id="b4d5c-105">Partial Classes</span></span>

<span data-ttu-id="b4d5c-106">クラス定義を分割するのが望ましいのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-106">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="b4d5c-107">大型プロジェクトを開発する際にクラスを別個のファイルに分割すると、複数のプログラマーが同時にそのクラスの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="b4d5c-108">自動的に生成されたソースを使用する場合、ソース ファイルを再作成することなく、コードをクラスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="b4d5c-109">Visual Studio では、Windows フォームや Web サービス ラッパー コードなどを作成するときにこのアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="b4d5c-110">Visual Studio によって作成されたファイルを変更せずに、これらのクラスを使用するコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="b4d5c-111">クラス定義を分割するには、次のように [partial](../../language-reference/keywords/partial-type.md) キーワード修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-111">To split a class definition, use the [partial](../../language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="b4d5c-112">`partial` キーワードは、クラス、構造体、またはインターフェイスの他の部分を名前空間内で定義できることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="b4d5c-113">`partial` キーワードは、すべての部分で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="b4d5c-114">最終的な型を形成するためには、コンパイル時にすべての部分が利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="b4d5c-115">また、すべての部分で同じアクセシビリティ (`public` や `private` など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="b4d5c-116">abstract と宣言された部分がある場合、型全体が抽象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="b4d5c-117">sealed と宣言された部分がある場合、型全体が sealed と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="b4d5c-118">また、基本データ型を宣言する部分がある場合は、型全体が該当するクラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-118">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="b4d5c-119">基底クラスを指定する部分はすべて一致する必要がありますが、基底クラスを省略する部分も基本データ型を継承します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="b4d5c-120">部分は別の基本インターフェイスを指定でき、すべての部分宣言で示されたすべてのインターフェイスが最終的な型によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="b4d5c-121">部分定義で宣言されたクラス、構造体、インターフェイスの各メンバーは、他のすべての部分で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="b4d5c-122">最終的な型は、コンパイル時にすべての部分を結合して形成されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-122">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="b4d5c-123">`partial` 識別子は、デリゲートや列挙宣言では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="b4d5c-124">次の例は、入れ子にされた型は、それを包含する型自体が partial でない場合でも、partial にできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="b4d5c-125">部分型定義の属性は、コンパイル時に結合されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="b4d5c-126">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-126">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="b4d5c-127">これらは、次の宣言と等価です。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-127">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="b4d5c-128">各部分型定義に含まれる次の要素は、すべて結合されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-128">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="b4d5c-129">XML コメント</span><span class="sxs-lookup"><span data-stu-id="b4d5c-129">XML comments</span></span>

- <span data-ttu-id="b4d5c-130">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d5c-130">interfaces</span></span>

- <span data-ttu-id="b4d5c-131">ジェネリック型パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="b4d5c-131">generic-type parameter attributes</span></span>

- <span data-ttu-id="b4d5c-132">クラス属性</span><span class="sxs-lookup"><span data-stu-id="b4d5c-132">class attributes</span></span>

- <span data-ttu-id="b4d5c-133">メンバー</span><span class="sxs-lookup"><span data-stu-id="b4d5c-133">members</span></span>

<span data-ttu-id="b4d5c-134">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-134">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="b4d5c-135">これらは、次の宣言と等価です。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-135">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="b4d5c-136">制約</span><span class="sxs-lookup"><span data-stu-id="b4d5c-136">Restrictions</span></span>

<span data-ttu-id="b4d5c-137">部分クラス定義を使用する場合は、いくつかの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-137">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="b4d5c-138">同じ型の部分である部分型定義はすべて `partial` で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="b4d5c-139">たとえば、次のクラス宣言はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-139">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="b4d5c-140">`partial` 修飾子は、`class`、`struct`、または `interface` キーワードの直前にのみ配置できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="b4d5c-141">入れ子にされた部分型は、次の例に示すように、部分型定義で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="b4d5c-142">同じ型の部分である部分型定義は、すべて同じアセンブリおよび同じモジュール (.exe ファイルまたは .dll ファイル) 内で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="b4d5c-143">部分定義は、複数のモジュールにまたがることができません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-143">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="b4d5c-144">クラス名とジェネリック型パラメーターはすべての部分型定義で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="b4d5c-145">ジェネリック型は partial にできます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-145">Generic types can be partial.</span></span> <span data-ttu-id="b4d5c-146">それぞれの部分宣言では、同じパラメーター名を同じ順序で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-146">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="b4d5c-147">以下のキーワードは、部分型定義では省略できますが、ある 1 つの部分型定義に存在する場合は、同じ型の別の部分定義で指定されているキーワードと競合できません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="b4d5c-148">public</span><span class="sxs-lookup"><span data-stu-id="b4d5c-148">public</span></span>](../../language-reference/keywords/public.md)

  - [<span data-ttu-id="b4d5c-149">private</span><span class="sxs-lookup"><span data-stu-id="b4d5c-149">private</span></span>](../../language-reference/keywords/private.md)

  - [<span data-ttu-id="b4d5c-150">protected</span><span class="sxs-lookup"><span data-stu-id="b4d5c-150">protected</span></span>](../../language-reference/keywords/protected.md)

  - [<span data-ttu-id="b4d5c-151">internal</span><span class="sxs-lookup"><span data-stu-id="b4d5c-151">internal</span></span>](../../language-reference/keywords/internal.md)

  - [<span data-ttu-id="b4d5c-152">abstract</span><span class="sxs-lookup"><span data-stu-id="b4d5c-152">abstract</span></span>](../../language-reference/keywords/abstract.md)

  - [<span data-ttu-id="b4d5c-153">sealed</span><span class="sxs-lookup"><span data-stu-id="b4d5c-153">sealed</span></span>](../../language-reference/keywords/sealed.md)

  - <span data-ttu-id="b4d5c-154">基本クラス</span><span class="sxs-lookup"><span data-stu-id="b4d5c-154">base class</span></span>

  - <span data-ttu-id="b4d5c-155">[new](../../language-reference/keywords/new-modifier.md) 修飾子 (入れ子にされた部分)</span><span class="sxs-lookup"><span data-stu-id="b4d5c-155">[new](../../language-reference/keywords/new-modifier.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="b4d5c-156">ジェネリック制約</span><span class="sxs-lookup"><span data-stu-id="b4d5c-156">generic constraints</span></span>

<span data-ttu-id="b4d5c-157">詳細については、「[型パラメーターの制約](../generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-157">For more information, see [Constraints on Type Parameters](../generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="b4d5c-158">例 1</span><span class="sxs-lookup"><span data-stu-id="b4d5c-158">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="b4d5c-159">説明</span><span class="sxs-lookup"><span data-stu-id="b4d5c-159">Description</span></span>

<span data-ttu-id="b4d5c-160">次の例では、クラス `Coords` のフィールドとコンストラクターを 1 つの部分クラス定義で宣言し、メンバー `PrintCoords` を別の部分クラス定義で宣言しています。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="b4d5c-161">コード</span><span class="sxs-lookup"><span data-stu-id="b4d5c-161">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="b4d5c-162">例 2</span><span class="sxs-lookup"><span data-stu-id="b4d5c-162">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="b4d5c-163">説明</span><span class="sxs-lookup"><span data-stu-id="b4d5c-163">Description</span></span>

<span data-ttu-id="b4d5c-164">次の例は、部分構造体と部分インターフェイスも開発できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-164">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="b4d5c-165">コード</span><span class="sxs-lookup"><span data-stu-id="b4d5c-165">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="b4d5c-166">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d5c-166">Partial Methods</span></span>

<span data-ttu-id="b4d5c-167">部分クラスまたは構造体には部分メソッドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="b4d5c-168">クラスのある部分に、メソッドのシグネチャが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="b4d5c-169">同じ部分または別の部分に、オプションの実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="b4d5c-170">実装が指定されていない場合、メソッドとメソッドに対するすべての呼び出しは、コンパイル時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="b4d5c-171">部分メソッドを使用すると、イベントと同様に、クラスのある部分の実装者がメソッドを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="b4d5c-172">クラスの別の部分の実装者は、メソッドを実装するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="b4d5c-173">メソッドが実装されない場合、コンパイラは、メソッド シグネチャとメソッドに対するすべての呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="b4d5c-174">このメソッドの呼び出しは、呼び出しの引数の評価から発生するすべての結果を含め、実行時に影響を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="b4d5c-175">そのため、実装が指定されていない場合でも、部分クラス内のすべてのコードで部分メソッドを自由に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="b4d5c-176">実装されていないメソッドが呼び出された場合、コンパイル時エラーまたは実行時エラーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="b4d5c-177">部分メソッドは、生成されるコードをカスタマイズする方法として特に便利です。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="b4d5c-178">メソッドの名前とシグネチャを予約できるため、生成されるコードでメソッドを呼び出すことができます。ただし、メソッドを実装するかどうかは開発者が決定できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="b4d5c-179">部分クラスと同様に、部分メソッドでも、コード ジェネレーターによって作成されたコードと人間である開発者によって作成されたコードを実行時コストなしで連携させることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="b4d5c-180">部分メソッドの宣言は、定義と実装の 2 つの部分から成ります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="b4d5c-181">これらは部分クラスの別々の部分にあっても同じ部分にあってもかまいません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="b4d5c-182">実装宣言がない場合は、定義宣言とメソッドに対するすべての呼び出しの両方が、コンパイラによる最適化によって除外されます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="b4d5c-183">部分メソッドの宣言はコンテキスト キーワード [partial](../../language-reference/keywords/partial-type.md) で始まる必要があり、メソッドは [void](../../language-reference/keywords/void.md) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-183">Partial method declarations must begin with the contextual keyword [partial](../../language-reference/keywords/partial-type.md) and the method must return [void](../../language-reference/keywords/void.md).</span></span>

- <span data-ttu-id="b4d5c-184">部分メソッドには、[in](../../language-reference/keywords/in-parameter-modifier.md) や [ref](../../language-reference/keywords/ref.md) パラメーターを使用できますが、[out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-184">Partial methods can have [in](../../language-reference/keywords/in-parameter-modifier.md) or [ref](../../language-reference/keywords/ref.md) but not [out](../../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="b4d5c-185">部分メソッドは暗黙的に [private](../../language-reference/keywords/private.md) です。したがって部分メソッドを [virtual](../../language-reference/keywords/virtual.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-185">Partial methods are implicitly [private](../../language-reference/keywords/private.md), and therefore they cannot be [virtual](../../language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="b4d5c-186">部分メソッドを [extern](../../language-reference/keywords/extern.md) にすることはできません。部分メソッドの定義なのか実装なのかは、本体の存在で決まるためです。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-186">Partial methods cannot be [extern](../../language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="b4d5c-187">部分メソッドには [static](../../language-reference/keywords/static.md) 修飾子と [unsafe](../../language-reference/keywords/unsafe.md) 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-187">Partial methods can have [static](../../language-reference/keywords/static.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="b4d5c-188">部分メソッドはジェネリックにできます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-188">Partial methods can be generic.</span></span> <span data-ttu-id="b4d5c-189">制約は部分メソッドの定義宣言に置き、必要に応じて実装宣言で繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="b4d5c-190">パラメーター名と型パラメーター名は、定義宣言と実装宣言で同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="b4d5c-191">[delegate](../../language-reference/builtin-types/reference-types.md) は、定義および実装されている部分メソッドには使用できますが、定義されているのみの部分メソッドには使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-191">You can make a [delegate](../../language-reference/builtin-types/reference-types.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4d5c-192">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b4d5c-192">C# Language Specification</span></span>

<span data-ttu-id="b4d5c-193">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[部分型](~/_csharplang/spec/classes.md#partial-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b4d5c-194">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="b4d5c-194">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4d5c-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4d5c-195">See also</span></span>

- [<span data-ttu-id="b4d5c-196">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b4d5c-196">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b4d5c-197">クラス</span><span class="sxs-lookup"><span data-stu-id="b4d5c-197">Classes</span></span>](./classes.md)
- [<span data-ttu-id="b4d5c-198">構造体</span><span class="sxs-lookup"><span data-stu-id="b4d5c-198">Structs</span></span>](./structs.md)
- [<span data-ttu-id="b4d5c-199">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d5c-199">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="b4d5c-200">partial (型)</span><span class="sxs-lookup"><span data-stu-id="b4d5c-200">partial (Type)</span></span>](../../language-reference/keywords/partial-type.md)
