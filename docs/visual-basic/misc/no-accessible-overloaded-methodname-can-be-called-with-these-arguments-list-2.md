---
title: 縮小変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '<methodname>' はありません <list>
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
ms.openlocfilehash: f824b1250c7cb98aeaf301ef57ee01ec2779215f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376704"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion-list"></a><span data-ttu-id="1f219-102">縮小変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '\<methodname>' はありません\<list></span><span class="sxs-lookup"><span data-stu-id="1f219-102">No accessible overloaded '\<methodname>' can be called with these arguments without a narrowing conversion: \<list></span></span>
<span data-ttu-id="1f219-103">オーバーロードされたメソッドが呼び出されましたが、メソッドは縮小変換せずに指定された引数のリストと一致しません。</span><span class="sxs-lookup"><span data-stu-id="1f219-103">An overloaded method was called, but the method cannot be matched with the list of provided arguments without a narrowing conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f219-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1f219-104">To correct this error</span></span>  
  
1. <span data-ttu-id="1f219-105">`Option Strict Off` を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f219-105">Specify `Option Strict Off`.</span></span>
  
2. <span data-ttu-id="1f219-106">オーバーロードされたメソッドのシグネチャと一致するように、引数を変更します。</span><span class="sxs-lookup"><span data-stu-id="1f219-106">Change the arguments to match a signature of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f219-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f219-107">See also</span></span>

- [<span data-ttu-id="1f219-108">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="1f219-108">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="1f219-109">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="1f219-109">Widening and Narrowing Conversions</span></span>](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
