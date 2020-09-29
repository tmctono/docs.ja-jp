---
title: 空間関数
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7d0979b5166c847244cbeec97acf4fa4f745a259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169584"
---
# <a name="spatial-functions"></a><span data-ttu-id="28dae-102">空間関数</span><span class="sxs-lookup"><span data-stu-id="28dae-102">Spatial Functions</span></span>

<span data-ttu-id="28dae-103">空間型のリテラル形式はありません。</span><span class="sxs-lookup"><span data-stu-id="28dae-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="28dae-104">ただし、Well-Known Text 形式の文字列を使用して呼び出す正規の Entity Framework 関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="28dae-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="28dae-105">たとえば、次の関数呼び出しでは、ジオメトリ ポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="28dae-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="28dae-106"><xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> メソッドには、Entity Framework の空間に関するすべての正規のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="28dae-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="28dae-107">目的のメソッドをクリックすると、関数に渡す必要のあるパラメーターを確認できます。</span><span class="sxs-lookup"><span data-stu-id="28dae-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
