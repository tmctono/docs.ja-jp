---
title: <methodname>縮小変換せずに、これらの引数と共に呼び出すことができるオーバーロードされたアクセス可能な ' ' はありません
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousMatch_NarrowingConversion1
ms.assetid: 2fdbadb9-8ef1-404a-a2ed-ce5f5e55cfcb
ms.openlocfilehash: 1bfa2b508e7102c6d1a3ea9279819d74d478a640
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077502"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion"></a><span data-ttu-id="8dea7-102">\<methodname>縮小変換せずに、これらの引数と共に呼び出すことができるオーバーロードされたアクセス可能な ' ' はありません</span><span class="sxs-lookup"><span data-stu-id="8dea7-102">No accessible overloaded '\<methodname>' can be called with these arguments without a narrowing conversion</span></span>

<span data-ttu-id="8dea7-103">オーバーロードされたメソッドが呼び出されましたが、縮小変換せずに指定された引数のリストと一致するメソッドはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="8dea7-103">An overloaded method was called, but no method was matched with the list of provided arguments without a narrowing conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dea7-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8dea7-104">To correct this error</span></span>  
  
1. <span data-ttu-id="8dea7-105">`Option Strict Off`を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dea7-105">Specify `Option Strict Off`.</span></span>  
  
2. <span data-ttu-id="8dea7-106">オーバーロードされたメソッドのシグネチャのいずれかと一致するように、引数を変更します。</span><span class="sxs-lookup"><span data-stu-id="8dea7-106">Change the arguments to match one of the signatures of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dea7-107">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="8dea7-107">See also</span></span>

- [<span data-ttu-id="8dea7-108">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="8dea7-108">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="8dea7-109">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="8dea7-109">Widening and Narrowing Conversions</span></span>](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
