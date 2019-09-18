---
title: '条件式: if...そうしたら。。。さも'
description: でF#条件式を記述して、異なるコードの分岐を実行する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083034"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="3e8bb-103">条件式:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="3e8bb-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="3e8bb-104">式`if...then...else`は、コードの異なる分岐を実行し、指定されたブール式に応じて別の値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e8bb-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e8bb-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="3e8bb-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e8bb-106">Remarks</span></span>

<span data-ttu-id="3e8bb-107">前の構文では 、ブール式がに`true`評価されると、expression1 が実行されます。それ以外の場合は、 *expression2*が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="3e8bb-108">他の言語`if...then...else`とは異なり、コンストラクトはステートメントではなく、式です。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="3e8bb-109">つまり、値が生成されます。これは、が実行される分岐の最後の式の値です。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="3e8bb-110">各分岐で生成される値の型が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="3e8bb-111">明示的`else`な分岐がない場合、その型`unit`はになります。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="3e8bb-112">したがって、 `then`分岐の型が以外`unit`の型である場合は、同じ戻り値`else`の型を持つ分岐が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="3e8bb-113">式を連結する場合は、の`else if`代わりに`elif`キーワードを使用できます。これらは等価です。 `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="3e8bb-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="3e8bb-114">例</span><span class="sxs-lookup"><span data-stu-id="3e8bb-114">Example</span></span>

<span data-ttu-id="3e8bb-115">次の例は、式の`if...then...else`使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3e8bb-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="3e8bb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e8bb-116">See also</span></span>

- [<span data-ttu-id="3e8bb-117">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="3e8bb-117">F# Language Reference</span></span>](index.md)
