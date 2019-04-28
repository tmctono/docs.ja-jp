---
title: 配列インデックス式が見つかりません。
ms.date: 07/20/2015
f1_keywords:
- bc30306
- vbc30306
helpviewer_keywords:
- BC30306
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
ms.openlocfilehash: 4dadad63f4321e88b79f2006a9e6b7befa27909a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935344"
---
# <a name="array-subscript-expression-missing"></a><span data-ttu-id="51cfb-102">配列インデックス式が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="51cfb-102">Array subscript expression missing</span></span>
<span data-ttu-id="51cfb-103">配列の初期化は、1 つ以上の配列の境界を定義するための添字を残します。</span><span class="sxs-lookup"><span data-stu-id="51cfb-103">An array initialization leaves out one or more of the subscripts that define the array bounds.</span></span> <span data-ttu-id="51cfb-104">たとえば、ステートメントは、式を含めることが`myArray (5,5,,10)`、3 番目の添字をままになります。</span><span class="sxs-lookup"><span data-stu-id="51cfb-104">For example, the statement might contain the expression `myArray (5,5,,10)`, which leaves out the third subscript.</span></span>  
  
 <span data-ttu-id="51cfb-105">**エラー ID:** BC30306</span><span class="sxs-lookup"><span data-stu-id="51cfb-105">**Error ID:** BC30306</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51cfb-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="51cfb-106">To correct this error</span></span>  
  
- <span data-ttu-id="51cfb-107">不足しているインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="51cfb-107">Supply the missing subscript.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51cfb-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="51cfb-108">See also</span></span>

- [<span data-ttu-id="51cfb-109">配列</span><span class="sxs-lookup"><span data-stu-id="51cfb-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
