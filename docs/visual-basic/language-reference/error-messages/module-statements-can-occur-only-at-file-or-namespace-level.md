---
title: "'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。"
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920862"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="d0de7-102">'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="d0de7-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="d0de7-103">`Module` ステートメントは、ソース ファイルの上部に表示する必要がありますの直後に`Option`と`Imports`ステートメント、グローバル属性および名前空間の宣言が、その他のすべての宣言の前にします。</span><span class="sxs-lookup"><span data-stu-id="d0de7-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="d0de7-104">**エラー ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="d0de7-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0de7-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d0de7-105">To correct this error</span></span>  
  
- <span data-ttu-id="d0de7-106">`Module` ステートメントを名前空間の宣言またはソース ファイルの先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0de7-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0de7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0de7-107">See also</span></span>

- [<span data-ttu-id="d0de7-108">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="d0de7-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
