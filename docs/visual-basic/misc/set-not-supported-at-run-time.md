---
title: Set は実行時にはサポートされません
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: 563cecde105f18ebba6da909a1977a272b052413
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91060628"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="dc697-102">Set は実行時にはサポートされません</span><span class="sxs-lookup"><span data-stu-id="dc697-102">Set not supported at run time</span></span>

<span data-ttu-id="dc697-103">デザイン時にのみ値を設定できるプロパティを設定または変更しようとしました。</span><span class="sxs-lookup"><span data-stu-id="dc697-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc697-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="dc697-104">To correct this error</span></span>  
  
1. <span data-ttu-id="dc697-105">コードからプロパティへの参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc697-105">Remove the reference to the property from your code.</span></span>  
  
2. <span data-ttu-id="dc697-106">実行時に、プロパティの値のみを返す参照に変更します。</span><span class="sxs-lookup"><span data-stu-id="dc697-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc697-107">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="dc697-107">See also</span></span>

- [<span data-ttu-id="dc697-108">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="dc697-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
