---
title: 引数 'Life' を 0 にすることはできません
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_LifeNEZero
ms.assetid: c402da97-a2b2-4219-a83a-0cebbfdffef2
ms.openlocfilehash: 689dc82f76d113e01bd2da9d7531c58df3b1409a
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58038520"
---
# <a name="argument-life-cannot-be-zero"></a><span data-ttu-id="e9de5-102">引数 'Life' を 0 にすることはできません</span><span class="sxs-lookup"><span data-stu-id="e9de5-102">Argument 'Life' cannot be zero</span></span>
<span data-ttu-id="e9de5-103">`Life`の引数が正しくありません。これは、資産の耐用年数を指定する `Double` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9de5-103">An argument for `Life`, which must be a `Double` that specifies the length of useful life of the asset, is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9de5-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e9de5-104">To correct this error</span></span>  
  
-   <span data-ttu-id="e9de5-105">式の引数のスペルを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9de5-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="e9de5-106">変数名のスペルが間違っていると、0 に初期化される数値型の変数が暗黙的に生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9de5-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
-   <span data-ttu-id="e9de5-107">式の変数 (特に、他のプロシージャから引数としてプロシージャに渡されたもの) に対してこれまで実行した操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="e9de5-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9de5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9de5-108">See also</span></span>

- [<span data-ttu-id="e9de5-109">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="e9de5-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
