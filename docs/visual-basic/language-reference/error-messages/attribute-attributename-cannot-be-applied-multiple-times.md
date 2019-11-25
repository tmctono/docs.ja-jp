---
title: 属性 '<attributename>' を複数回適用することはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968226"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="2e891-102">属性 '\<attributename > ' を複数回適用することはできません</span><span class="sxs-lookup"><span data-stu-id="2e891-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="2e891-103">属性を適用できるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="2e891-103">The attribute can only be applied once.</span></span> <span data-ttu-id="2e891-104">`AttributeUsage` 属性は、属性を複数回適用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2e891-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="2e891-105">**エラー ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="2e891-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e891-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2e891-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2e891-107">属性が適用されるのは一度だけであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e891-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="2e891-108">開発したカスタム属性を使用している場合は、次の例のように、複数の属性の使用を許可するように `AttributeUsage` 属性を変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2e891-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e891-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e891-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="2e891-110">カスタム属性の作成</span><span class="sxs-lookup"><span data-stu-id="2e891-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="2e891-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="2e891-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
