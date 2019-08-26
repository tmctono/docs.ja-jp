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
ms.openlocfilehash: 77d18d12cd0fabb26906a5b58dc3939da6214a29
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602248"
---
# <a name="break-c-reference"></a><span data-ttu-id="37cd8-102">break (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="37cd8-102">break (C# Reference)</span></span>

<span data-ttu-id="37cd8-103">`break` ステートメントは、これを囲むループまたは [switch](./switch.md) ステートメントのうち、最も内側のものを終了させます。</span><span class="sxs-lookup"><span data-stu-id="37cd8-103">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="37cd8-104">終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。</span><span class="sxs-lookup"><span data-stu-id="37cd8-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="37cd8-105">例</span><span class="sxs-lookup"><span data-stu-id="37cd8-105">Example</span></span>

<span data-ttu-id="37cd8-106">次の例では、条件付きステートメントに 1 から 100 までをカウントするカウンターがあります。ただし、`break` ステートメントによって、ループは 4 回で終了します。</span><span class="sxs-lookup"><span data-stu-id="37cd8-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="37cd8-107">例</span><span class="sxs-lookup"><span data-stu-id="37cd8-107">Example</span></span>

<span data-ttu-id="37cd8-108">この例では、`break` ステートメントを使用して、入れ子になった内側のループから抜け出し、外側のループに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="37cd8-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="37cd8-109">例</span><span class="sxs-lookup"><span data-stu-id="37cd8-109">Example</span></span>

<span data-ttu-id="37cd8-110">次に示すのは、[switch](./switch.md) ステートメントで `break` を使用する例です。</span><span class="sxs-lookup"><span data-stu-id="37cd8-110">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="37cd8-111">`4` を入力すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="37cd8-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="37cd8-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="37cd8-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="37cd8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="37cd8-113">See also</span></span>

- [<span data-ttu-id="37cd8-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="37cd8-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="37cd8-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="37cd8-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="37cd8-116">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="37cd8-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="37cd8-117">switch</span><span class="sxs-lookup"><span data-stu-id="37cd8-117">switch</span></span>](./switch.md)
