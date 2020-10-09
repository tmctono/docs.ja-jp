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
ms.openlocfilehash: 239163fc2f91ccbfe8b1c111a358db87d36a8308
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654640"
---
# <a name="static-c-reference"></a><span data-ttu-id="74dbb-103">static (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="74dbb-103">static (C# Reference)</span></span>

<span data-ttu-id="74dbb-104">このページでは、`static` 修飾子キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="74dbb-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="74dbb-105">`static` キーワードも [`using static`](using-static.md) ディレクティブに含まれます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="74dbb-106">`static` 修飾子は、静的メンバーの宣言に使用します。静的メンバーは、特定のオブジェクトではなく、型自体に属するメンバーです。</span><span class="sxs-lookup"><span data-stu-id="74dbb-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="74dbb-107">`static` 修飾子は `static` クラスの宣言に使用できます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="74dbb-108">クラス、インターフェイス、構造体では、`static` 修飾子をフィールド、メソッド、プロパティ、演算子、イベント、コンストラクターに追加できます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="74dbb-109">`static` 修飾子はインデクサーおよびファイナライザーと併用できません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="74dbb-110">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74dbb-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="74dbb-111">C# 8.0 以降では、[ローカル関数](../../programming-guide/classes-and-structs/local-functions.md)に `static` 修飾子を追加できます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-111">Beginning with C# 8.0, you can add the `static` modifier to a [local function](../../programming-guide/classes-and-structs/local-functions.md).</span></span> <span data-ttu-id="74dbb-112">静的なローカル関数では、ローカル変数やインスタンスの状態をキャプチャすることはできません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-112">A static local function can't capture local variables or instance state.</span></span>

<span data-ttu-id="74dbb-113">C# 9.0 以降では、`static` 修飾子を[ラムダ式](../operators/lambda-expressions.md)または[匿名メソッド](../operators/delegate-operator.md)に追加できます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-113">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="74dbb-114">静的ラムダまたは匿名メソッドでは、ローカル変数またはインスタンスの状態をキャプチャすることはできません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-114">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="74dbb-115">例 - 静的クラス</span><span class="sxs-lookup"><span data-stu-id="74dbb-115">Example - static class</span></span>

<span data-ttu-id="74dbb-116">次のクラスは `static` として宣言され、`static` メソッドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-116">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="74dbb-117">定数宣言や型宣言は暗黙的な `static` メンバーです。</span><span class="sxs-lookup"><span data-stu-id="74dbb-117">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="74dbb-118">`static` メンバーはインスタンスを使って参照できません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-118">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="74dbb-119">代わりに、型の名前を使って参照します。</span><span class="sxs-lookup"><span data-stu-id="74dbb-119">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="74dbb-120">たとえば、次のクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-120">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="74dbb-121">`static` メンバー `x` を参照するには、同じスコープからその静的メンバーにアクセス可能でない限り、完全修飾名 (`MyBaseC.MyStruct.x`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="74dbb-121">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="74dbb-122">クラスのインスタンスには、そのクラスのインスタンス フィールドすべてにそれぞれのコピーが含まれていますが、各 `static` フィールドのコピーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="74dbb-122">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="74dbb-123">`static` メソッドまたはプロパティ アクセサーへの参照には、[`this`](this.md) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-123">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="74dbb-124">`static` キーワードをクラスに適用する場合、そのクラスのすべてのメンバーが `static` でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="74dbb-124">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="74dbb-125">クラス、インターフェイス、`static` クラスには、`static` コンストラクターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-125">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="74dbb-126">`static` コンストラクターは、プログラムが開始されてからクラスがインスタンス化されるまでの間に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-126">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="74dbb-127">`static` キーワードの用法は、C++ の場合よりも制限されています。</span><span class="sxs-lookup"><span data-stu-id="74dbb-127">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="74dbb-128">C++ キーワードと比較するには、「[ストレージ クラス (C++)](/cpp/cpp/storage-classes-cpp#static)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74dbb-128">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="74dbb-129">`static` メンバーの例を示すために、ある企業の従業員を表すクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-129">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="74dbb-130">このクラスには、従業員数を数えるメソッドと、従業員数を格納するフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="74dbb-130">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="74dbb-131">メソッドとフィールドはどちらも、従業員のインスタンスに属しておらず、</span><span class="sxs-lookup"><span data-stu-id="74dbb-131">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="74dbb-132">全体として従業員のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="74dbb-132">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="74dbb-133">クラスの `static` メンバーとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74dbb-133">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="74dbb-134">例 - 静的フィールドとメソッド</span><span class="sxs-lookup"><span data-stu-id="74dbb-134">Example - static field and method</span></span>

<span data-ttu-id="74dbb-135">この例では、新しい従業員の名前と ID を読み取り、従業員数のカウンターを 1 つインクリメントして、新しい従業員の情報と従業員数を表示します。</span><span class="sxs-lookup"><span data-stu-id="74dbb-135">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="74dbb-136">このプログラムでは、現在の従業員数がキーボードから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-136">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="74dbb-137">例 - 静的な初期化</span><span class="sxs-lookup"><span data-stu-id="74dbb-137">Example - static initialization</span></span>

<span data-ttu-id="74dbb-138">この例では、まだ宣言されていない別の `static` フィールドを使用することで `static` フィールドを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="74dbb-138">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="74dbb-139">`static` フィールドに値を明示的に割り当てるまで、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="74dbb-139">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="74dbb-140">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="74dbb-140">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="74dbb-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="74dbb-141">See also</span></span>

- [<span data-ttu-id="74dbb-142">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="74dbb-142">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="74dbb-143">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="74dbb-143">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="74dbb-144">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="74dbb-144">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="74dbb-145">修飾子</span><span class="sxs-lookup"><span data-stu-id="74dbb-145">Modifiers</span></span>](index.md)
- [<span data-ttu-id="74dbb-146">using static ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="74dbb-146">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="74dbb-147">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="74dbb-147">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
