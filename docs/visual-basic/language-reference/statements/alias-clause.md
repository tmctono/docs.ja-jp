---
title: Alias 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053354"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="cf2be-102">Alias 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf2be-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="cf2be-103">外部プロシージャにその DLL 内の別の名前があることを示します。</span><span class="sxs-lookup"><span data-stu-id="cf2be-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf2be-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf2be-104">Remarks</span></span>  
 <span data-ttu-id="cf2be-105">`Alias`キーワードは、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf2be-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="cf2be-106">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf2be-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="cf2be-107">次の例では、 `Alias` advapi32.dll、内の関数の名前を指定するキーワードが使用される`GetUserNameA`、その`getUserName`の代わりにこの例では使用します。</span><span class="sxs-lookup"><span data-stu-id="cf2be-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="cf2be-108">関数`getUserName`sub で呼び出される`getUser`、現在のユーザーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf2be-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="cf2be-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf2be-109">See also</span></span>

- [<span data-ttu-id="cf2be-110">キーワード</span><span class="sxs-lookup"><span data-stu-id="cf2be-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
