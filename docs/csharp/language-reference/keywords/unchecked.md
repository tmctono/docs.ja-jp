---
title: unchecked キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 0d96b9af0eaee81da8532c1facbfa8b1d1a8128f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633497"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="2d1d9-102">unchecked (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2d1d9-102">unchecked (C# Reference)</span></span>

<span data-ttu-id="2d1d9-103">`unchecked` キーワードは、整数型の算術演算と変換に対してオーバーフロー チェックを抑制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="2d1d9-104">unchecked コンテキストでは、式が変換先の型の範囲外の値を生成した場合に、オーバーフローが検出されません。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="2d1d9-105">たとえば、次の例では、`unchecked` ブロックまたは式で計算が行われるため、結果が integer に対して大きすぎるという事実が無視され、`int1` には-2,147,483,639 の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="2d1d9-106">`unchecked` 環境が削除されると、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="2d1d9-107">式のすべての用語が定数なので、コンパイル時にはオーバーフローを検出できます。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="2d1d9-108">非定数の用語を含む式は、実行時およびコンパイル時に既定ではチェックされません。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="2d1d9-109">checked 環境を有効にする方法については、「[checked](checked.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-109">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="2d1d9-110">オーバーフローのチェックには時間がかかるため、オーバーフローの危険性がない状況では、unchecked コードを使用することで、パフォーマンスを改善できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="2d1d9-111">ただし、オーバーフローの可能性がある場合は、checked 環境を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-111">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="2d1d9-112">例</span><span class="sxs-lookup"><span data-stu-id="2d1d9-112">Example</span></span>

<span data-ttu-id="2d1d9-113">この例では、`unchecked` キーワードの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d1d9-113">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="2d1d9-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2d1d9-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2d1d9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1d9-115">See also</span></span>

- [<span data-ttu-id="2d1d9-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2d1d9-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2d1d9-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2d1d9-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2d1d9-118">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="2d1d9-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2d1d9-119">Checked と Unchecked</span><span class="sxs-lookup"><span data-stu-id="2d1d9-119">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="2d1d9-120">checked</span><span class="sxs-lookup"><span data-stu-id="2d1d9-120">checked</span></span>](checked.md)
