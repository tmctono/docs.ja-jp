---
title: 部分クラスと部分メソッド - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 0d54101badab297457e8d8ecf277898fc6908779
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481056"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="8c1a2-102">部分クラスと部分メソッド (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8c1a2-102">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="8c1a2-103">[クラス](../../../csharp/language-reference/keywords/class.md)、[構造体](../../../csharp/language-reference/keywords/struct.md)、[インターフェイス](../../../csharp/language-reference/keywords/interface.md)やメソッドの定義を複数のソース ファイルに分割できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md), a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="8c1a2-104">各ソース ファイルには型やメソッドの定義のセクションが含まれ、分割されたすべての部分はアプリケーションのコンパイル時に結合されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="8c1a2-105">部分クラス</span><span class="sxs-lookup"><span data-stu-id="8c1a2-105">Partial Classes</span></span>

<span data-ttu-id="8c1a2-106">クラス定義を分割するのが望ましいのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-106">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="8c1a2-107">大型プロジェクトを開発する際にクラスを別個のファイルに分割すると、複数のプログラマーが同時にそのクラスの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="8c1a2-108">自動的に生成されたソースを使用する場合、ソース ファイルを再作成することなく、コードをクラスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="8c1a2-109">Visual Studio では、Windows フォームや Web サービス ラッパー コードなどを作成するときにこのアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="8c1a2-110">Visual Studio によって作成されたファイルを変更せずに、これらのクラスを使用するコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="8c1a2-111">クラス定義を分割するには、次のように [partial](../../../csharp/language-reference/keywords/partial-type.md) キーワード修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="8c1a2-112">`partial` キーワードは、クラス、構造体、またはインターフェイスの他の部分を名前空間内で定義できることを示します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="8c1a2-113">`partial` キーワードは、すべての部分で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="8c1a2-114">最終的な型を形成するためには、コンパイル時にすべての部分が利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="8c1a2-115">また、すべての部分で同じアクセシビリティ (`public` や `private` など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="8c1a2-116">abstract と宣言された部分がある場合、型全体が抽象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="8c1a2-117">sealed と宣言された部分がある場合、型全体が sealed と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="8c1a2-118">また、基本データ型を宣言する部分がある場合は、型全体が該当するクラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-118">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="8c1a2-119">基底クラスを指定する部分はすべて一致する必要がありますが、基底クラスを省略する部分も基本データ型を継承します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="8c1a2-120">部分は別の基本インターフェイスを指定でき、すべての部分宣言で示されたすべてのインターフェイスが最終的な型によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="8c1a2-121">部分定義で宣言されたクラス、構造体、インターフェイスの各メンバーは、他のすべての部分で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="8c1a2-122">最終的な型は、コンパイル時にすべての部分を結合して形成されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-122">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="8c1a2-123">`partial` 識別子は、デリゲートや列挙宣言では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="8c1a2-124">次の例は、入れ子にされた型は、それを包含する型自体が partial でない場合でも、partial にできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="8c1a2-125">部分型定義の属性は、コンパイル時に結合されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="8c1a2-126">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-126">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="8c1a2-127">これらは、次の宣言と等価です。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-127">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="8c1a2-128">各部分型定義に含まれる次の要素は、すべて結合されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-128">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="8c1a2-129">XML コメント</span><span class="sxs-lookup"><span data-stu-id="8c1a2-129">XML comments</span></span>

- <span data-ttu-id="8c1a2-130">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c1a2-130">interfaces</span></span>

- <span data-ttu-id="8c1a2-131">ジェネリック型パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="8c1a2-131">generic-type parameter attributes</span></span>

- <span data-ttu-id="8c1a2-132">クラス属性</span><span class="sxs-lookup"><span data-stu-id="8c1a2-132">class attributes</span></span>

- <span data-ttu-id="8c1a2-133">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c1a2-133">members</span></span>

<span data-ttu-id="8c1a2-134">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-134">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="8c1a2-135">これらは、次の宣言と等価です。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-135">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="8c1a2-136">制約</span><span class="sxs-lookup"><span data-stu-id="8c1a2-136">Restrictions</span></span>

