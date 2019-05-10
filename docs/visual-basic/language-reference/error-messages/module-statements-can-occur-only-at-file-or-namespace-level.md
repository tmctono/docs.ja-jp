---
title: "'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。"
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592099"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="410cc-102">'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="410cc-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="410cc-103">`Module` ステートメントは、ソース ファイルの上部に表示する必要がありますの直後に`Option`と`Imports`ステートメント、グローバル属性および名前空間の宣言が、その他のすべての宣言の前にします。</span><span class="sxs-lookup"><span data-stu-id="410cc-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="410cc-104">**エラー ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="410cc-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="410cc-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="410cc-105">To correct this error</span></span>  
  
- <span data-ttu-id="410cc-106">`Module` ステートメントを名前空間の宣言またはソース ファイルの先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="410cc-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410cc-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="410cc-107">See also</span></span>

- [<span data-ttu-id="410cc-108">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="410cc-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
