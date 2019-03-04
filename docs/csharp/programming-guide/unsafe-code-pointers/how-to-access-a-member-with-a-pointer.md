---
title: '方法 : ポインターを使用してメンバーにアクセスする - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200352"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="ffbd3-102">方法 : ポインターを使用してメンバーにアクセスする (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ffbd3-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="ffbd3-103">安全ではないコンテキストで宣言されている構造体のメンバーにアクセスするには、次の例のように、メンバー アクセス演算子を利用できます。`p` は、メンバー `x` を含む[構造体](../../../csharp/language-reference/keywords/struct.md)を指すポインターです。</span><span class="sxs-lookup"><span data-stu-id="ffbd3-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="ffbd3-104">例</span><span class="sxs-lookup"><span data-stu-id="ffbd3-104">Example</span></span>  
 <span data-ttu-id="ffbd3-105">この例では、2 つの座標 (`x` と `y`) を含む[構造体](../../../csharp/language-reference/keywords/struct.md) `CoOrds` が宣言され、インスタンス化されています。</span><span class="sxs-lookup"><span data-stu-id="ffbd3-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="ffbd3-106">メンバー アクセス演算子 `->` とインスタンス `home` を指すポインターを使用することで、`x` と `y` に値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ffbd3-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffbd3-107">式 `p->x` は式 `(*p).x` と等しく、2 つの式のいずれを利用しても同じ結果が得られることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="ffbd3-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="ffbd3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffbd3-108">See also</span></span>

- [<span data-ttu-id="ffbd3-109">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ffbd3-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ffbd3-110">ポインター式</span><span class="sxs-lookup"><span data-stu-id="ffbd3-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="ffbd3-111">ポインター型</span><span class="sxs-lookup"><span data-stu-id="ffbd3-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="ffbd3-112">型</span><span class="sxs-lookup"><span data-stu-id="ffbd3-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="ffbd3-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="ffbd3-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="ffbd3-114">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="ffbd3-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="ffbd3-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="ffbd3-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
