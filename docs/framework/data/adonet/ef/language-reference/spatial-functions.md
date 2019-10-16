---
title: 空間関数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319299"
---
# <a name="spatial-functions"></a><span data-ttu-id="db0c5-102">空間関数</span><span class="sxs-lookup"><span data-stu-id="db0c5-102">Spatial Functions</span></span>
<span data-ttu-id="db0c5-103">空間型のリテラル形式はありません。</span><span class="sxs-lookup"><span data-stu-id="db0c5-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="db0c5-104">ただし、Well-Known Text 形式の文字列を使用して呼び出す正規の Entity Framework 関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db0c5-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="db0c5-105">たとえば、次の関数呼び出しでは、ジオメトリ ポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="db0c5-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="db0c5-106">@No__t 0 のメソッドには、すべての空間正規 Entity Framework メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="db0c5-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="db0c5-107">目的のメソッドをクリックすると、関数に渡す必要のあるパラメーターを確認できます。</span><span class="sxs-lookup"><span data-stu-id="db0c5-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
