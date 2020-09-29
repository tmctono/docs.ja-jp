---
title: サポートされていない機能
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164156"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="4d8fc-102">サポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="4d8fc-102">Unsupported Functionality</span></span>

<span data-ttu-id="4d8fc-103">LINQ to SQL では、次の SQL 機能は、既存の共通言語ランタイム (CLR) および .NET Framework の構成要素の変換からは公開できません。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="4d8fc-104">`LIKE` は直接変換によってサポートされませんが、同様の機能が <xref:System.Data.Linq.SqlClient.SqlMethods> クラスにあります。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="4d8fc-105">詳細については、「<xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="4d8fc-106">LINQ to SQL では、`DATEDIFF` のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="4d8fc-107">同様の機能が <xref:System.Data.Linq.SqlClient.SqlMethods> クラスにあります。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="4d8fc-108">LINQ to SQL では、`ROUND` のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="4d8fc-109">詳細については、「[System.Math メソッド](system-math-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d8fc-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8fc-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d8fc-110">See also</span></span>

- [<span data-ttu-id="4d8fc-111">データ型と関数</span><span class="sxs-lookup"><span data-stu-id="4d8fc-111">Data Types and Functions</span></span>](data-types-and-functions.md)
