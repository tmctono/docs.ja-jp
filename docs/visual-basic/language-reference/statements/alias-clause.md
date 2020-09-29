---
title: Alias 句
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866684"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="77ab6-102">Alias 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77ab6-102">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="77ab6-103">外部プロシージャがその DLL で別の名前を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="77ab6-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77ab6-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="77ab6-104">Remarks</span></span>  

 <span data-ttu-id="77ab6-105">`Alias` キーワードは次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="77ab6-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="77ab6-106">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="77ab6-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="77ab6-107">次の例では、`Alias` キーワードを使用して、advapi32.dll 内の関数の名前 `GetUserNameA` を指定しています。この例では代わりに `getUserName` が使用されています。</span><span class="sxs-lookup"><span data-stu-id="77ab6-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="77ab6-108">関数 `getUserName` はサブ `getUser` で呼び出され、それによって現在のユーザーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77ab6-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="77ab6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="77ab6-109">See also</span></span>

- [<span data-ttu-id="77ab6-110">キーワード</span><span class="sxs-lookup"><span data-stu-id="77ab6-110">Keywords</span></span>](../keywords/index.md)
