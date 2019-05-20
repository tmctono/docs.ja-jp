---
title: '方法 : ポインター変数の値を取得する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 9a10bcc809f3ecbc9a0fa9b917940b8e030fab8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635099"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="0a906-102">方法 : ポインター変数の値を取得する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0a906-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="0a906-103">ポインターが指す位置にある変数を取得するには、ポインター間接演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a906-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="0a906-104">この式は次の形式になります。`p` はポインター型です。</span><span class="sxs-lookup"><span data-stu-id="0a906-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="0a906-105">ポインター型以外の型の式では、単項間接演算子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a906-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="0a906-106">また、[void](../../../csharp/language-reference/keywords/void.md) ポインターに適用することもできません。</span><span class="sxs-lookup"><span data-stu-id="0a906-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="0a906-107">間接演算子を [null](../../../csharp/language-reference/keywords/null.md) ポインターに適用すると、結果は実装によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0a906-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="0a906-108">例</span><span class="sxs-lookup"><span data-stu-id="0a906-108">Example</span></span>

<span data-ttu-id="0a906-109">次の例では、`char` 型の変数に、さまざまな型のポインターを使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0a906-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="0a906-110">変数に割り当てられる物理アドレスが変更できるため、`theChar` のアドレスが実行ごとに異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0a906-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="0a906-111">**theChar の値 = Z**</span><span class="sxs-lookup"><span data-stu-id="0a906-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="0a906-112">**theChar のアドレス = 12F718**</span><span class="sxs-lookup"><span data-stu-id="0a906-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="0a906-113">**pChar の値 = Z**</span><span class="sxs-lookup"><span data-stu-id="0a906-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="0a906-114">**pInt の値 = 90**</span><span class="sxs-lookup"><span data-stu-id="0a906-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="0a906-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a906-115">See also</span></span>

- [<span data-ttu-id="0a906-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0a906-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0a906-117">ポインター型</span><span class="sxs-lookup"><span data-stu-id="0a906-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0a906-118">型</span><span class="sxs-lookup"><span data-stu-id="0a906-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="0a906-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="0a906-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="0a906-120">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="0a906-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="0a906-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0a906-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
