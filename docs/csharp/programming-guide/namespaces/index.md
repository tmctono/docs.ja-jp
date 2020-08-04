---
title: 名前空間 - C# プログラミング ガイド
description: C# でのプログラミングにおける名前空間について説明します。 名前空間のプロパティの概要およびその他のリソースについて参照してください。
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: fca2c641520bd9cd19a48bff2119a6f09c3713ea
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382101"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="93930-104">名前空間 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="93930-104">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="93930-105">C# プログラミングでは、名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="93930-105">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="93930-106">最初の方法では、次のように .NET で名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="93930-106">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="93930-107"><xref:System> は名前空間で、<xref:System.Console> はその名前空間内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="93930-107"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="93930-108">以下の例のように、`using` キーワードを使用できるため、完全な名前は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="93930-108">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]

<span data-ttu-id="93930-109">詳細については、「[using ディレクティブ](../../language-reference/keywords/using-directive.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93930-109">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="93930-110">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="93930-110">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="93930-111">名前空間を宣言するには、以下の例のように、[namespace](../../language-reference/keywords/namespace.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="93930-111">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="93930-112">名前空間の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93930-112">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="93930-113">名前空間の概要</span><span class="sxs-lookup"><span data-stu-id="93930-113">Namespaces overview</span></span>

<span data-ttu-id="93930-114">名前空間には次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="93930-114">Namespaces have the following properties:</span></span>

- <span data-ttu-id="93930-115">大きなコード プロジェクトを整理します。</span><span class="sxs-lookup"><span data-stu-id="93930-115">They organize large code projects.</span></span>
- <span data-ttu-id="93930-116">`.` 演算子を使用して、区切られます。</span><span class="sxs-lookup"><span data-stu-id="93930-116">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="93930-117">`using` ディレクティブを使用すると、クラスごとに名前空間の名前を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="93930-117">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="93930-118">`global` 名前空間は "ルート" 名前空間です。`global::System` は常に .NET 名前空間の <xref:System> を参照します。</span><span class="sxs-lookup"><span data-stu-id="93930-118">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="93930-119">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="93930-119">C# language specification</span></span>

<span data-ttu-id="93930-120">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関する記事の「[名前空間](~/_csharplang/spec/namespaces.md)」に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93930-120">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93930-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="93930-121">See also</span></span>

- [<span data-ttu-id="93930-122">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="93930-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="93930-123">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="93930-123">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="93930-124">My 名前空間を使用する方法</span><span class="sxs-lookup"><span data-stu-id="93930-124">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="93930-125">識別子名</span><span class="sxs-lookup"><span data-stu-id="93930-125">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="93930-126">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="93930-126">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="93930-127">::演算子</span><span class="sxs-lookup"><span data-stu-id="93930-127">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
