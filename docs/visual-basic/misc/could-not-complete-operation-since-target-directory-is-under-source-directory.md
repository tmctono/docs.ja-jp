---
title: ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039428"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="4381b-102">ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした</span><span class="sxs-lookup"><span data-stu-id="4381b-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="4381b-103">循環操作が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4381b-103">A cyclic operation has failed.</span></span> <span data-ttu-id="4381b-104">循環操作は循環しているため、完了できません。</span><span class="sxs-lookup"><span data-stu-id="4381b-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="4381b-105">たとえば、オブジェクト A がオブジェクト B の継承を試行し、同様にオブジェクト B がオブジェクト A の継承を試行するような場合です。</span><span class="sxs-lookup"><span data-stu-id="4381b-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4381b-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4381b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4381b-107">継承を行うときには、参照の循環がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4381b-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4381b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="4381b-108">See also</span></span>

- [<span data-ttu-id="4381b-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="4381b-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="4381b-110">Visual Studio デバッガーでブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4381b-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
