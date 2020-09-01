---
description: break ステートメント - C# リファレンス
title: break ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134745"
---
# <a name="break-c-reference"></a><span data-ttu-id="fec32-103">break (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fec32-103">break (C# Reference)</span></span>

<span data-ttu-id="fec32-104">`break` ステートメントは、これを囲むループまたは [switch](./switch.md) ステートメントのうち、最も内側のものを終了させます。</span><span class="sxs-lookup"><span data-stu-id="fec32-104">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="fec32-105">終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。</span><span class="sxs-lookup"><span data-stu-id="fec32-105">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="fec32-106">例</span><span class="sxs-lookup"><span data-stu-id="fec32-106">Example</span></span>

<span data-ttu-id="fec32-107">次の例では、条件付きステートメントに 1 から 100 までをカウントするカウンターがあります。ただし、`break` ステートメントによって、ループは 4 回で終了します。</span><span class="sxs-lookup"><span data-stu-id="fec32-107">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="fec32-108">例</span><span class="sxs-lookup"><span data-stu-id="fec32-108">Example</span></span>

<span data-ttu-id="fec32-109">次に示すのは、[switch](./switch.md) ステートメントで `break` を使用する例です。</span><span class="sxs-lookup"><span data-stu-id="fec32-109">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="fec32-110">`4` を入力すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fec32-110">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="fec32-111">例</span><span class="sxs-lookup"><span data-stu-id="fec32-111">Example</span></span>

<span data-ttu-id="fec32-112">この例では、`break` ステートメントを使用して、入れ子になった内側のループから抜け出し、外側のループに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="fec32-112">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="fec32-113">コントロールは、入れ子になったループの 1 つ上のレベルに_のみ_返されます。</span><span class="sxs-lookup"><span data-stu-id="fec32-113">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="fec32-114">例</span><span class="sxs-lookup"><span data-stu-id="fec32-114">Example</span></span>

<span data-ttu-id="fec32-115">この例で、`break` ステートメントは、ループの各繰り返し時に現在の分岐を抜けるためだけに使用されています。</span><span class="sxs-lookup"><span data-stu-id="fec32-115">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="fec32-116">ループ自体は、入れ子になった [switch](./switch.md) ステートメントに属する `break` のインスタンスの影響は受けません。</span><span class="sxs-lookup"><span data-stu-id="fec32-116">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="fec32-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fec32-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fec32-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fec32-118">See also</span></span>

- [<span data-ttu-id="fec32-119">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="fec32-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fec32-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fec32-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fec32-121">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="fec32-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="fec32-122">switch</span><span class="sxs-lookup"><span data-stu-id="fec32-122">switch</span></span>](./switch.md)
