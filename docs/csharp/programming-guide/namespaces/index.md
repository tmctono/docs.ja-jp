---
title: 名前空間 - C# プログラミング ガイド
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: e3e9dc22186e5e319c63e34bd85e5e317effde88
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712014"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="7c4ac-102">名前空間 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="7c4ac-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="7c4ac-103">C# プログラミングでは、名前空間が 2 つの方法でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="7c4ac-104">最初の方法では、次のように .NET Framework で名前空間を使用して、その多くのクラスを整理します。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="7c4ac-105">`System` は名前空間で、`Console` はその名前空間内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="7c4ac-106">以下の例のように、`using` キーワードを使用できるため、完全な名前は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="7c4ac-107">詳細については、「[using ディレクティブ](../../language-reference/keywords/using-directive.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="7c4ac-108">2 つ目の方法では、独自の名前空間を宣言します。これは、より大きなプログラミング プロジェクトでクラス名とメソッド名のスコープを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="7c4ac-109">名前空間を宣言するには、以下の例のように、[namespace](../../language-reference/keywords/namespace.md) キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="7c4ac-110">名前空間の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="7c4ac-111">名前空間の概要</span><span class="sxs-lookup"><span data-stu-id="7c4ac-111">Namespaces Overview</span></span>  

<span data-ttu-id="7c4ac-112">名前空間には次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="7c4ac-113">大きなコード プロジェクトを整理します。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-113">They organize large code projects.</span></span>  
- <span data-ttu-id="7c4ac-114">`.` 演算子を使用して、区切られます。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="7c4ac-115">`using` ディレクティブを使用すると、クラスごとに名前空間の名前を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="7c4ac-116">`global` 名前空間は "ルート" 名前空間です。`global::System` は常に .NET 名前空間の <xref:System> を参照します。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="7c4ac-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7c4ac-117">C# language specification</span></span>

<span data-ttu-id="7c4ac-118">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関する記事の「[名前空間](~/_csharplang/spec/namespaces.md)」に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c4ac-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7c4ac-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c4ac-119">See also</span></span>

- [<span data-ttu-id="7c4ac-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7c4ac-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7c4ac-121">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="7c4ac-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="7c4ac-122">My 名前空間を使用する方法</span><span class="sxs-lookup"><span data-stu-id="7c4ac-122">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="7c4ac-123">識別子名</span><span class="sxs-lookup"><span data-stu-id="7c4ac-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="7c4ac-124">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="7c4ac-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="7c4ac-125">::演算子</span><span class="sxs-lookup"><span data-stu-id="7c4ac-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
