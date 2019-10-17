---
title: break ステートメント - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 2628da73364cf94a52e2862d349243c100d4afaf
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179935"
---
# <a name="break-c-reference"></a><span data-ttu-id="b5776-102">break (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b5776-102">break (C# Reference)</span></span>

<span data-ttu-id="b5776-103">`break` ステートメントは、これを囲むループまたは [switch](./switch.md) ステートメントのうち、最も内側のものを終了させます。</span><span class="sxs-lookup"><span data-stu-id="b5776-103">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="b5776-104">終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。</span><span class="sxs-lookup"><span data-stu-id="b5776-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="b5776-105">例</span><span class="sxs-lookup"><span data-stu-id="b5776-105">Example</span></span>

<span data-ttu-id="b5776-106">次の例では、条件付きステートメントに 1 から 100 までをカウントするカウンターがあります。ただし、`break` ステートメントによって、ループは 4 回で終了します。</span><span class="sxs-lookup"><span data-stu-id="b5776-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="b5776-107">例</span><span class="sxs-lookup"><span data-stu-id="b5776-107">Example</span></span>

<span data-ttu-id="b5776-108">次に示すのは、[switch](./switch.md) ステートメントで `break` を使用する例です。</span><span class="sxs-lookup"><span data-stu-id="b5776-108">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="b5776-109">`4` を入力すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b5776-109">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="b5776-110">例</span><span class="sxs-lookup"><span data-stu-id="b5776-110">Example</span></span>

<span data-ttu-id="b5776-111">この例では、`break` ステートメントを使用して、入れ子になった内側のループから抜け出し、外側のループに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="b5776-111">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="b5776-112">コントロールは、入れ子になったループの 1 つ上のレベルに_のみ_返されます。</span><span class="sxs-lookup"><span data-stu-id="b5776-112">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="b5776-113">例</span><span class="sxs-lookup"><span data-stu-id="b5776-113">Example</span></span>

<span data-ttu-id="b5776-114">この例で、`break` ステートメントは、ループの各繰り返し時に現在の分岐を抜けるためだけに使用されています。</span><span class="sxs-lookup"><span data-stu-id="b5776-114">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="b5776-115">ループ自体は、入れ子になった [switch](./switch.md) ステートメントに属する `break` のインスタンスの影響は受けません。</span><span class="sxs-lookup"><span data-stu-id="b5776-115">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="b5776-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b5776-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b5776-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5776-117">See also</span></span>

- [<span data-ttu-id="b5776-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b5776-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b5776-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b5776-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b5776-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b5776-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b5776-121">switch</span><span class="sxs-lookup"><span data-stu-id="b5776-121">switch</span></span>](./switch.md)
