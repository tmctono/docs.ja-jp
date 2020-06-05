---
title: "上位変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '<methodname>' はありません:  <list>"
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall_WideningConversion2
ms.assetid: 5e74f5cf-80bd-4b48-b58a-465f981ec694
ms.openlocfilehash: ed28e6c2f8336ff47bfae4021038f71bc7693c97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376600"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-widening-conversion-list"></a><span data-ttu-id="a31f7-102">上位変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '\<methodname>' はありません: \<list></span><span class="sxs-lookup"><span data-stu-id="a31f7-102">No accessible overloaded '\<methodname>' can be called with these arguments without a widening conversion: \<list></span></span>
<span data-ttu-id="a31f7-103">オーバーロードされたメソッドが呼び出されましたが、拡大変換せずに指定された引数のリストと一致するメソッドはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="a31f7-103">An overloaded method was called, but no method could be matched with the list of provided arguments without a widening conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a31f7-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a31f7-104">To correct this error</span></span>  
  
- <span data-ttu-id="a31f7-105">`Option Strict Off` を指定します。</span><span class="sxs-lookup"><span data-stu-id="a31f7-105">Specify `Option Strict Off`.</span></span>  
  
- <span data-ttu-id="a31f7-106">オーバーロードされたメソッドのシグネチャのいずれかと一致するように、引数を変更します。</span><span class="sxs-lookup"><span data-stu-id="a31f7-106">Change the arguments to match one of the signatures of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31f7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="a31f7-107">See also</span></span>

- [<span data-ttu-id="a31f7-108">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="a31f7-108">Widening and Narrowing Conversions</span></span>](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a31f7-109">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="a31f7-109">Option Strict Statement</span></span>](../language-reference/statements/option-strict-statement.md)
