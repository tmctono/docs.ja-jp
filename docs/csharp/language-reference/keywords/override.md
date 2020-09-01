---
description: override 修飾子 - C# リファレンス
title: override 修飾子 - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 51ca806310214981b7ff24a796fe078d902dca4d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134459"
---
# <a name="override-c-reference"></a><span data-ttu-id="0f0b5-103">override (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0f0b5-103">override (C# Reference)</span></span>

<span data-ttu-id="0f0b5-104">`override` 修飾子は、継承したメソッド、プロパティ、インデクサー、またはイベントの抽象実装または仮想実装を拡張したり修飾したりする際に必要です。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="0f0b5-105">例</span><span class="sxs-lookup"><span data-stu-id="0f0b5-105">Example</span></span>

<span data-ttu-id="0f0b5-106">この例では、`Square` クラスが `GetArea` のオーバーライドされる実装を提供する必要があります。これは、`GetArea` が `Shape` 抽象クラスから継承されているためです。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-106">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="0f0b5-107">`override` メソッドは、基底クラスから継承されるメンバーの新しい実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="0f0b5-108">`override` 宣言によってオーバーライドされるメソッドを、オーバーライドされる基本メソッドと言います。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="0f0b5-109">オーバーライドされる基本メソッドには、`override` メソッドと同じシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="0f0b5-110">継承については、「[継承](../../programming-guide/classes-and-structs/inheritance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-110">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="0f0b5-111">非仮想メソッドまたは静的メソッドをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="0f0b5-112">オーバーライドされる基本メソッドは、`virtual`、`abstract`、`override` のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="0f0b5-113">`override` 宣言は、`virtual` メソッドのアクセシビリティを変更できません。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="0f0b5-114">`override` メソッドと `virtual` メソッドの両方に、同じ[アクセス レベル修飾子](access-modifiers.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-114">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="0f0b5-115">`override` メソッドの修飾に、修飾子 `new`、`static`、または `virtual` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="0f0b5-116">オーバーライドするプロパティの宣言では、継承されるプロパティとまったく同じアクセス修飾子、型、および名前を指定する必要があります。オーバーライドされるプロパティは、`virtual`、`abstract`、または `override` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="0f0b5-117">`override` キーワードの使い方の詳細については、「[Override キーワードと New キーワードによるバージョン管理](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)」および「[Override キーワードと New キーワードを使用する場合について](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="0f0b5-118">例</span><span class="sxs-lookup"><span data-stu-id="0f0b5-118">Example</span></span>

<span data-ttu-id="0f0b5-119">この例では、`Employee` という基底クラスと、`SalesEmployee` という派生クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="0f0b5-120">`SalesEmployee` クラスには追加のフィールド `salesbonus` があり、このフィールドを処理に含めるために、`CalculatePay` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-120">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="0f0b5-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="0f0b5-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0f0b5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f0b5-122">See also</span></span>

- [<span data-ttu-id="0f0b5-123">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0f0b5-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0f0b5-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0f0b5-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0f0b5-125">継承</span><span class="sxs-lookup"><span data-stu-id="0f0b5-125">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="0f0b5-126">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="0f0b5-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0f0b5-127">修飾子</span><span class="sxs-lookup"><span data-stu-id="0f0b5-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0f0b5-128">abstract</span><span class="sxs-lookup"><span data-stu-id="0f0b5-128">abstract</span></span>](abstract.md)
- [<span data-ttu-id="0f0b5-129">virtual</span><span class="sxs-lookup"><span data-stu-id="0f0b5-129">virtual</span></span>](virtual.md)
- [<span data-ttu-id="0f0b5-130">new (修飾子)</span><span class="sxs-lookup"><span data-stu-id="0f0b5-130">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="0f0b5-131">ポリモーフィズム</span><span class="sxs-lookup"><span data-stu-id="0f0b5-131">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
