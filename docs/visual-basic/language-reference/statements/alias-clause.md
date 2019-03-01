---
title: Alias 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978229"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="f15ba-102">Alias 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f15ba-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="f15ba-103">外部プロシージャにその DLL 内の別の名前があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f15ba-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f15ba-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f15ba-104">Remarks</span></span>  
 <span data-ttu-id="f15ba-105">`Alias`キーワードは、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f15ba-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="f15ba-106">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="f15ba-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="f15ba-107">次の例では、 `Alias` advapi32.dll、内の関数の名前を指定するキーワードが使用される`GetUserNameA`、その`getUserName`の代わりにこの例では使用します。</span><span class="sxs-lookup"><span data-stu-id="f15ba-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="f15ba-108">関数`getUserName`sub で呼び出される`getUser`、現在のユーザーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f15ba-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="f15ba-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f15ba-109">See also</span></span>
- [<span data-ttu-id="f15ba-110">キーワード</span><span class="sxs-lookup"><span data-stu-id="f15ba-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
