---
title: ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 39373cd368282f3b109b450189561366b9e74484
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200573"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="76bb1-102">ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした</span><span class="sxs-lookup"><span data-stu-id="76bb1-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="76bb1-103">循環操作が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="76bb1-103">A cyclic operation has failed.</span></span> <span data-ttu-id="76bb1-104">循環操作は循環しているため、完了できません。</span><span class="sxs-lookup"><span data-stu-id="76bb1-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="76bb1-105">たとえば、オブジェクト A がオブジェクト B の継承を試行し、同様にオブジェクト B がオブジェクト A の継承を試行するような場合です。</span><span class="sxs-lookup"><span data-stu-id="76bb1-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76bb1-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="76bb1-106">To correct this error</span></span>  
  
-   <span data-ttu-id="76bb1-107">継承を行うときには、参照の循環がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="76bb1-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76bb1-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="76bb1-108">See also</span></span>
- [<span data-ttu-id="76bb1-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="76bb1-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="76bb1-110">Visual Studio デバッガーでブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="76bb1-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
