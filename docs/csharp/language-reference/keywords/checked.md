---
description: checked キーワード - C# リファレンス
title: checked キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 4dd8bc02d3af89d6bab3aef55a88cb8b40704da6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138281"
---
# <a name="checked-c-reference"></a><span data-ttu-id="4bbd7-103">checked (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4bbd7-103">checked (C# Reference)</span></span>

<span data-ttu-id="4bbd7-104">`checked` キーワードは、整数型の算術演算と変換に対してオーバーフロー チェックを明示的に有効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-104">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="4bbd7-105">既定では、定数値のみを含む式がチェック先の型の範囲外にある値を生成した場合、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-105">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="4bbd7-106">式が 1 つ以上の非定数値を含む場合、コンパイラはオーバーフローを検出しません。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-106">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="4bbd7-107">次の例で `i2` に割り当てられた式を評価しても、コンパイラ エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-107">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="4bbd7-108">既定では、これらの非定数式のオーバーフローは実行時にもチェックされず、オーバーフロー例外も発生しません。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="4bbd7-109">前の例では、2 つの正の整数の合計として -2,147,483,639 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="4bbd7-110">オーバーフロー チェックを有効にするには、コンパイラ オプション、環境設定、または `checked` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="4bbd7-111">`checked` 式または `checked` ブロックを使用して、前の合計によって生じたオーバーフローを実行時に検出する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="4bbd7-112">どちらの例でもオーバーフロー例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-112">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="4bbd7-113">[unchecked](./unchecked.md) キーワードを使用してオーバーフロー チェックを行わないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-113">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="4bbd7-114">例</span><span class="sxs-lookup"><span data-stu-id="4bbd7-114">Example</span></span>

<span data-ttu-id="4bbd7-115">この例では、`checked` を使用して実行時のオーバーフロー チェックを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4bbd7-115">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="4bbd7-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4bbd7-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4bbd7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bbd7-117">See also</span></span>

- [<span data-ttu-id="4bbd7-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="4bbd7-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4bbd7-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4bbd7-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4bbd7-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="4bbd7-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="4bbd7-121">Checked と Unchecked</span><span class="sxs-lookup"><span data-stu-id="4bbd7-121">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="4bbd7-122">unchecked</span><span class="sxs-lookup"><span data-stu-id="4bbd7-122">unchecked</span></span>](./unchecked.md)
