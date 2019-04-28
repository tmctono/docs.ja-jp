---
title: 入れ子になった関数に、デリゲート '<delegatename>' と互換性のあるシグネチャがありません。
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 04eae6d2c6d64e8a0f46ae3c2801a7eb6d893dca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918256"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="92605-102">入れ子になった関数には、デリゲートと互換性のあるシグネチャはありません '\<delegatename >'。</span><span class="sxs-lookup"><span data-stu-id="92605-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="92605-103">ラムダ式は、互換性のないシグネチャを持つデリゲートに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="92605-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="92605-104">たとえば、次のコードでは、委任`Del`は 2 つの整数パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="92605-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="92605-105">1 つの引数があるラムダ式が型として宣言されている場合、エラーが発生した`Del`:</span><span class="sxs-lookup"><span data-stu-id="92605-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="92605-106">**エラー ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="92605-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92605-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="92605-107">To correct this error</span></span>  
  
- <span data-ttu-id="92605-108">シグネチャに互換性があるように、デリゲートの定義または割り当てられているラムダ式のいずれかを調整します。</span><span class="sxs-lookup"><span data-stu-id="92605-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92605-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="92605-109">See also</span></span>

- [<span data-ttu-id="92605-110">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="92605-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="92605-111">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="92605-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
