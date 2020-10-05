---
description: static 修飾子 - C# リファレンス
title: static 修飾子 - C# リファレンス
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: ccd575748c2286fa7348e2880acbfadd036d9ccd
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247723"
---
# <a name="static-c-reference"></a><span data-ttu-id="f6bce-103">static (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f6bce-103">static (C# Reference)</span></span>

<span data-ttu-id="f6bce-104">このページでは、`static` 修飾子キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6bce-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="f6bce-105">`static` キーワードも [`using static`](using-static.md) ディレクティブに含まれます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="f6bce-106">`static` 修飾子は、静的メンバーの宣言に使用します。静的メンバーは、特定のオブジェクトではなく、型自体に属するメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f6bce-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="f6bce-107">`static` 修飾子は `static` クラスの宣言に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="f6bce-108">クラス、インターフェイス、構造体では、`static` 修飾子をフィールド、メソッド、プロパティ、演算子、イベント、コンストラクターに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="f6bce-109">`static` 修飾子はインデクサーおよびファイナライザーと併用できません。</span><span class="sxs-lookup"><span data-stu-id="f6bce-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="f6bce-110">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6bce-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="f6bce-111">C# 9.0 以降では、`static` 修飾子を[ラムダ式](../operators/lambda-expressions.md)または[匿名メソッド](../operators/delegate-operator.md)に追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-111">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="f6bce-112">静的ラムダまたは匿名メソッドでは、ローカル変数またはインスタンスの状態をキャプチャすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6bce-112">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="f6bce-113">例 - 静的クラス</span><span class="sxs-lookup"><span data-stu-id="f6bce-113">Example - static class</span></span>

<span data-ttu-id="f6bce-114">次のクラスは `static` として宣言され、`static` メソッドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-114">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="f6bce-115">定数宣言や型宣言は暗黙的な `static` メンバーです。</span><span class="sxs-lookup"><span data-stu-id="f6bce-115">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="f6bce-116">`static` メンバーはインスタンスを使って参照できません。</span><span class="sxs-lookup"><span data-stu-id="f6bce-116">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="f6bce-117">代わりに、型の名前を使って参照します。</span><span class="sxs-lookup"><span data-stu-id="f6bce-117">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="f6bce-118">たとえば、次のクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-118">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="f6bce-119">`static` メンバー `x` を参照するには、同じスコープからその静的メンバーにアクセス可能でない限り、完全修飾名 (`MyBaseC.MyStruct.x`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6bce-119">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="f6bce-120">クラスのインスタンスには、そのクラスのインスタンス フィールドすべてにそれぞれのコピーが含まれていますが、各 `static` フィールドのコピーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="f6bce-120">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="f6bce-121">`static` メソッドまたはプロパティ アクセサーへの参照には、[`this`](this.md) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f6bce-121">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="f6bce-122">`static` キーワードをクラスに適用する場合、そのクラスのすべてのメンバーが `static` でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f6bce-122">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="f6bce-123">クラス、インターフェイス、`static` クラスには、`static` コンストラクターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-123">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="f6bce-124">`static` コンストラクターは、プログラムが開始されてからクラスがインスタンス化されるまでの間に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-124">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="f6bce-125">`static` キーワードの用法は、C++ の場合よりも制限されています。</span><span class="sxs-lookup"><span data-stu-id="f6bce-125">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="f6bce-126">C++ キーワードと比較するには、「[ストレージ クラス (C++)](/cpp/cpp/storage-classes-cpp#static)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6bce-126">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="f6bce-127">`static` メンバーの例を示すために、ある企業の従業員を表すクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-127">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="f6bce-128">このクラスには、従業員数を数えるメソッドと、従業員数を格納するフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="f6bce-128">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="f6bce-129">メソッドとフィールドはどちらも、従業員のインスタンスに属しておらず、</span><span class="sxs-lookup"><span data-stu-id="f6bce-129">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="f6bce-130">全体として従業員のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="f6bce-130">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="f6bce-131">クラスの `static` メンバーとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bce-131">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="f6bce-132">例 - 静的フィールドとメソッド</span><span class="sxs-lookup"><span data-stu-id="f6bce-132">Example - static field and method</span></span>

<span data-ttu-id="f6bce-133">この例では、新しい従業員の名前と ID を読み取り、従業員数のカウンターを 1 つインクリメントして、新しい従業員の情報と従業員数を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6bce-133">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="f6bce-134">このプログラムでは、現在の従業員数がキーボードから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-134">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="f6bce-135">例 - 静的な初期化</span><span class="sxs-lookup"><span data-stu-id="f6bce-135">Example - static initialization</span></span>

<span data-ttu-id="f6bce-136">この例では、まだ宣言されていない別の `static` フィールドを使用することで `static` フィールドを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f6bce-136">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="f6bce-137">`static` フィールドに値を明示的に割り当てるまで、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="f6bce-137">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="f6bce-138">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f6bce-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f6bce-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6bce-139">See also</span></span>

- [<span data-ttu-id="f6bce-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f6bce-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6bce-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f6bce-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6bce-142">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="f6bce-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f6bce-143">修飾子</span><span class="sxs-lookup"><span data-stu-id="f6bce-143">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f6bce-144">using static ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f6bce-144">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="f6bce-145">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="f6bce-145">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
