---
title: "'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。"
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: d01c30571fc34e142300ac8706c56d5e99175fcf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397208"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="26299-102">'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="26299-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="26299-103">`Module` ステートメントは、ソース ファイルの先頭の、`Option` および `Imports` ステートメント、グローバル属性、および名前空間宣言の直後、ただし他のすべての宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26299-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="26299-104">**エラー ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="26299-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26299-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="26299-105">To correct this error</span></span>  
  
- <span data-ttu-id="26299-106">`Module` ステートメントを名前空間の宣言またはソース ファイルの先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="26299-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26299-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="26299-107">See also</span></span>

- [<span data-ttu-id="26299-108">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="26299-108">Module Statement</span></span>](../statements/module-statement.md)
