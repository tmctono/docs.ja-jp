---
title: ジェネリック - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 186c5bc91204770e636eed5c008db23b798b6880
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202159"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="5e6f9-102">ジェネリック (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5e6f9-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="5e6f9-103">ジェネリックは、バージョン 2.0 の C# 言語と共通言語ランタイム (CLR) に追加されたものです。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="5e6f9-104">ジェネリックは、.NET Framework に型パラメーターという概念を導入します。型パラメーターを使用すると、クラスやメソッドがクライアント コードで宣言され、インスタンス化されるまで、1 つ以上の型の指定を遅延させるクラスとメソッドを設計できます。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="5e6f9-105">たとえば、ジェネリック型パラメーター T を使用すると、次に示すようにランタイムのキャストやボックス化操作のコストやリスクを負わずに他のクライアント コードで使用できる単一のクラスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  
  
## <a name="generics-overview"></a><span data-ttu-id="5e6f9-106">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="5e6f9-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="5e6f9-107">ジェネリック型は、コードの再利用、タイプ セーフ、およびパフォーマンスを最大化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="5e6f9-108">ジェネリックの最も一般的な用途は、コレクション クラスの作成です。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="5e6f9-109">.NET Framework クラス ライブラリには、複数の新しいジェネリック コレクション クラスが <xref:System.Collections.Generic> 名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="5e6f9-110"><xref:System.Collections> 名前空間の <xref:System.Collections.ArrayList> などのクラスの代わりとして、できる限りこれらを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="5e6f9-111">独自のジェネリック インターフェイス、クラス、メソッド、イベントおよびデリゲートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="5e6f9-112">ジェネリック クラスは、特定のデータ型のメソッドへのアクセスを有効にするように制限できます。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="5e6f9-113">ジェネリック データ型で使用される型に関する情報は、実行時にリフレクションを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5e6f9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e6f9-114">Related Sections</span></span>  
 <span data-ttu-id="5e6f9-115">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5e6f9-115">For more information:</span></span>  
  
-   [<span data-ttu-id="5e6f9-116">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="5e6f9-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="5e6f9-117">ジェネリックの利点</span><span class="sxs-lookup"><span data-stu-id="5e6f9-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="5e6f9-118">ジェネリック型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e6f9-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="5e6f9-119">型パラメーターの制約</span><span class="sxs-lookup"><span data-stu-id="5e6f9-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="5e6f9-120">ジェネリック クラス</span><span class="sxs-lookup"><span data-stu-id="5e6f9-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="5e6f9-121">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e6f9-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="5e6f9-122">ジェネリック メソッド</span><span class="sxs-lookup"><span data-stu-id="5e6f9-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="5e6f9-123">汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="5e6f9-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="5e6f9-124">C++ テンプレートと C# ジェネリックの違い</span><span class="sxs-lookup"><span data-stu-id="5e6f9-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="5e6f9-125">ジェネリックとリフレクション</span><span class="sxs-lookup"><span data-stu-id="5e6f9-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="5e6f9-126">ランタイムのジェネリック</span><span class="sxs-lookup"><span data-stu-id="5e6f9-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5e6f9-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5e6f9-127">C# Language Specification</span></span>  
 <span data-ttu-id="5e6f9-128">詳細については、「[C# 言語の仕様](~/_csharplang/spec/types.md#constructed-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e6f9-128">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6f9-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e6f9-129">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="5e6f9-130">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5e6f9-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5e6f9-131">型</span><span class="sxs-lookup"><span data-stu-id="5e6f9-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="5e6f9-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="5e6f9-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="5e6f9-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="5e6f9-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="5e6f9-134">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="5e6f9-134">Generics in .NET</span></span>](../../../standard/generics/index.md)
