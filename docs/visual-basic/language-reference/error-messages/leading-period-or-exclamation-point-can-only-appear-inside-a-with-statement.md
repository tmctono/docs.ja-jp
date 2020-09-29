---
title: 先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873851"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="88e2d-102">先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="88e2d-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="88e2d-103">`With` ブロック内にないピリオド (.) または感嘆符 (!) が、左側に式がない状態で指定されています。</span><span class="sxs-lookup"><span data-stu-id="88e2d-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="88e2d-104">メンバー アクセス (`.`) とディクショナリ メンバー アクセス (`!`) には、メンバーが含まれている要素を指定した式が必要になります。</span><span class="sxs-lookup"><span data-stu-id="88e2d-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="88e2d-105">これは、アクセサーのすぐ左側、またはメンバー アクセスを含む `With` ブロックのターゲットとして指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e2d-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="88e2d-106">**エラー ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="88e2d-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88e2d-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="88e2d-107">To correct this error</span></span>  
  
1. <span data-ttu-id="88e2d-108">`With` ブロックが正しく書式設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88e2d-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="88e2d-109">`With` ブロックがない場合は、アクセサーの左側に、メンバーを含む定義済みの要素に評価される式を追加します。</span><span class="sxs-lookup"><span data-stu-id="88e2d-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e2d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="88e2d-110">See also</span></span>

- [<span data-ttu-id="88e2d-111">コード内の特殊文字</span><span class="sxs-lookup"><span data-stu-id="88e2d-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="88e2d-112">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="88e2d-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
