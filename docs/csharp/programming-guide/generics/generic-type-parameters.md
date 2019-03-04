---
title: ジェネリック型の型パラメーター - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: f6acbfee5c6b5ec426076d7bf766a3c6894b736f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972184"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="f9189-102">ジェネリック型の型パラメーター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f9189-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="f9189-103">ジェネリック型またはメソッド定義で、型パラメーターは、ジェネリック型の変数をインスタンス化するときにクライアントが指定する特定の型のためのプレースホルダーになります。</span><span class="sxs-lookup"><span data-stu-id="f9189-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="f9189-104">「[ジェネリックの概要](../../../csharp/programming-guide/generics/introduction-to-generics.md)」に記載されている `GenericList<T>` などのジェネリック クラスは、実際は型でないため、そのままでは使用できません。これは型の設計図のようなものです。</span><span class="sxs-lookup"><span data-stu-id="f9189-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="f9189-105">`GenericList<T>` を使用するには、クライアント コードで構築された型を宣言し、インスタンス化する必要があります。山かっこ内に型引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9189-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="f9189-106">この特定のクラスの型引数は、コンパイラで認識されるあらゆる型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f9189-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="f9189-107">構築された型インスタンスは、次のようにさまざまな型引数を利用し、いくつでも作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9189-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
 <span data-ttu-id="f9189-108">`GenericList<T>` の各インスタンスでは、クラス内のすべての `T` は実行時に型引数に置換されます。</span><span class="sxs-lookup"><span data-stu-id="f9189-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="f9189-109">この置換を使用し、単一クラス定義を使用してタイプ セーフで効率的なオブジェクトを 3 つ作成しました。</span><span class="sxs-lookup"><span data-stu-id="f9189-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="f9189-110">この置換が CLR で実行されるしくみについては、「[ランタイムのジェネリック](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9189-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="f9189-111">型パラメーターの名前付けガイドライン</span><span class="sxs-lookup"><span data-stu-id="f9189-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="f9189-112">1 文字の名前でも完全に説明され、説明的な名前を付けることに意味がない場合を除き、ジェネリック型パラメーターには**説明的な名前を付けてください**。</span><span class="sxs-lookup"><span data-stu-id="f9189-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
-   <span data-ttu-id="f9189-113">1 文字の型パラメーターを持つ型の型パラメーター名として T を利用することを**検討してください**。</span><span class="sxs-lookup"><span data-stu-id="f9189-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
-   <span data-ttu-id="f9189-114">型パラメーターの説明的な名前には "T" という**接頭辞を付けてください**。</span><span class="sxs-lookup"><span data-stu-id="f9189-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
-   <span data-ttu-id="f9189-115">型パラメーターに与えられた制約をパラメーターの名前で示唆することを**検討してください**。</span><span class="sxs-lookup"><span data-stu-id="f9189-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="f9189-116">たとえば、`ISession` に制約されているパラメーターの名前を `TSession` にします。</span><span class="sxs-lookup"><span data-stu-id="f9189-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9189-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9189-117">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f9189-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f9189-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f9189-119">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="f9189-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="f9189-120">C++ テンプレートと C# ジェネリックの違い</span><span class="sxs-lookup"><span data-stu-id="f9189-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
