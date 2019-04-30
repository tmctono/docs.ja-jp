---
title: ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970119"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="883f3-102">ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした</span><span class="sxs-lookup"><span data-stu-id="883f3-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="883f3-103">循環操作が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="883f3-103">A cyclic operation has failed.</span></span> <span data-ttu-id="883f3-104">循環操作は循環しているため、完了できません。</span><span class="sxs-lookup"><span data-stu-id="883f3-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="883f3-105">たとえば、オブジェクト A がオブジェクト B の継承を試行し、同様にオブジェクト B がオブジェクト A の継承を試行するような場合です。</span><span class="sxs-lookup"><span data-stu-id="883f3-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="883f3-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="883f3-106">To correct this error</span></span>  
  
- <span data-ttu-id="883f3-107">継承を行うときには、参照の循環がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="883f3-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883f3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="883f3-108">See also</span></span>

- [<span data-ttu-id="883f3-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="883f3-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="883f3-110">Visual Studio デバッガーでブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="883f3-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
