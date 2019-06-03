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
ms.openlocfilehash: 15b193d9f294c01826b6b60587678ad76248e976
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422064"
---
# <a name="break-c-reference"></a><span data-ttu-id="3c621-102">break (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3c621-102">break (C# Reference)</span></span>

<span data-ttu-id="3c621-103">`break` ステートメントは、これを囲むループまたは [switch](../../../csharp/language-reference/keywords/switch.md) ステートメントのうち、最も内側のものを終了させます。</span><span class="sxs-lookup"><span data-stu-id="3c621-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="3c621-104">終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。</span><span class="sxs-lookup"><span data-stu-id="3c621-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="3c621-105">例</span><span class="sxs-lookup"><span data-stu-id="3c621-105">Example</span></span>

<span data-ttu-id="3c621-106">次の例では、条件付きステートメントに 1 から 100 までをカウントするカウンターがあります。ただし、`break` ステートメントによって、ループは 4 回で終了します。</span><span class="sxs-lookup"><span data-stu-id="3c621-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="3c621-107">例</span><span class="sxs-lookup"><span data-stu-id="3c621-107">Example</span></span>

<span data-ttu-id="3c621-108">この例では、`break` ステートメントを使用して、入れ子になった内側のループから抜け出し、外側のループに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="3c621-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="3c621-109">例</span><span class="sxs-lookup"><span data-stu-id="3c621-109">Example</span></span>

<span data-ttu-id="3c621-110">次に示すのは、[switch](../../../csharp/language-reference/keywords/switch.md) ステートメントで `break` を使用する例です。</span><span class="sxs-lookup"><span data-stu-id="3c621-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="3c621-111">`4` を入力すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3c621-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="3c621-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="3c621-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3c621-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c621-113">See also</span></span>

- [<span data-ttu-id="3c621-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3c621-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="3c621-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3c621-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3c621-116">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="3c621-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="3c621-117">switch</span><span class="sxs-lookup"><span data-stu-id="3c621-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)
