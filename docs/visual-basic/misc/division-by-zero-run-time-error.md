---
title: 0 による除算 (Visual Basic 実行時エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
ms.openlocfilehash: 194dcebe40b7f14ba4bf4ebce6f2b1294d3e6791
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336335"
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="b382f-102">0 による除算 (Visual Basic 実行時エラー)</span><span class="sxs-lookup"><span data-stu-id="b382f-102">Division by zero (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="b382f-103">除数として使用する式の値が 0 です。</span><span class="sxs-lookup"><span data-stu-id="b382f-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b382f-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b382f-104">To correct this error</span></span>  
  
1. <span data-ttu-id="b382f-105">式の変数のスペルを確認します。</span><span class="sxs-lookup"><span data-stu-id="b382f-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="b382f-106">変数名のスペルが間違っていると、0 に初期化される数値型の変数が暗黙的に生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b382f-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2. <span data-ttu-id="b382f-107">式の変数 (特に、他のプロシージャから引数としてプロシージャに渡されたもの) に対してこれまで実行した操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="b382f-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b382f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="b382f-108">See also</span></span>

- [<span data-ttu-id="b382f-109">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="b382f-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
