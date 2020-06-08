---
title: '方法: 値の変わらない変数を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 04e08784b5cfbdeb6db73b9b00fe9afa201bd06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410517"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="e4910-102">方法: 値の変わらない変数を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4910-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="e4910-103">値の変わらない変数の概念は、矛盾しているように見えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e4910-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="e4910-104">しかし、定数を使用することができず、固定値を持つ変数を用意すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4910-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="e4910-105">そのような場合は、[ReadOnly](../../../language-reference/modifiers/readonly.md) キーワードを使用してメンバー変数を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="e4910-105">In such a case you can define a member variable with the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="e4910-106">次のような状況では、[Const ステートメント](../../../language-reference/statements/const-statement.md)を使用して定数値の宣言および割り当てを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e4910-106">You cannot use the [Const Statement](../../../language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="e4910-107">使用したいデータ型を `Const` ステートメントに指定できない</span><span class="sxs-lookup"><span data-stu-id="e4910-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="e4910-108">コンパイル時に値がわからない</span><span class="sxs-lookup"><span data-stu-id="e4910-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="e4910-109">コンパイル時に定数値を計算できない</span><span class="sxs-lookup"><span data-stu-id="e4910-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="e4910-110">値の変わらない変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="e4910-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="e4910-111">モジュール レベルで、[Dim ステートメント](../../../language-reference/statements/dim-statement.md)を使用してメンバー変数を宣言し、[ReadOnly](../../../language-reference/modifiers/readonly.md) キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="e4910-111">At module level, declare a member variable with the [Dim Statement](../../../language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="e4910-112">`ReadOnly` は、メンバー変数に対してのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4910-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="e4910-113">つまり、プロシージャの外部で、モジュール レベルで、この変数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4910-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="e4910-114">コンパイル時に単一のステートメントで値を計算できる場合は、`Dim` ステートメントで初期化句を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4910-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="e4910-115">[As](../../../language-reference/statements/as-clause.md) 句の後に等号 (`=`) を置き、その後に式を続けます。</span><span class="sxs-lookup"><span data-stu-id="e4910-115">Follow the [As](../../../language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="e4910-116">コンパイラがこの式を定数値に評価できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e4910-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="e4910-117">`ReadOnly` 変数に値を割り当てることができるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="e4910-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="e4910-118">一度それを行うと、コードによってその値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4910-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="e4910-119">コンパイル時に値がわからない場合、またはコンパイル時に単一のステートメントで値を計算できない場合でも、実行時にコンストラクター内でそれを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e4910-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="e4910-120">これを行うには、クラスまたは構造体のレベルで `ReadOnly` 変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4910-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="e4910-121">そのクラスまたは構造体のコンストラクターで、変数の固定値を計算し、それを変数に割り当てたら、コンストラクターから戻ります。</span><span class="sxs-lookup"><span data-stu-id="e4910-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4910-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4910-122">See also</span></span>

- [<span data-ttu-id="e4910-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="e4910-123">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="e4910-124">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4910-124">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
