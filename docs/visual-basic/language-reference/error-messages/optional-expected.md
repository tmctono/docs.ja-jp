---
title: "'Optional' が必要です。"
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 71a25784f357a7e596093b314ed5b3d721d6f92c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341882"
---
# <a name="optional-expected"></a><span data-ttu-id="2d88c-102">'Optional' が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d88c-102">'Optional' expected</span></span>
<span data-ttu-id="2d88c-103">プロシージャ宣言の省略可能な引数には、必須の引数が続きます。</span><span class="sxs-lookup"><span data-stu-id="2d88c-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="2d88c-104">次のオプションの引数すべての引数も省略可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d88c-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="2d88c-105">**エラー ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="2d88c-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d88c-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2d88c-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2d88c-107">引数が必要にする場合は、引数リストで最初の省略可能な引数の前に移動します。</span><span class="sxs-lookup"><span data-stu-id="2d88c-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="2d88c-108">使用して、引数を省略可能にする場合は、`Optional`キーワード。</span><span class="sxs-lookup"><span data-stu-id="2d88c-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d88c-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d88c-109">See also</span></span>

- [<span data-ttu-id="2d88c-110">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="2d88c-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
