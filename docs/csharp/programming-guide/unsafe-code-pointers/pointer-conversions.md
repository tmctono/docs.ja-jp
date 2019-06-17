---
title: ポインター変換 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 3cef2f2d2af2d285504daea14aa57c55b9e9a21b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833459"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="05937-102">ポインター変換 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="05937-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="05937-103">定義済みの暗黙的なポインター変換を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="05937-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="05937-104">暗黙的な変換は、メソッドの呼び出しや代入ステートメントなど、多くの状況で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="05937-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="05937-105">暗黙的なポインター変換</span><span class="sxs-lookup"><span data-stu-id="05937-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="05937-106">ソース</span><span class="sxs-lookup"><span data-stu-id="05937-106">From</span></span>|<span data-ttu-id="05937-107">ターゲット</span><span class="sxs-lookup"><span data-stu-id="05937-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="05937-108">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-108">Any pointer type</span></span>|<span data-ttu-id="05937-109">void\*</span><span class="sxs-lookup"><span data-stu-id="05937-109">void\*</span></span>|  
|<span data-ttu-id="05937-110">null</span><span class="sxs-lookup"><span data-stu-id="05937-110">null</span></span>|<span data-ttu-id="05937-111">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="05937-112">明示的なポインター変換は、暗黙的な変換がない場合に、キャスト式を使用して、変換を実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="05937-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="05937-113">次の表はこの変換についてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="05937-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="05937-114">明示的なポインター変換</span><span class="sxs-lookup"><span data-stu-id="05937-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="05937-115">ソース</span><span class="sxs-lookup"><span data-stu-id="05937-115">From</span></span>|<span data-ttu-id="05937-116">ターゲット</span><span class="sxs-lookup"><span data-stu-id="05937-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="05937-117">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-117">Any pointer type</span></span>|<span data-ttu-id="05937-118">その他のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-118">Any other pointer type</span></span>|  
|<span data-ttu-id="05937-119">sbyte、byte、short、ushort、int、uint、long または ulong</span><span class="sxs-lookup"><span data-stu-id="05937-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="05937-120">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-120">Any pointer type</span></span>|  
|<span data-ttu-id="05937-121">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-121">Any pointer type</span></span>|<span data-ttu-id="05937-122">sbyte、byte、short、ushort、int、uint、long または ulong</span><span class="sxs-lookup"><span data-stu-id="05937-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05937-123">例</span><span class="sxs-lookup"><span data-stu-id="05937-123">Example</span></span>  
 <span data-ttu-id="05937-124">次の例では、`int` へのポインターは `byte` へのポインターに変換されます。</span><span class="sxs-lookup"><span data-stu-id="05937-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="05937-125">ポインターは、変数の最下位バイト アドレスを指すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="05937-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="05937-126">`int` のサイズ (4 バイト) まで結果を連続してインクリメントする場合、変数の残りのバイトを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="05937-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="05937-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="05937-127">See also</span></span>

- [<span data-ttu-id="05937-128">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="05937-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="05937-129">ポインター型</span><span class="sxs-lookup"><span data-stu-id="05937-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="05937-130">型</span><span class="sxs-lookup"><span data-stu-id="05937-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="05937-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="05937-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="05937-132">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="05937-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="05937-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="05937-133">stackalloc</span></span>](../../../csharp/language-reference/operators/stackalloc.md)
