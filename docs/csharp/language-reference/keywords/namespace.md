---
title: 名前空間キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b35f0a2a5cc0b2895b491d4ee24f89955f4b8fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625801"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="32791-102">namespace (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="32791-102">namespace (C# Reference)</span></span>

<span data-ttu-id="32791-103">`namespace` キーワードは、関連する一連のオブジェクトを含む範囲を宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="32791-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="32791-104">名前空間を利用し、コード要素を整理したり、グローバルに一意の型を作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="32791-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="32791-105">解説</span><span class="sxs-lookup"><span data-stu-id="32791-105">Remarks</span></span>

<span data-ttu-id="32791-106">名前空間内では、以下の型を 0 個以上宣言できます。</span><span class="sxs-lookup"><span data-stu-id="32791-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="32791-107">別の名前空間</span><span class="sxs-lookup"><span data-stu-id="32791-107">another namespace</span></span>

- [<span data-ttu-id="32791-108">class</span><span class="sxs-lookup"><span data-stu-id="32791-108">class</span></span>](class.md)

- [<span data-ttu-id="32791-109">interface</span><span class="sxs-lookup"><span data-stu-id="32791-109">interface</span></span>](interface.md)

- [<span data-ttu-id="32791-110">struct</span><span class="sxs-lookup"><span data-stu-id="32791-110">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="32791-111">enum</span><span class="sxs-lookup"><span data-stu-id="32791-111">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="32791-112">delegate</span><span class="sxs-lookup"><span data-stu-id="32791-112">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="32791-113">C# ソース ファイル内に名前空間を明示的に宣言しているかどうかに関係なく、コンパイラは既定の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="32791-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="32791-114">この無名の名前空間はグローバル名前空間とも呼ばれますが、すべてのファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="32791-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="32791-115">グローバル名前空間内にある識別子は、名前付き名前空間で利用できます。</span><span class="sxs-lookup"><span data-stu-id="32791-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="32791-116">名前空間には暗黙的にパブリック アクセスが設定されます。この属性は変更できません。</span><span class="sxs-lookup"><span data-stu-id="32791-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="32791-117">名前空間内の要素に割り当てることができるアクセス修飾子については、「[アクセス修飾子](access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32791-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="32791-118">名前空間は、2 つ以上の宣言で定義できます。</span><span class="sxs-lookup"><span data-stu-id="32791-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="32791-119">たとえば、次の例では、`MyCompany` 名前空間の一部として 2 つのクラスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="32791-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="32791-120">例</span><span class="sxs-lookup"><span data-stu-id="32791-120">Example</span></span>

<span data-ttu-id="32791-121">入れ子になった名前空間で静的なメソッドを呼び出す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32791-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="32791-122">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="32791-122">C# language specification</span></span>

<span data-ttu-id="32791-123">詳細については、[C# 言語仕様](~/_csharplang/spec/namespaces.md)に関する記事の「[名前空間](~/_csharplang/spec/introduction.md)」に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32791-123">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32791-124">参照</span><span class="sxs-lookup"><span data-stu-id="32791-124">See also</span></span>

- [<span data-ttu-id="32791-125">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="32791-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="32791-126">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="32791-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="32791-127">using</span><span class="sxs-lookup"><span data-stu-id="32791-127">using</span></span>](using-directive.md)
- [<span data-ttu-id="32791-128">using static</span><span class="sxs-lookup"><span data-stu-id="32791-128">using static</span></span>](using-static.md)
- [<span data-ttu-id="32791-129">名前空間エイリアス修飾子 `::`</span><span class="sxs-lookup"><span data-stu-id="32791-129">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="32791-130">名前空間</span><span class="sxs-lookup"><span data-stu-id="32791-130">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
