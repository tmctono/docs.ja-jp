---
title: '方法: 値が変更されない変数を作成する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d201e95463dd0431825fee03ebfd340ac80cc552
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630887"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="14e1e-102">方法: 値が変更されない変数を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14e1e-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="14e1e-103">値を変更しない変数の概念は、矛盾しているように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="14e1e-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="14e1e-104">しかし、定数を使用できない場合は、固定値を持つ変数を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="14e1e-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="14e1e-105">このような場合は、 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)キーワードを使用してメンバー変数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="14e1e-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="14e1e-106">次のような状況では、 [Const ステートメント](../../../../visual-basic/language-reference/statements/const-statement.md)を使用して定数値を宣言して割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="14e1e-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="14e1e-107">ステートメント`Const`は、使用するデータ型を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="14e1e-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="14e1e-108">コンパイル時に値がわからない</span><span class="sxs-lookup"><span data-stu-id="14e1e-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="14e1e-109">コンパイル時に定数値を計算できません</span><span class="sxs-lookup"><span data-stu-id="14e1e-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="14e1e-110">値を変更しない変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="14e1e-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="14e1e-111">モジュールレベルで、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用してメンバー変数を宣言し、 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="14e1e-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="14e1e-112">は、メンバー `ReadOnly`変数に対してのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="14e1e-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="14e1e-113">これは、プロシージャの外部でモジュールレベルで変数を定義する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="14e1e-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="14e1e-114">コンパイル時に1つのステートメントで値を計算できる場合は、 `Dim`ステートメントで初期化句を使用します。</span><span class="sxs-lookup"><span data-stu-id="14e1e-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="14e1e-115">[As](../../../../visual-basic/language-reference/statements/as-clause.md)句に続けて等号 (`=`) を指定し、その後に式を指定します。</span><span class="sxs-lookup"><span data-stu-id="14e1e-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="14e1e-116">コンパイラがこの式を定数値に評価できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14e1e-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="14e1e-117">`ReadOnly`変数に値を割り当てることができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="14e1e-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="14e1e-118">その後、コードで値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="14e1e-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="14e1e-119">コンパイル時に値がわからない場合、またはコンパイル時に1つのステートメントで値を計算できない場合でも、コンストラクターで実行時に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="14e1e-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="14e1e-120">これを行うには、クラスまた`ReadOnly`は構造体レベルで変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e1e-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="14e1e-121">そのクラスまたは構造体のコンストラクターで、変数の固定値を計算し、コンストラクターから戻る前に変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="14e1e-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="14e1e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e1e-122">See also</span></span>

- [<span data-ttu-id="14e1e-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="14e1e-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="14e1e-124">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="14e1e-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
