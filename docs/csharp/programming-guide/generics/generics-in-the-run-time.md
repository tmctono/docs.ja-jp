---
title: ランタイムのジェネリック - C# プログラミング ガイド
description: ランタイムのジェネリック型について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
ms.openlocfilehash: 8e072e7aa53177929dda0be931beb85863b6a12e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299228"
---
# <a name="generics-in-the-run-time-c-programming-guide"></a><span data-ttu-id="b2d10-104">ランタイムのジェネリック (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b2d10-104">Generics in the Run Time (C# Programming Guide)</span></span>
<span data-ttu-id="b2d10-105">ジェネリック型またはメソッドが Microsoft 中間言語 (MSIL) にコンパイルされるとき、型パラメーターありとして識別するメタデータが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-105">When a generic type or method is compiled into Microsoft intermediate language (MSIL), it contains metadata that identifies it as having type parameters.</span></span> <span data-ttu-id="b2d10-106">ジェネリック型の MSIL の使われ方は、指定した型パラメーターの種類 (値型または参照型) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b2d10-106">How the MSIL for a generic type is used differs based on whether the supplied type parameter is a value type or reference type.</span></span>  
  
 <span data-ttu-id="b2d10-107">ジェネリック型が値型をパラメーターとして最初に構築されるとき、ランタイムにより、特殊なジェネリック型が作成されます。このとき、MSIL の適切な場所で指定のパラメーターが代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-107">When a generic type is first constructed with a value type as a parameter, the runtime creates a specialized generic type with the supplied parameter or parameters substituted in the appropriate locations in the MSIL.</span></span> <span data-ttu-id="b2d10-108">特殊なジェネリック型は、パラメーターとして使用される一意の値型ごとに 1 回作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-108">Specialized generic types are created one time for each unique value type that is used as a parameter.</span></span>  
  
 <span data-ttu-id="b2d10-109">たとえば、プログラム コードで、整数で構成されるスタックを宣言したとします。</span><span class="sxs-lookup"><span data-stu-id="b2d10-109">For example, suppose your program code declared a stack that is constructed of integers:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#42)]  
  
 <span data-ttu-id="b2d10-110">この時点で、整数がそのパラメーターに合わせて置き換えられた <xref:System.Collections.Generic.Stack%601> クラスの特殊なバージョンがランタイムにより生成されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-110">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that has the integer substituted appropriately for its parameter.</span></span> <span data-ttu-id="b2d10-111">プログラム コードで整数のスタックを使用するたびに、ランタイムは、生成された特殊な <xref:System.Collections.Generic.Stack%601> クラスを再利用します。</span><span class="sxs-lookup"><span data-stu-id="b2d10-111">Now, whenever your program code uses a stack of integers, the runtime reuses the generated specialized <xref:System.Collections.Generic.Stack%601> class.</span></span> <span data-ttu-id="b2d10-112">次の例では、整数のスタックの 2 つのインスタンスが作成され、`Stack<int>` コードの単一インスタンスを共有します。</span><span class="sxs-lookup"><span data-stu-id="b2d10-112">In the following example, two instances of a stack of integers are created, and they share a single instance of the `Stack<int>` code:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#43)]  
  
 <span data-ttu-id="b2d10-113">ただし、`long` のような異なる値型を持つか、パラメーターとしてユーザー定義構造を持つ別の <xref:System.Collections.Generic.Stack%601> クラスがコード内の別のポイントで作成されると想定します。</span><span class="sxs-lookup"><span data-stu-id="b2d10-113">However, suppose that another <xref:System.Collections.Generic.Stack%601> class with a different value type such as a `long` or a user-defined structure as its parameter is created at another point in your code.</span></span> <span data-ttu-id="b2d10-114">結果として、ランタイムによりジェネリック型の別バージョンが生成され、MSIL 内の適切な場所で `long` を代わりに使います。</span><span class="sxs-lookup"><span data-stu-id="b2d10-114">As a result, the runtime generates another version of the generic type and substitutes a `long` in the appropriate locations in MSIL.</span></span> <span data-ttu-id="b2d10-115">特殊なジェネリック クラスにはそれぞれ、ネイティブで値型が含まれているため、変換は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b2d10-115">Conversions are no longer necessary because each specialized generic class natively contains the value type.</span></span>  
  
 <span data-ttu-id="b2d10-116">参照型の場合、ジェネリックの動作は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="b2d10-116">Generics work somewhat differently for reference types.</span></span> <span data-ttu-id="b2d10-117">何らかの参照型でジェネリック型を初めて構築するとき、ランタイムは、MSIL のパラメーターの代わりに使用されているオブジェクト参照を利用して特殊なジェネリック型を作成します。</span><span class="sxs-lookup"><span data-stu-id="b2d10-117">The first time a generic type is constructed with any reference type, the runtime creates a specialized generic type with object references substituted for the parameters in the MSIL.</span></span> <span data-ttu-id="b2d10-118">その後、構築された型が参照型をそのパラメーターとしてインスタンス化されるたびに、型に関係なく、ランタイムは、以前に利用した特殊なバージョンのジェネリック型を再利用します。</span><span class="sxs-lookup"><span data-stu-id="b2d10-118">Then, every time that a constructed type is instantiated with a reference type as its parameter, regardless of what type it is, the runtime reuses the previously created specialized version of the generic type.</span></span> <span data-ttu-id="b2d10-119">すべての参照のサイズが同じであるため、これが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b2d10-119">This is possible because all references are the same size.</span></span>  
  
 <span data-ttu-id="b2d10-120">たとえば、`Customer` クラスと `Order` クラスという 2 つの参照型があるとき、`Customer` 型のスタックを作成したとします。</span><span class="sxs-lookup"><span data-stu-id="b2d10-120">For example, suppose you had two reference types, a `Customer` class and an `Order` class, and also suppose that you created a stack of `Customer` types:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#47)]  
  
 [!code-csharp[csProgGuideGenerics#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#44)]  
  
 <span data-ttu-id="b2d10-121">この時点で、オブジェクト参照を格納する <xref:System.Collections.Generic.Stack%601> クラスの特殊なバージョンがランタイムにより生成されます。データを保存しなくても、後にオブジェクト参照にデータが入力されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-121">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that stores object references that will be filled in later instead of storing data.</span></span> <span data-ttu-id="b2d10-122">次のコード行により、`Order` という名前のもう 1 つの参照型のスタックが作成されるとします。</span><span class="sxs-lookup"><span data-stu-id="b2d10-122">Suppose the next line of code creates a stack of another reference type, which is named `Order`:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#45)]  
  
 <span data-ttu-id="b2d10-123">値型とは異なり、<xref:System.Collections.Generic.Stack%601> クラスのもう 1 つの特殊なバージョンは `Order` 型に対して作成されません。</span><span class="sxs-lookup"><span data-stu-id="b2d10-123">Unlike with value types, another specialized version of the <xref:System.Collections.Generic.Stack%601> class is not created for the `Order` type.</span></span> <span data-ttu-id="b2d10-124">代わりに、<xref:System.Collections.Generic.Stack%601> クラスの特殊なバージョンのインスタンスが作成され、それを参照するように `orders` 変数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-124">Instead, an instance of the specialized version of the <xref:System.Collections.Generic.Stack%601> class is created and the `orders` variable is set to reference it.</span></span> <span data-ttu-id="b2d10-125">その後、`Customer` 型のスタックを作成するコード行が見つかったとします。</span><span class="sxs-lookup"><span data-stu-id="b2d10-125">Suppose that you then encountered a line of code to create a stack of a `Customer` type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#46)]  
  
 <span data-ttu-id="b2d10-126">`Order` 型を利用して作成された <xref:System.Collections.Generic.Stack%601> クラスの前の使用と同様に、特殊な <xref:System.Collections.Generic.Stack%601> クラスのもう 1 つのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-126">As with the previous use of the <xref:System.Collections.Generic.Stack%601> class created by using the `Order` type, another instance of the specialized <xref:System.Collections.Generic.Stack%601> class is created.</span></span> <span data-ttu-id="b2d10-127">そこに含まれるポインターは、`Customer` 型のサイズのメモリ領域を参照するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="b2d10-127">The pointers that are contained therein are set to reference an area of memory the size of a `Customer` type.</span></span> <span data-ttu-id="b2d10-128">参照型はプログラムによって大きく異なることがあるため、ジェネリックの C# 実装では、コードの量が大幅に、参照型のジェネリック クラスのコンパイラにより作成された特殊なクラスの数まで減ります。</span><span class="sxs-lookup"><span data-stu-id="b2d10-128">Because the number of reference types can vary wildly from program to program, the C# implementation of generics greatly reduces the amount of code by reducing to one the number of specialized classes created by the compiler for generic classes of reference types.</span></span>  
  
 <span data-ttu-id="b2d10-129">また、ジェネリック C# クラスが値型または参照型パラメーターの利用によりインスタンス化されるとき、ランタイム時にリフレクションがクエリを実行し、その型パラメーターを確かめることができます。</span><span class="sxs-lookup"><span data-stu-id="b2d10-129">Moreover, when a generic C# class is instantiated by using a value type or reference type parameter, reflection can query it at runtime and both its actual type and its type parameter can be ascertained.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d10-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2d10-130">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="b2d10-131">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b2d10-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2d10-132">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="b2d10-132">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="b2d10-133">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="b2d10-133">Generics</span></span>](../../../standard/generics/index.md)
