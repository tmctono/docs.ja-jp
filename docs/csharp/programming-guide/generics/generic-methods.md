---
title: ジェネリック メソッド - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 083fc6ff3dd15252fb6cf2beb27b5be0a6e489f5
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423449"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="fccc2-102">ジェネリック メソッド (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fccc2-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="fccc2-103">ジェネリック メソッドは、次のように型パラメーターで宣言されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="fccc2-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 <span data-ttu-id="fccc2-104">メソッドの呼び出し方法の 1 つを示しているのが次のコード サンプルです。型引数に `int` を利用します。</span><span class="sxs-lookup"><span data-stu-id="fccc2-104">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 <span data-ttu-id="fccc2-105">型引数は省略することもできます。コンパイラが推定します。</span><span class="sxs-lookup"><span data-stu-id="fccc2-105">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="fccc2-106">次は、前の呼び出しと同じように `Swap` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fccc2-106">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 <span data-ttu-id="fccc2-107">型推定の同じ規則が静的メソッドとインスタンス メソッドに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-107">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="fccc2-108">コンパイラは、渡されたメソッド引数に基づいて型パラメーターを推定できます。制約や戻り値だけでは型パラメーターを推定できません。</span><span class="sxs-lookup"><span data-stu-id="fccc2-108">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="fccc2-109">そのため、パラメーターのないメソッドでは型を推定できません。</span><span class="sxs-lookup"><span data-stu-id="fccc2-109">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="fccc2-110">型はコンパイル時に、コンパイラがオーバーロードされたメソッド シグネチャを解決する前に推定されます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-110">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="fccc2-111">コンパイラは、同じ名前を共有するすべてのジェネリック メソッドに型の推定ロジックを適用します。</span><span class="sxs-lookup"><span data-stu-id="fccc2-111">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="fccc2-112">オーバーロード解決手順では、型を推定できたジェネリック メソッドのみがコンパイラに含まれます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-112">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="fccc2-113">ジェネリック クラス内では、非ジェネリック メソッドは、次のように、クラスレベルの型パラメーターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-113">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 <span data-ttu-id="fccc2-114">包含クラスと同じ型パラメーターを受け取るジェネリック メソッドを定義すると、コンパイラは警告 CS0693 を生成します。これは、メソッド範囲内で、内側の `T` に与えられた引数により外側の `T` に与えられた引数が隠されるためです。</span><span class="sxs-lookup"><span data-stu-id="fccc2-114">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="fccc2-115">クラスがインスタンス化されたときに与えらたれ型パラメーター以外の型パラメーターでジェネリック クラス メソッドを呼び出すという柔軟性が必要な場合、メソッドの型パラメーターに別の識別子を指定することを検討してください。次の例の `GenericList2<T>` をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fccc2-115">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 <span data-ttu-id="fccc2-116">メソッドの型パラメーターでさらに多くの特殊操作を可能にするために、制約を使用します。</span><span class="sxs-lookup"><span data-stu-id="fccc2-116">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="fccc2-117">`SwapIfGreater<T>` という名前が付けられた `Swap<T>` のこのバージョンは、<xref:System.IComparable%601> を実装する型引数との併用でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-117">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 <span data-ttu-id="fccc2-118">ジェネリック メソッドは、いくつかの型パラメーターでオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-118">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="fccc2-119">たとえば、次のメソッドはすべて同じクラスに配置できます。</span><span class="sxs-lookup"><span data-stu-id="fccc2-119">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fccc2-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fccc2-120">C# Language Specification</span></span>  
 <span data-ttu-id="fccc2-121">詳細については、「[C# 言語の仕様](~/_csharplang/spec/classes.md#methods)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fccc2-121">For more information, see the [C# Language Specification](~/_csharplang/spec/classes.md#methods).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fccc2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fccc2-122">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="fccc2-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fccc2-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fccc2-124">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="fccc2-124">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="fccc2-125">メソッド</span><span class="sxs-lookup"><span data-stu-id="fccc2-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
