---
title: 名前空間 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 395ffb23859be27b4897dfc352f6e44d52286b26
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249991"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="feb27-102">名前空間 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="feb27-102">Namespaces (Entity SQL)</span></span>
<span data-ttu-id="feb27-103">型名、エンティティ セット、関数など、グローバル識別子の名前の競合を防ぐために、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] には名前空間が採用されています。</span><span class="sxs-lookup"><span data-stu-id="feb27-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="feb27-104">で[!INCLUDE[esql](../../../../../../includes/esql-md.md)]の名前空間のサポートは、.NET Framework での名前空間のサポートに似ています。</span><span class="sxs-lookup"><span data-stu-id="feb27-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 <span data-ttu-id="feb27-105">次の例のように、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、2 とおりの形式で USING 句を指定できます。1 つは略称的な別名を指定する修飾名前空間、もう 1 つは別名を指定しない非修飾名前空間です。</span><span class="sxs-lookup"><span data-stu-id="feb27-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="feb27-106">名前解決ルール</span><span class="sxs-lookup"><span data-stu-id="feb27-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="feb27-107">ローカルスコープで識別子を解決できない場合、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]はグローバルスコープ (名前空間) で名前の検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="feb27-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="feb27-108">は、まず識別子 (プレフィックス) と修飾名前空間の 1 つを照合します。</span><span class="sxs-lookup"><span data-stu-id="feb27-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="feb27-109">一致するものがある場合[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 、は、指定された名前空間内の残りの識別子の解決を試みます。</span><span class="sxs-lookup"><span data-stu-id="feb27-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="feb27-110">一致が見つからなかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="feb27-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="feb27-111">次に[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 、は、識別子に対して (プロローグで指定された) すべての非修飾名前空間の検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="feb27-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="feb27-112">その識別子が属している名前空間を一意に特定できた場合は、その場所が返されます。</span><span class="sxs-lookup"><span data-stu-id="feb27-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="feb27-113">同じ識別子に対して複数の名前空間が見つかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="feb27-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="feb27-114">識別子に対して名前空間を識別できない[!INCLUDE[esql](../../../../../../includes/esql-md.md)]場合は、次の例に示すように<xref:System.Data.Common.DbCommand> 、 <xref:System.Data.Common.DbConnection>によって次の外側のスコープ (オブジェクトまたはオブジェクト) に名前が渡されます。</span><span class="sxs-lookup"><span data-stu-id="feb27-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="feb27-115">.NET Framework との違い</span><span class="sxs-lookup"><span data-stu-id="feb27-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="feb27-116">.NET Framework では、部分修飾された名前空間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="feb27-116">In the .NET Framework, you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="feb27-117">では使用できません。</span><span class="sxs-lookup"><span data-stu-id="feb27-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="feb27-118">ADO.NET の使用法</span><span class="sxs-lookup"><span data-stu-id="feb27-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="feb27-119">クエリは、ADO.NET の <xref:System.Data.Common.DbCommand> オブジェクトを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="feb27-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="feb27-120"><xref:System.Data.Common.DbCommand> オブジェクトは、<xref:System.Data.Common.DbConnection> オブジェクトに対して構築できます。</span><span class="sxs-lookup"><span data-stu-id="feb27-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="feb27-121">名前空間を <xref:System.Data.Common.DbCommand> オブジェクトや <xref:System.Data.Common.DbConnection> オブジェクトの一部として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="feb27-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="feb27-122">が[!INCLUDE[esql](../../../../../../includes/esql-md.md)]クエリ自体で識別子を解決できない場合、外部の名前空間は (同様の規則に基づいて) プローブされます。</span><span class="sxs-lookup"><span data-stu-id="feb27-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb27-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="feb27-123">See also</span></span>

- [<span data-ttu-id="feb27-124">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="feb27-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="feb27-125">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="feb27-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
