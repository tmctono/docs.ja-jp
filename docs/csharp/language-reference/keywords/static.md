---
title: static 修飾子 - C# リファレンス
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 771bcfdac4c4bf27c15da4bc374d804405317a78
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102061"
---
# <a name="static-c-reference"></a><span data-ttu-id="02517-102">static (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="02517-102">static (C# Reference)</span></span>

<span data-ttu-id="02517-103">このページでは、`static` 修飾子キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02517-103">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="02517-104">`static` キーワードも [`using static`](using-static.md) ディレクティブに含まれます。</span><span class="sxs-lookup"><span data-stu-id="02517-104">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="02517-105">`static` 修飾子は、静的メンバーの宣言に使用します。静的メンバーは、特定のオブジェクトではなく、型自体に属するメンバーです。</span><span class="sxs-lookup"><span data-stu-id="02517-105">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="02517-106">`static` 修飾子は `static` クラスの宣言に使用できます。</span><span class="sxs-lookup"><span data-stu-id="02517-106">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="02517-107">クラス、インターフェイス、構造体では、`static` 修飾子をフィールド、メソッド、プロパティ、演算子、イベント、コンストラクターに追加できます。</span><span class="sxs-lookup"><span data-stu-id="02517-107">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="02517-108">`static` 修飾子はインデクサーおよびファイナライザーと併用できません。</span><span class="sxs-lookup"><span data-stu-id="02517-108">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="02517-109">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02517-109">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="02517-110">例 - 静的クラス</span><span class="sxs-lookup"><span data-stu-id="02517-110">Example - static class</span></span>

<span data-ttu-id="02517-111">次のクラスは `static` として宣言され、`static` メソッドのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02517-111">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="02517-112">定数宣言や型宣言は暗黙的な `static` メンバーです。</span><span class="sxs-lookup"><span data-stu-id="02517-112">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="02517-113">`static` メンバーはインスタンスを使って参照できません。</span><span class="sxs-lookup"><span data-stu-id="02517-113">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="02517-114">代わりに、型の名前を使って参照します。</span><span class="sxs-lookup"><span data-stu-id="02517-114">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="02517-115">たとえば、次のクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="02517-115">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="02517-116">`static` メンバー `x` を参照するには、同じスコープからその静的メンバーにアクセス可能でない限り、完全修飾名 (`MyBaseC.MyStruct.x`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="02517-116">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="02517-117">クラスのインスタンスには、そのクラスのインスタンス フィールドすべてにそれぞれのコピーが含まれていますが、各 `static` フィールドのコピーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="02517-117">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="02517-118">`static` メソッドまたはプロパティ アクセサーへの参照には、[`this`](this.md) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="02517-118">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="02517-119">`static` キーワードをクラスに適用する場合、そのクラスのすべてのメンバーが `static` でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="02517-119">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="02517-120">クラス、インターフェイス、`static` クラスには、`static` コンストラクターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="02517-120">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="02517-121">`static` コンストラクターは、プログラムが開始されてからクラスがインスタンス化されるまでの間に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="02517-121">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="02517-122">`static` キーワードの用法は、C++ の場合よりも制限されています。</span><span class="sxs-lookup"><span data-stu-id="02517-122">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="02517-123">C++ キーワードと比較するには、「[ストレージ クラス (C++)](/cpp/cpp/storage-classes-cpp#static)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02517-123">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="02517-124">`static` メンバーの例を示すために、ある企業の従業員を表すクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="02517-124">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="02517-125">このクラスには、従業員数を数えるメソッドと、従業員数を格納するフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="02517-125">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="02517-126">メソッドとフィールドはどちらも、従業員のインスタンスに属しておらず、</span><span class="sxs-lookup"><span data-stu-id="02517-126">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="02517-127">全体として従業員のクラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="02517-127">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="02517-128">クラスの `static` メンバーとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02517-128">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="02517-129">例 - 静的フィールドとメソッド</span><span class="sxs-lookup"><span data-stu-id="02517-129">Example - static field and method</span></span>

<span data-ttu-id="02517-130">この例では、新しい従業員の名前と ID を読み取り、従業員数のカウンターを 1 つインクリメントして、新しい従業員の情報と従業員数を表示します。</span><span class="sxs-lookup"><span data-stu-id="02517-130">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="02517-131">このプログラムでは、現在の従業員数がキーボードから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="02517-131">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="02517-132">例 - 静的な初期化</span><span class="sxs-lookup"><span data-stu-id="02517-132">Example - static initialization</span></span>

<span data-ttu-id="02517-133">この例では、まだ宣言されていない別の `static` フィールドを使用することで `static` フィールドを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="02517-133">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="02517-134">`static` フィールドに値を明示的に割り当てるまで、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="02517-134">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="02517-135">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="02517-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="02517-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="02517-136">See also</span></span>

- [<span data-ttu-id="02517-137">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="02517-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02517-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="02517-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02517-139">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="02517-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="02517-140">修飾子</span><span class="sxs-lookup"><span data-stu-id="02517-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="02517-141">using static ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="02517-141">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="02517-142">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="02517-142">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
