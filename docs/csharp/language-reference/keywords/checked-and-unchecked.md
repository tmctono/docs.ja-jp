---
description: Checked と Unchecked - C# リファレンス
title: Checked と Unchecked - C# リファレンス
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 0ab30eb238a4db21233da612d132dfcbdb9e8895
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160516"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="ec455-103">Checked と Unchecked (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ec455-103">Checked and Unchecked (C# Reference)</span></span>

<span data-ttu-id="ec455-104">C# のステートメントは、checked または unchecked のいずれかのコンテキストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ec455-104">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="ec455-105">checked コンテキストでは、算術オーバーフローにより例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="ec455-105">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="ec455-106">unchecked コンテキストでは、算術オーバーフローが無視され、結果の格納先の型に収まらない上位ビットが破棄されて、結果が切り詰められます。</span><span class="sxs-lookup"><span data-stu-id="ec455-106">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="ec455-107">[checked](checked.md): checked コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec455-107">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="ec455-108">[unchecked](unchecked.md): unchecked コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec455-108">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="ec455-109">オーバーフロー チェックにより、次の操作が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="ec455-109">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="ec455-110">整数型で次の定義済み演算子を使用する式:</span><span class="sxs-lookup"><span data-stu-id="ec455-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="ec455-111">`++`、`--`、(単項) `-`、`+`、`-`、`*`、`/`</span><span class="sxs-lookup"><span data-stu-id="ec455-111">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="ec455-112">整数型間か、`float` または `double` から整数型へのの明示的な数値変換。</span><span class="sxs-lookup"><span data-stu-id="ec455-112">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="ec455-113">`checked` と `unchecked` のいずれも指定されない場合、非定数式 (実行時に評価される式) の既定のコンテキストが [-checked](../compiler-options/checked-compiler-option.md) コンパイラ オプションの値によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ec455-113">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ec455-114">既定では、そのオプションの値の設定が解除され、算術演算が unchecked コンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ec455-114">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="ec455-115">定数式 (コンパイル時に完全に評価される式) の場合、既定のコンテキストは常に確認されます。</span><span class="sxs-lookup"><span data-stu-id="ec455-115">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="ec455-116">定数式が unchecked コンテキストに明示的に配置されていない限り、式のコンパイル時の評価中に発生するオーバーフローによってコンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ec455-116">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec455-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec455-117">See also</span></span>

- [<span data-ttu-id="ec455-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ec455-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ec455-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ec455-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ec455-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="ec455-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ec455-121">ステートメントのキーワード</span><span class="sxs-lookup"><span data-stu-id="ec455-121">Statement Keywords</span></span>](statement-keywords.md)
