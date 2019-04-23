---
title: パラメーター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187675"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="0e35c-102">パラメーター (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0e35c-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="0e35c-103">パラメーターは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の外部で定義される変数です。通常は、ホスト言語で使用されるバインド API を通じて定義されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="0e35c-104">それぞれのパラメーターには、名前と型があります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="0e35c-105">パラメーター名が使用してクエリ式で定義されているので (@) 記号をプレフィックスとして。</span><span class="sxs-lookup"><span data-stu-id="0e35c-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="0e35c-106">これにより、クエリ内で定義されている他の名前 (プロパティ名など) と明確に区別されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="0e35c-107">パラメーターをバインドするための API は、ホスト言語によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e35c-108">例</span><span class="sxs-lookup"><span data-stu-id="0e35c-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e35c-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e35c-109">See also</span></span>

- [<span data-ttu-id="0e35c-110">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0e35c-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0e35c-111">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="0e35c-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
