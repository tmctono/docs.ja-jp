---
title: ポインターに対する算術演算 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: b08f9dbf8137e483bd38a4f396732191598532cf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635234"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="13332-102">ポインターに対する算術演算 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="13332-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="13332-103">このトピックでは、算術演算子 `+` と `-` を使用したポインター操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="13332-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13332-104">void ポインターには、算術演算を実行できません。</span><span class="sxs-lookup"><span data-stu-id="13332-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="13332-105">ポインターに対する数値の加算と減算</span><span class="sxs-lookup"><span data-stu-id="13332-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="13332-106">型が [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md) のいずれかである値 `n` をポインターに加算できます。</span><span class="sxs-lookup"><span data-stu-id="13332-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="13332-107">`p` が型 `pointer-type*` のポインターである場合、結果の `p+n` は `p` のアドレスに `n * sizeof(pointer-type)` を加算した結果のポインターです。</span><span class="sxs-lookup"><span data-stu-id="13332-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="13332-108">同様に、`p-n` は `p` のアドレスから `n * sizeof(pointer-type)` を減算した結果を表すポインターです。</span><span class="sxs-lookup"><span data-stu-id="13332-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="13332-109">ポインターの減算</span><span class="sxs-lookup"><span data-stu-id="13332-109">Subtracting pointers</span></span>  
 <span data-ttu-id="13332-110">同じ型のポインターを減算することもできます。</span><span class="sxs-lookup"><span data-stu-id="13332-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="13332-111">結果は常に `long` 型になります。</span><span class="sxs-lookup"><span data-stu-id="13332-111">The result is always of the type `long`.</span></span> <span data-ttu-id="13332-112">たとえば場合、`p1` と `p2` が `pointer-type*` 型のポインターである場合、式 `p1-p2` の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13332-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="13332-113">算術演算がポインターのドメインをオーバーフローしても、例外は生成されません。生じる結果は実装によって異なります。</span><span class="sxs-lookup"><span data-stu-id="13332-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13332-114">例</span><span class="sxs-lookup"><span data-stu-id="13332-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="13332-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="13332-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="13332-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="13332-116">See also</span></span>

- [<span data-ttu-id="13332-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="13332-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="13332-118">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="13332-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="13332-119">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="13332-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="13332-120">ポインターの操作</span><span class="sxs-lookup"><span data-stu-id="13332-120">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="13332-121">ポインター型</span><span class="sxs-lookup"><span data-stu-id="13332-121">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="13332-122">型</span><span class="sxs-lookup"><span data-stu-id="13332-122">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="13332-123">unsafe</span><span class="sxs-lookup"><span data-stu-id="13332-123">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="13332-124">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="13332-124">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="13332-125">stackalloc</span><span class="sxs-lookup"><span data-stu-id="13332-125">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
