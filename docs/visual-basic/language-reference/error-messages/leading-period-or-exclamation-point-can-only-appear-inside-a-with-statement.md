---
title: 先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 15390fb506fe9bca10f6917f5b26451a5569bece
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322850"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="e042a-102">先頭の '.' または '!' は、'With' ステートメント内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e042a-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="e042a-103">ピリオド (.) または感嘆符 (!) でない内部、`With`左の式がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e042a-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="e042a-104">メンバー アクセス (`.`) およびディクショナリ メンバー アクセス (`!`) メンバーを含む要素を指定する式が必要です。</span><span class="sxs-lookup"><span data-stu-id="e042a-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="e042a-105">これは、アクセサーのまたはのターゲットとしての左側にすぐに表示する必要があります、`With`メンバー アクセスを含むブロックします。</span><span class="sxs-lookup"><span data-stu-id="e042a-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="e042a-106">**エラー ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="e042a-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e042a-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e042a-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e042a-108">いることを確認、`With`ブロックが正しく書式設定します。</span><span class="sxs-lookup"><span data-stu-id="e042a-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="e042a-109">存在する場合ありません`With`ブロック、メンバーを含む定義の要素に評価されるアクセサーの左側に式を追加します。</span><span class="sxs-lookup"><span data-stu-id="e042a-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e042a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e042a-110">See also</span></span>

- [<span data-ttu-id="e042a-111">コード内の特殊文字</span><span class="sxs-lookup"><span data-stu-id="e042a-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="e042a-112">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="e042a-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
