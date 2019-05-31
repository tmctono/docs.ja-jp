---
title: ジェネリック - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423392"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="d5559-102">ジェネリック (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d5559-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="d5559-103">ジェネリックは、バージョン 2.0 の C# 言語と共通言語ランタイム (CLR) に追加されたものです。</span><span class="sxs-lookup"><span data-stu-id="d5559-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="d5559-104">ジェネリックは、.NET Framework に型パラメーターという概念を導入します。型パラメーターを使用すると、クラスやメソッドがクライアント コードで宣言され、インスタンス化されるまで、1 つ以上の型の指定を遅延させるクラスとメソッドを設計できます。</span><span class="sxs-lookup"><span data-stu-id="d5559-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="d5559-105">たとえば、ジェネリック型パラメーター T を使用すると、次に示すようにランタイムのキャストやボックス化操作のコストやリスクを負わずに他のクライアント コードで使用できる単一のクラスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="d5559-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="d5559-106">ジェネリックのクラスとメソッドは、非ジェネリックでは不可能な方法で、再利用性、タイプ セーフ、効率性を同時に実現しています。</span><span class="sxs-lookup"><span data-stu-id="d5559-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="d5559-107">ジェネリックは、コレクションとそれを操作するメソッドとともに使用されるのが通常です。</span><span class="sxs-lookup"><span data-stu-id="d5559-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="d5559-108">.NET Framework クラス ライブラリのバージョン 2.0 には、いくつかの新しいジェネリック ベースのコレクション クラスを含む新しい名前空間、<xref:System.Collections.Generic> が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d5559-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="d5559-109">.NET Framework 2.0 以降を対象とするすべてのアプリケーションでは、<xref:System.Collections.ArrayList> などの以前の非ジェネリック コレクション クラスの代わりに、新しいジェネリック コレクション クラスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5559-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="d5559-110">詳細については、「[.NET のジェネリック](../../../standard/generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5559-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="d5559-111">もちろん、カスタムのジェネリック型やジェネリック メソッドを作成して、タイプ セーフで効率的な独自の汎用ソリューションや設計パターンを実現することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5559-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="d5559-112">次のコード例では、デモンストレーション用の簡単なジェネリックのリンク リスト クラスを示します。</span><span class="sxs-lookup"><span data-stu-id="d5559-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="d5559-113">(通常は、独自のクラスを作成するのではなく、.NET Framework クラス ライブラリに用意されている <xref:System.Collections.Generic.List%601> クラスを使用してください。)この例では、通常、具体的な型を使用して、リストに格納する項目の型を示す場面で、型パラメーター `T` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d5559-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="d5559-114">このパラメーターは、次のように使用されています。</span><span class="sxs-lookup"><span data-stu-id="d5559-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="d5559-115">`AddHead` メソッドのメソッド パラメーターの型として使用。</span><span class="sxs-lookup"><span data-stu-id="d5559-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="d5559-116">入れ子になった `Node` クラスの `Data` プロパティの戻り値の型として使用。</span><span class="sxs-lookup"><span data-stu-id="d5559-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="d5559-117">入れ子になったクラスのプライベート メンバー `data` の型として使用。</span><span class="sxs-lookup"><span data-stu-id="d5559-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="d5559-118">T は、入れ子になった `Node` クラスで使用できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5559-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="d5559-119">`GenericList<T>` が `GenericList<int>` のような具象型でインスタンス化されると、`T` の部分はそれぞれ `int` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d5559-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="d5559-120">次のコード例では、クライアント コードでジェネリックの `GenericList<T>` クラスを使用して、整数のリストを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d5559-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="d5559-121">このコードの型引数を変更するだけで、文字列やその他の任意のカスタム型のリストを作成するように簡単に修正できます。</span><span class="sxs-lookup"><span data-stu-id="d5559-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="d5559-122">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="d5559-122">Generics Overview</span></span>  
  
- <span data-ttu-id="d5559-123">ジェネリック型は、コードの再利用、タイプ セーフ、およびパフォーマンスを最大化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d5559-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="d5559-124">ジェネリックの最も一般的な用途は、コレクション クラスの作成です。</span><span class="sxs-lookup"><span data-stu-id="d5559-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="d5559-125">.NET Framework クラス ライブラリには、複数の新しいジェネリック コレクション クラスが <xref:System.Collections.Generic> 名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5559-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="d5559-126"><xref:System.Collections> 名前空間の <xref:System.Collections.ArrayList> などのクラスの代わりとして、できる限りこれらを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d5559-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="d5559-127">独自のジェネリック インターフェイス、クラス、メソッド、イベントおよびデリゲートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d5559-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="d5559-128">ジェネリック クラスは、特定のデータ型のメソッドへのアクセスを有効にするように制限できます。</span><span class="sxs-lookup"><span data-stu-id="d5559-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="d5559-129">ジェネリック データ型で使用される型に関する情報は、実行時にリフレクションを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="d5559-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5559-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5559-130">Related Sections</span></span>  
 <span data-ttu-id="d5559-131">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d5559-131">For more information:</span></span>  
  
- [<span data-ttu-id="d5559-132">ジェネリック型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5559-132">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [<span data-ttu-id="d5559-133">型パラメーターの制約</span><span class="sxs-lookup"><span data-stu-id="d5559-133">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="d5559-134">ジェネリック クラス</span><span class="sxs-lookup"><span data-stu-id="d5559-134">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [<span data-ttu-id="d5559-135">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5559-135">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [<span data-ttu-id="d5559-136">ジェネリック メソッド</span><span class="sxs-lookup"><span data-stu-id="d5559-136">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [<span data-ttu-id="d5559-137">汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="d5559-137">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [<span data-ttu-id="d5559-138">C++ テンプレートと C# ジェネリックの違い</span><span class="sxs-lookup"><span data-stu-id="d5559-138">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="d5559-139">ジェネリックとリフレクション</span><span class="sxs-lookup"><span data-stu-id="d5559-139">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [<span data-ttu-id="d5559-140">ランタイムのジェネリック</span><span class="sxs-lookup"><span data-stu-id="d5559-140">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5559-141">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d5559-141">C# Language Specification</span></span>  
 <span data-ttu-id="d5559-142">詳細については、「[C# 言語の仕様](~/_csharplang/spec/types.md#constructed-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5559-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5559-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5559-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="d5559-144">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d5559-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d5559-145">型</span><span class="sxs-lookup"><span data-stu-id="d5559-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="d5559-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="d5559-146">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="d5559-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="d5559-147">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="d5559-148">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="d5559-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
