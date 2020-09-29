---
title: "'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。"
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 91e6c81bb64c259411cbef8a36629b8b320ea584
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873758"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="b5279-102">'Module' ステートメントは、ファイルまたは名前空間レベルでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="b5279-102">'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="b5279-103">`Module` ステートメントは、ソース ファイルの先頭の、`Option` および `Imports` ステートメント、グローバル属性、および名前空間宣言の直後、ただし他のすべての宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5279-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="b5279-104">**エラー ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="b5279-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5279-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b5279-105">To correct this error</span></span>  
  
- <span data-ttu-id="b5279-106">`Module` ステートメントを名前空間の宣言またはソース ファイルの先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5279-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5279-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5279-107">See also</span></span>

- [<span data-ttu-id="b5279-108">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="b5279-108">Module Statement</span></span>](../statements/module-statement.md)
