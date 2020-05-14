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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946589"
---
# <a name="optional-expected"></a><span data-ttu-id="e262d-102">'Optional' が必要です。</span><span class="sxs-lookup"><span data-stu-id="e262d-102">'Optional' expected</span></span>
<span data-ttu-id="e262d-103">プロシージャ宣言内の省略可能な引数の後に必須の引数があります。</span><span class="sxs-lookup"><span data-stu-id="e262d-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="e262d-104">省略可能な引数の後の引数もすべて、省略可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e262d-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="e262d-105">**エラー ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="e262d-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e262d-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e262d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="e262d-107">引数が必須と想定される場合は、引数リストの最初の省略可能な引数の前に移動します。</span><span class="sxs-lookup"><span data-stu-id="e262d-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="e262d-108">引数が省略可能と想定される場合は、`Optional` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e262d-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e262d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e262d-109">See also</span></span>

- [<span data-ttu-id="e262d-110">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="e262d-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
