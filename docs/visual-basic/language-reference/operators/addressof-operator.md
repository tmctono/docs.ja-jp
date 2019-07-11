---
title: AddressOf 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760378"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="a9288-102">AddressOf 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9288-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="a9288-103">特定のプロシージャを参照するデリゲート インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9288-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9288-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9288-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="a9288-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a9288-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="a9288-106">必須。</span><span class="sxs-lookup"><span data-stu-id="a9288-106">Required.</span></span> <span data-ttu-id="a9288-107">新しく作成されたデリゲートが参照するプロシージャを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9288-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9288-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9288-108">Remarks</span></span>  
 <span data-ttu-id="a9288-109">`AddressOf`演算子は、sub またはで指定された関数を指すデリゲートを作成します。`procedurename`します。</span><span class="sxs-lookup"><span data-stu-id="a9288-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="a9288-110">ときに、指定したプロシージャは、インスタンス メソッド、デリゲートがインスタンスとメソッドの両方を参照します。</span><span class="sxs-lookup"><span data-stu-id="a9288-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="a9288-111">次に、デリゲートが呼び出されたときに、指定したインスタンスの指定されたメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a9288-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="a9288-112">`AddressOf` Delegate コンス トラクターのオペランドとして使用できる演算子またはにおいて、コンパイラによってデリゲートの型を決定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9288-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9288-113">例</span><span class="sxs-lookup"><span data-stu-id="a9288-113">Example</span></span>  
 <span data-ttu-id="a9288-114">この例では、`AddressOf`を処理するデリゲートを指定する演算子、`Click`ボタンのイベント。</span><span class="sxs-lookup"><span data-stu-id="a9288-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="a9288-115">例</span><span class="sxs-lookup"><span data-stu-id="a9288-115">Example</span></span>  
 <span data-ttu-id="a9288-116">次の例では、`AddressOf`スレッドのスタートアップ関数を指定する演算子。</span><span class="sxs-lookup"><span data-stu-id="a9288-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a9288-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9288-117">See also</span></span>

- [<span data-ttu-id="a9288-118">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="a9288-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="a9288-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="a9288-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a9288-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="a9288-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a9288-121">デリゲート</span><span class="sxs-lookup"><span data-stu-id="a9288-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
