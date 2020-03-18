---
title: ジェネリック型の型パラメーター - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8412980d35989c445d2e0a44c0b9f35e6087bb8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712183"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="68d0c-102">ジェネリック型の型パラメーター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="68d0c-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="68d0c-103">ジェネリック型またはメソッド定義で、型パラメーターは、ジェネリック型のインスタンスを作成するときにクライアントが指定する特定の型のためのプレースホルダーになります。</span><span class="sxs-lookup"><span data-stu-id="68d0c-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="68d0c-104">「`GenericList<T>`ジェネリックの概要[」に記載されている ](./index.md) などのジェネリック クラスは、実際は型でないため、そのままでは使用できません。これは型の設計図のようなものです。</span><span class="sxs-lookup"><span data-stu-id="68d0c-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="68d0c-105">`GenericList<T>` を使用するには、クライアント コードで構築された型を宣言し、インスタンス化する必要があります。山かっこ内に型引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="68d0c-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="68d0c-106">この特定のクラスの型引数は、コンパイラで認識されるあらゆる型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="68d0c-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="68d0c-107">構築された型インスタンスは、次のようにさまざまな型引数を利用し、いくつでも作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d0c-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="68d0c-108">`GenericList<T>` の各インスタンスでは、クラス内のすべての `T` は実行時に型引数に置換されます。</span><span class="sxs-lookup"><span data-stu-id="68d0c-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="68d0c-109">この置換を使用し、単一クラス定義を使用してタイプ セーフで効率的なオブジェクトを 3 つ作成しました。</span><span class="sxs-lookup"><span data-stu-id="68d0c-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="68d0c-110">この置換が CLR で実行されるしくみについては、「[ランタイムのジェネリック](./generics-in-the-run-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68d0c-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="68d0c-111">型パラメーターの名前付けガイドライン</span><span class="sxs-lookup"><span data-stu-id="68d0c-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="68d0c-112">1 文字の名前でも完全に説明され、説明的な名前を付けることに意味がない場合を除き、ジェネリック型パラメーターには**説明的な名前を付けてください**。</span><span class="sxs-lookup"><span data-stu-id="68d0c-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="68d0c-113">1 文字の型パラメーターを持つ型の型パラメーター名として T を利用することを**検討してください**。</span><span class="sxs-lookup"><span data-stu-id="68d0c-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="68d0c-114">型パラメーターの説明的な名前には "T" という**接頭辞を付けてください**。</span><span class="sxs-lookup"><span data-stu-id="68d0c-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="68d0c-115">型パラメーターに与えられた制約をパラメーターの名前で示唆することを**検討してください**。</span><span class="sxs-lookup"><span data-stu-id="68d0c-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="68d0c-116">たとえば、`ISession` に制約されているパラメーターの名前を `TSession` にします。</span><span class="sxs-lookup"><span data-stu-id="68d0c-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="68d0c-117">コード分析規則 [CA1715](/visualstudio/code-quality/ca1715) を使用して、型パラメーターの名前が適切に付けられていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="68d0c-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68d0c-118">参照</span><span class="sxs-lookup"><span data-stu-id="68d0c-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="68d0c-119">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="68d0c-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="68d0c-120">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="68d0c-120">Generics</span></span>](./index.md)
- [<span data-ttu-id="68d0c-121">C++ テンプレートと C# ジェネリックの違い</span><span class="sxs-lookup"><span data-stu-id="68d0c-121">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
