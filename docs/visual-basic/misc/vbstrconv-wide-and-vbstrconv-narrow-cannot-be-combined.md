---
title: VbStrConv.Wide と VbStrConv.Narrow を組み合わせることはできません
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 7193d1f635ff877ab5d07f03584f19f5ce18138a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059369"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="3d6fb-102">VbStrConv.Wide と VbStrConv.Narrow を組み合わせることはできません</span><span class="sxs-lookup"><span data-stu-id="3d6fb-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>

<span data-ttu-id="3d6fb-103">アプリケーションが `VbStrConv` 列挙型メンバー `Wide` と `Narrow`を結合しようとしていますが、これらは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="3d6fb-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d6fb-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="3d6fb-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3d6fb-105">`VbStrConv.Wide` または `VbStrConv.Narrow`のいずれかを削除します。</span><span class="sxs-lookup"><span data-stu-id="3d6fb-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6fb-106">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="3d6fb-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="3d6fb-107">グローバル化およびローカライズされたアプリの開発</span><span class="sxs-lookup"><span data-stu-id="3d6fb-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
