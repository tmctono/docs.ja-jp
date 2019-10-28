---
title: C# の式 - C# 言語のツアー
description: 式、オペランド、および演算子は、C# 言語の構成要素です
ms.date: 04/25/2019
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4866d12118518827c1f7032ac09933927f0f3c52
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395672"
---
# <a name="expressions"></a><span data-ttu-id="6d701-103">式</span><span class="sxs-lookup"><span data-stu-id="6d701-103">Expressions</span></span>

<span data-ttu-id="6d701-104">*式*は、*オペランド*と*演算子*で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="6d701-105">式の演算子は、オペランドに適用する演算を表します。</span><span class="sxs-lookup"><span data-stu-id="6d701-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="6d701-106">演算子の例として、`+`、`-`、`*`、`/`、および `new` などがあります。</span><span class="sxs-lookup"><span data-stu-id="6d701-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="6d701-107">オペランドの例としては、リテラル、フィールド、ローカル変数、式などがあります。</span><span class="sxs-lookup"><span data-stu-id="6d701-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="6d701-108">複数の演算子を含む式の場合、演算子の*優先順位*によって各々の演算子が評価される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="6d701-109">たとえば、式 `x + y * z` の評価は `x + (y * z)` ですが、これは `*` 演算子が `+` 演算子より高い優先順位だからです。</span><span class="sxs-lookup"><span data-stu-id="6d701-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="6d701-110">1 つのオペランドが同じ優先順位を持つ 2 つの演算子の間で発生した場合、演算子の*結合性*によって演算が実行される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="6d701-111">代入演算子および null 合体演算子を除くすべてのバイナリ演算子は、"*左からの結合*"、つまり演算は左から右に実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-111">Except for the assignment and null-coalescing operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="6d701-112">たとえば、`x + y + z` は `(x + y) + z` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="6d701-113">代入演算子、null 合体 `??` および `??=` 演算子、および条件演算子 `?:` は、"*右からの結合*"、つまり演算は右から左に実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-113">The assignment operators, the null-coalescing `??` and `??=` operators, and the conditional operator `?:` are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="6d701-114">たとえば、`x = y = z` は `x = (y = z)` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="6d701-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="6d701-115">優先順位と結合性は、かっこを使用して制御することができます。</span><span class="sxs-lookup"><span data-stu-id="6d701-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="6d701-116">たとえば、`x + y * z` は最初に `y` と `z` を掛け、そして結果を `x` に足しますが、`(x + y) * z` では最初に `x` と `y` を足してから `z` を掛けます。</span><span class="sxs-lookup"><span data-stu-id="6d701-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="6d701-117">ほとんどの演算子は[*オーバーロード*](../language-reference/operators/operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="6d701-117">Most operators can be [*overloaded*](../language-reference/operators/operator-overloading.md).</span></span> <span data-ttu-id="6d701-118">演算子をオーバーロードすると、ユーザー定義演算子の実装を、1 つまたは両方のオペランドがユーザー定義のクラスまたは構造体型である演算子に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6d701-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="6d701-119">C# では、[算術](../language-reference/operators/arithmetic-operators.md)、[論理](../language-reference/operators/boolean-logical-operators.md)、[ビットごとやシフト](../language-reference/operators/bitwise-and-shift-operators.md)の演算に加えて、[等値](../language-reference/operators/equality-operators.md)や[順序](../language-reference/operators/comparison-operators.md)の比較を実行するための多数の演算子を提供しています。</span><span class="sxs-lookup"><span data-stu-id="6d701-119">C# provides a number of operators to perform [arithmetic](../language-reference/operators/arithmetic-operators.md), [logical](../language-reference/operators/boolean-logical-operators.md), [bitwise and shift](../language-reference/operators/bitwise-and-shift-operators.md) operations and [equality](../language-reference/operators/equality-operators.md) and [order](../language-reference/operators/comparison-operators.md) comparisons.</span></span>

<span data-ttu-id="6d701-120">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](../language-reference/operators/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d701-120">For the complete list of C# operators ordered by precedence level, see [C# operators](../language-reference/operators/index.md).</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="6d701-121">[前へ](types-and-variables.md)
> [次へ](statements.md)</span><span class="sxs-lookup"><span data-stu-id="6d701-121">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
