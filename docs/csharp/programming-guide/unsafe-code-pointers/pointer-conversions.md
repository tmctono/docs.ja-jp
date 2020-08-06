---
title: ポインター変換 - C# プログラミング ガイド
description: ポインター変換について説明します。 暗黙的および明示的なポインター変換の表とコード例を確認し、使用可能なその他のリソースを参照してください。
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: c39be5cb52964abbea5bc5636c6fa74d8411a331
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382088"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="de46d-104">ポインター変換 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="de46d-104">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="de46d-105">定義済みの暗黙的なポインター変換を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="de46d-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="de46d-106">暗黙的な変換は、メソッドの呼び出しや代入ステートメントなど、多くの状況で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="de46d-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="de46d-107">暗黙的なポインター変換</span><span class="sxs-lookup"><span data-stu-id="de46d-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="de46d-108">From</span><span class="sxs-lookup"><span data-stu-id="de46d-108">From</span></span>|<span data-ttu-id="de46d-109">終了</span><span class="sxs-lookup"><span data-stu-id="de46d-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="de46d-110">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-110">Any pointer type</span></span>|<span data-ttu-id="de46d-111">void\*</span><span class="sxs-lookup"><span data-stu-id="de46d-111">void\*</span></span>|  
|<span data-ttu-id="de46d-112">null</span><span class="sxs-lookup"><span data-stu-id="de46d-112">null</span></span>|<span data-ttu-id="de46d-113">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="de46d-114">明示的なポインター変換は、暗黙的な変換がない場合に、キャスト式を使用して、変換を実行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="de46d-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="de46d-115">次の表はこの変換についてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="de46d-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="de46d-116">明示的なポインター変換</span><span class="sxs-lookup"><span data-stu-id="de46d-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="de46d-117">From</span><span class="sxs-lookup"><span data-stu-id="de46d-117">From</span></span>|<span data-ttu-id="de46d-118">終了</span><span class="sxs-lookup"><span data-stu-id="de46d-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="de46d-119">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-119">Any pointer type</span></span>|<span data-ttu-id="de46d-120">その他のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-120">Any other pointer type</span></span>|  
|<span data-ttu-id="de46d-121">sbyte、byte、short、ushort、int、uint、long または ulong</span><span class="sxs-lookup"><span data-stu-id="de46d-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="de46d-122">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-122">Any pointer type</span></span>|  
|<span data-ttu-id="de46d-123">任意のポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-123">Any pointer type</span></span>|<span data-ttu-id="de46d-124">sbyte、byte、short、ushort、int、uint、long または ulong</span><span class="sxs-lookup"><span data-stu-id="de46d-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de46d-125">例</span><span class="sxs-lookup"><span data-stu-id="de46d-125">Example</span></span>  
 <span data-ttu-id="de46d-126">次の例では、`int` へのポインターは `byte` へのポインターに変換されます。</span><span class="sxs-lookup"><span data-stu-id="de46d-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="de46d-127">ポインターは、変数の最下位バイト アドレスを指すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="de46d-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="de46d-128">`int` のサイズ (4 バイト) まで結果を連続してインクリメントする場合、変数の残りのバイトを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="de46d-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="de46d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="de46d-129">See also</span></span>

- [<span data-ttu-id="de46d-130">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="de46d-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="de46d-131">ポインター型</span><span class="sxs-lookup"><span data-stu-id="de46d-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="de46d-132">参照型</span><span class="sxs-lookup"><span data-stu-id="de46d-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="de46d-133">値型</span><span class="sxs-lookup"><span data-stu-id="de46d-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="de46d-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="de46d-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="de46d-135">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="de46d-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="de46d-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="de46d-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
