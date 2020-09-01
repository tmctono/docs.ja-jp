---
description: static 修飾子 - C# リファレンス
title: static 修飾子 - C# リファレンス
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f42636d1bbdf4342297f46f50ec6dfc2a70eacad
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142064"
---
# <a name="static-c-reference"></a><span data-ttu-id="299d2-103">static (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="299d2-103">static (C# Reference)</span></span>

<span data-ttu-id="299d2-104">このページでは、`static` 修飾子キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="299d2-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="299d2-105">`static` キーワードも [`using static`](using-static.md) ディレクティブに含まれます。</span><span class="sxs-lookup"><span data-stu-id="299d2-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="299d2-106">`static` 修飾子は、静的メンバーの宣言に使用します。静的メンバーは、特定のオブジェクトではなく、型自体に属するメンバーです。</span><span class="sxs-lookup"><span data-stu-id="299d2-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="299d2-107">`static` 修飾子は `static` クラスの宣言に使用できます。</span><span class="sxs-lookup"><span data-stu-id="299d2-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="299d2-108">クラス、インターフェイス、構造体では、`static` 修飾子をフィールド、メソッド、プロパティ、演算子、イベント、コンストラクターに追加できます。</span><span class="sxs-lookup"><span data-stu-id="299d2-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="299d2-109">`static` 修飾子はインデクサーおよびファイナライザーと併用できません。</span><span class="sxs-lookup"><span data-stu-id="299d2-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="299d2-110">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="299d2-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="299d2-111">例 - 静的クラス</span><span class="sxs-lookup"><span data-stu-id="299d2-111">Example - static class</span></span>

<span data-ttu-id="299d2-112">次のクラスは `static` として宣言され、`static` メソッドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="299d2-112">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="299d2-113">定数宣言や型宣言は暗黙的な `static` メンバーです。</span><span class="sxs-lookup"><span data-stu-id="299d2-113">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="299d2-114">`static` メンバーはインスタンスを使って参照できません。</span><span class="sxs-lookup"><span data-stu-id="299d2-114">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="299d2-115">代わりに、型の名前を使って参照します。</span><span class="sxs-lookup"><span data-stu-id="299d2-115">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="299d2-116">たとえば、次のクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="299d2-116">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="299d2-117">`static` メンバー `x` を参照するには、同じスコープからその静的メンバーにアクセス可能でない限り、完全修飾名 (`MyBaseC.MyStruct.x`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="299d2-117">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="299d2-118">クラスのインスタンスには、そのクラスのインスタンス フィールドすべてにそれぞれのコピーが含まれていますが、各 `static` フィールドのコピーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="299d2-118">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="299d2-119">`static` メソッドまたはプロパティ アクセサーへの参照には、[`this`](this.md) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="299d2-119">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="299d2-120">`static` キーワードをクラスに適用する場合、そのクラスのすべてのメンバーが `static` でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="299d2-120">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="299d2-121">クラス、インターフェイス、`static` クラスには、`static` コンストラクターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="299d2-121">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="299d2-122">`static` コンストラクターは、プログラムが開始されてからクラスがインスタンス化されるまでの間に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="299d2-122">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="299d2-123">`static` キーワードの用法は、C++ の場合よりも制限されています。</span><span class="sxs-lookup"><span data-stu-id="299d2-123">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="299d2-124">C++ キーワードと比較するには、「[ストレージ クラス (C++)](/cpp/cpp/storage-classes-cpp#static)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="299d2-124">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="299d2-125">`static` メンバーの例を示すために、ある企業の従業員を表すクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="299d2-125">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="299d2-126">このクラスには、従業員数を数えるメソッドと、従業員数を格納するフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="299d2-126">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="299d2-127">メソッドとフィールドはどちらも、従業員のインスタンスに属しておらず、</span><span class="sxs-lookup"><span data-stu-id="299d2-127">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="299d2-128">全体として従業員のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="299d2-128">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="299d2-129">クラスの `static` メンバーとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="299d2-129">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="299d2-130">例 - 静的フィールドとメソッド</span><span class="sxs-lookup"><span data-stu-id="299d2-130">Example - static field and method</span></span>

<span data-ttu-id="299d2-131">この例では、新しい従業員の名前と ID を読み取り、従業員数のカウンターを 1 つインクリメントして、新しい従業員の情報と従業員数を表示します。</span><span class="sxs-lookup"><span data-stu-id="299d2-131">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="299d2-132">このプログラムでは、現在の従業員数がキーボードから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="299d2-132">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="299d2-133">例 - 静的な初期化</span><span class="sxs-lookup"><span data-stu-id="299d2-133">Example - static initialization</span></span>

<span data-ttu-id="299d2-134">この例では、まだ宣言されていない別の `static` フィールドを使用することで `static` フィールドを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="299d2-134">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="299d2-135">`static` フィールドに値を明示的に割り当てるまで、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="299d2-135">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="299d2-136">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="299d2-136">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="299d2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="299d2-137">See also</span></span>

- [<span data-ttu-id="299d2-138">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="299d2-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="299d2-139">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="299d2-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="299d2-140">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="299d2-140">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="299d2-141">修飾子</span><span class="sxs-lookup"><span data-stu-id="299d2-141">Modifiers</span></span>](index.md)
- [<span data-ttu-id="299d2-142">using static ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="299d2-142">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="299d2-143">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="299d2-143">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
