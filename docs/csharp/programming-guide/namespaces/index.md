---
title: 名前空間 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: cf5a7f239cf7d3cd3a6e39f31d16adb830646afc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039490"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="21738-102">名前空間 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="21738-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="21738-103">C# プログラミングでは、名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="21738-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="21738-104">最初の方法では、次のように .NET Framework で名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="21738-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="21738-105">`System` は名前空間で、`Console` はその名前空間内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="21738-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="21738-106">以下の例のように、`using` キーワードを使用できるため、完全な名前は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21738-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="21738-107">詳細については、「[using ディレクティブ](../../language-reference/keywords/using-directive.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="21738-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="21738-108">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21738-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="21738-109">名前空間を宣言するには、以下の例のように、[namespace](../../language-reference/keywords/namespace.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="21738-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="21738-110">名前空間の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21738-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="21738-111">名前空間の概要</span><span class="sxs-lookup"><span data-stu-id="21738-111">Namespaces Overview</span></span>  

<span data-ttu-id="21738-112">名前空間には次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="21738-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="21738-113">大きなコード プロジェクトを整理します。</span><span class="sxs-lookup"><span data-stu-id="21738-113">They organize large code projects.</span></span>  
- <span data-ttu-id="21738-114">`.` 演算子を使用して、区切られます。</span><span class="sxs-lookup"><span data-stu-id="21738-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="21738-115">`using` ディレクティブを使用すると、クラスごとに名前空間の名前を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="21738-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="21738-116">`global` 名前空間は "ルート" 名前空間です。`global::System` は常に .NET 名前空間の <xref:System> を参照します。</span><span class="sxs-lookup"><span data-stu-id="21738-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="21738-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="21738-117">C# language specification</span></span>

<span data-ttu-id="21738-118">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関する記事の「[名前空間](~/_csharplang/spec/namespaces.md)」に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21738-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21738-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="21738-119">See also</span></span>

- [<span data-ttu-id="21738-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="21738-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="21738-121">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="21738-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="21738-122">方法: My 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="21738-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="21738-123">識別子名</span><span class="sxs-lookup"><span data-stu-id="21738-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="21738-124">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="21738-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="21738-125">::演算子</span><span class="sxs-lookup"><span data-stu-id="21738-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
