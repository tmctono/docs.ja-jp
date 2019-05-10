---
title: '方法: 値 (Visual Basic) 変化しない変数を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 3a9fa93b69c9abb42b2dd7eae623048f3628999e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663570"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="797f6-102">方法: 値 (Visual Basic) 変化しない変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="797f6-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="797f6-103">矛盾する値を変更しない変数の概念があります。</span><span class="sxs-lookup"><span data-stu-id="797f6-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="797f6-104">定数では不可能である場合もありますし、固定値を持つ変数を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="797f6-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="797f6-105">このような場合でメンバー変数を定義することができます、 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="797f6-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="797f6-106">使用することはできません、 [Const ステートメント](../../../../visual-basic/language-reference/statements/const-statement.md)宣言を次の状況で定数の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="797f6-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
- <span data-ttu-id="797f6-107">`Const`ステートメントには、使用するデータ型は受け入れません。</span><span class="sxs-lookup"><span data-stu-id="797f6-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
- <span data-ttu-id="797f6-108">コンパイル時に、値がわからない</span><span class="sxs-lookup"><span data-stu-id="797f6-108">You do not know the value at compile time</span></span>  
  
- <span data-ttu-id="797f6-109">コンパイル時に定数値を計算できません。</span><span class="sxs-lookup"><span data-stu-id="797f6-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="797f6-110">値の変わらない変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="797f6-110">To create a variable that does not change in value</span></span>  
  
1. <span data-ttu-id="797f6-111">モジュール レベルでのメンバー変数を宣言、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)、含めると、 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="797f6-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="797f6-112">指定できる`ReadOnly`メンバー変数でのみです。</span><span class="sxs-lookup"><span data-stu-id="797f6-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="797f6-113">つまり、すべてのプロシージャの外部でのモジュール レベル変数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="797f6-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2. <span data-ttu-id="797f6-114">コンパイル時に単一のステートメントで値を計算することができる場合は、初期化句を使用して、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="797f6-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="797f6-115">に従って、[として](../../../../visual-basic/language-reference/statements/as-clause.md)句に等号 (`=`)、その後に式。</span><span class="sxs-lookup"><span data-stu-id="797f6-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="797f6-116">コンパイラが定数の値には、この式を評価してください。</span><span class="sxs-lookup"><span data-stu-id="797f6-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="797f6-117">値を割り当てることができます、`ReadOnly`変数の 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="797f6-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="797f6-118">そうとコードはこれまでこの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="797f6-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="797f6-119">、コンパイル時に、値がわからないするか、または単一のステートメントでは、コンパイル時に計算できない場合は、コンス トラクターで実行時にも割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="797f6-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="797f6-120">これを行うには、宣言する必要があります、`ReadOnly`クラスまたは構造体のレベルにある変数です。</span><span class="sxs-lookup"><span data-stu-id="797f6-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="797f6-121">そのクラスまたは構造体のコンス トラクターで変数の固定値を計算し、コンス トラクターから戻る前に、変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="797f6-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797f6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="797f6-122">See also</span></span>

- [<span data-ttu-id="797f6-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="797f6-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="797f6-124">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="797f6-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