<span data-ttu-id="8c1a2-137">部分クラス定義を使用する場合は、いくつかの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-137">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="8c1a2-138">同じ型の部分である部分型定義はすべて `partial` で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="8c1a2-139">たとえば、次のクラス宣言はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-139">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="8c1a2-140">`partial` 修飾子は、`class`、`struct`、または `interface` キーワードの直前にのみ配置できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="8c1a2-141">入れ子にされた部分型は、次の例に示すように、部分型定義で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="8c1a2-142">同じ型の部分である部分型定義は、すべて同じアセンブリおよび同じモジュール (.exe ファイルまたは .dll ファイル) 内で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="8c1a2-143">部分定義は、複数のモジュールにまたがることができません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-143">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="8c1a2-144">クラス名とジェネリック型パラメーターはすべての部分型定義で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="8c1a2-145">ジェネリック型は partial にできます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-145">Generic types can be partial.</span></span> <span data-ttu-id="8c1a2-146">それぞれの部分宣言では、同じパラメーター名を同じ順序で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-146">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="8c1a2-147">以下のキーワードは、部分型定義では省略できますが、ある 1 つの部分型定義に存在する場合は、同じ型の別の部分定義で指定されているキーワードと競合できません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="8c1a2-148">public</span><span class="sxs-lookup"><span data-stu-id="8c1a2-148">public</span></span>](../../../csharp/language-reference/keywords/public.md)

  - [<span data-ttu-id="8c1a2-149">private</span><span class="sxs-lookup"><span data-stu-id="8c1a2-149">private</span></span>](../../../csharp/language-reference/keywords/private.md)

  - [<span data-ttu-id="8c1a2-150">protected</span><span class="sxs-lookup"><span data-stu-id="8c1a2-150">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

  - [<span data-ttu-id="8c1a2-151">internal</span><span class="sxs-lookup"><span data-stu-id="8c1a2-151">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

  - [<span data-ttu-id="8c1a2-152">abstract</span><span class="sxs-lookup"><span data-stu-id="8c1a2-152">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

  - [<span data-ttu-id="8c1a2-153">sealed</span><span class="sxs-lookup"><span data-stu-id="8c1a2-153">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

  - <span data-ttu-id="8c1a2-154">基本クラス</span><span class="sxs-lookup"><span data-stu-id="8c1a2-154">base class</span></span>

  - <span data-ttu-id="8c1a2-155">[new](../../../csharp/language-reference/keywords/new.md) 修飾子 (入れ子にされた部分)</span><span class="sxs-lookup"><span data-stu-id="8c1a2-155">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="8c1a2-156">ジェネリック制約</span><span class="sxs-lookup"><span data-stu-id="8c1a2-156">generic constraints</span></span>

<span data-ttu-id="8c1a2-157">詳細については、「[型パラメーターの制約](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-157">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="8c1a2-158">例 1</span><span class="sxs-lookup"><span data-stu-id="8c1a2-158">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="8c1a2-159">説明</span><span class="sxs-lookup"><span data-stu-id="8c1a2-159">Description</span></span>

<span data-ttu-id="8c1a2-160">次の例では、クラス `Coords` のフィールドとコンストラクターを 1 つの部分クラス定義で宣言し、メンバー `PrintCoords` を別の部分クラス定義で宣言しています。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="8c1a2-161">コード</span><span class="sxs-lookup"><span data-stu-id="8c1a2-161">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="8c1a2-162">例 2</span><span class="sxs-lookup"><span data-stu-id="8c1a2-162">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="8c1a2-163">説明</span><span class="sxs-lookup"><span data-stu-id="8c1a2-163">Description</span></span>

<span data-ttu-id="8c1a2-164">次の例は、部分構造体と部分インターフェイスも開発できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-164">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="8c1a2-165">コード</span><span class="sxs-lookup"><span data-stu-id="8c1a2-165">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="8c1a2-166">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="8c1a2-166">Partial Methods</span></span>

<span data-ttu-id="8c1a2-167">部分クラスまたは構造体には部分メソッドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="8c1a2-168">クラスのある部分に、メソッドのシグネチャが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="8c1a2-169">同じ部分または別の部分に、オプションの実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="8c1a2-170">実装が指定されていない場合、メソッドとメソッドに対するすべての呼び出しは、コンパイル時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="8c1a2-171">部分メソッドを使用すると、イベントと同様に、クラスのある部分の実装者がメソッドを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="8c1a2-172">クラスの別の部分の実装者は、メソッドを実装するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="8c1a2-173">メソッドが実装されない場合、コンパイラは、メソッド シグネチャとメソッドに対するすべての呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="8c1a2-174">このメソッドの呼び出しは、呼び出しの引数の評価から発生するすべての結果を含め、実行時に影響を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="8c1a2-175">そのため、実装が指定されていない場合でも、部分クラス内のすべてのコードで部分メソッドを自由に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="8c1a2-176">実装されていないメソッドが呼び出された場合、コンパイル時エラーまたは実行時エラーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="8c1a2-177">部分メソッドは、生成されるコードをカスタマイズする方法として特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="8c1a2-178">メソッドの名前とシグネチャを予約できるため、生成されるコードでメソッドを呼び出すことができます。ただし、メソッドを実装するかどうかは開発者が決定できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="8c1a2-179">部分クラスと同様に、部分メソッドでも、コード ジェネレーターによって作成されたコードと人間である開発者によって作成されたコードを実行時コストなしで連携させることができます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="8c1a2-180">部分メソッドの宣言は、定義と実装の 2 つの部分から成ります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="8c1a2-181">これらは部分クラスの別々の部分にあっても同じ部分にあってもかまいません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="8c1a2-182">実装宣言がない場合は、定義宣言とメソッドに対するすべての呼び出しの両方が、コンパイラによる最適化によって除外されます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="8c1a2-183">部分メソッドの宣言はコンテキスト キーワード [partial](../../../csharp/language-reference/keywords/partial-type.md) で始まる必要があり、メソッドは [void](../../../csharp/language-reference/keywords/void.md) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-183">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>

- <span data-ttu-id="8c1a2-184">部分メソッドには、[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) や [ref](../../../csharp/language-reference/keywords/ref.md) パラメーターを使用できますが、[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-184">Partial methods can have [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="8c1a2-185">部分メソッドは暗黙的に [private](../../../csharp/language-reference/keywords/private.md) です。したがって部分メソッドを [virtual](../../../csharp/language-reference/keywords/virtual.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-185">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="8c1a2-186">部分メソッドを [extern](../../../csharp/language-reference/keywords/extern.md) にすることはできません。部分メソッドの定義なのか実装なのかは、本体の存在で決まるためです。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-186">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="8c1a2-187">部分メソッドには [static](../../../csharp/language-reference/keywords/static.md) 修飾子と [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-187">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="8c1a2-188">部分メソッドはジェネリックにできます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-188">Partial methods can be generic.</span></span> <span data-ttu-id="8c1a2-189">制約は部分メソッドの定義宣言に置き、必要に応じて実装宣言で繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="8c1a2-190">パラメーター名と型パラメーター名は、定義宣言と実装宣言で同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="8c1a2-191">[delegate](../../../csharp/language-reference/keywords/delegate.md) は、定義および実装されている部分メソッドには使用できますが、定義されているのみの部分メソッドには使用できません。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-191">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8c1a2-192">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="8c1a2-192">C# Language Specification</span></span>

<span data-ttu-id="8c1a2-193">詳細については、「[C# 言語仕様](../../language-reference/language-specification/index.md)」の[部分型](~/_csharplang/spec/classes.md#partial-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="8c1a2-194">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="8c1a2-194">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c1a2-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c1a2-195">See also</span></span>

- [<span data-ttu-id="8c1a2-196">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8c1a2-196">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8c1a2-197">クラス</span><span class="sxs-lookup"><span data-stu-id="8c1a2-197">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="8c1a2-198">構造体</span><span class="sxs-lookup"><span data-stu-id="8c1a2-198">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="8c1a2-199">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c1a2-199">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="8c1a2-200">partial (型)</span><span class="sxs-lookup"><span data-stu-id="8c1a2-200">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
