---
title: 名前空間 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7f05067c4bdb859f3661f775c2502852b6658522
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319554"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="2d237-102">名前空間 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2d237-102">Namespaces (Entity SQL)</span></span>
<span data-ttu-id="2d237-103">型名、エンティティ セット、関数など、グローバル識別子の名前の競合を防ぐために、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] には名前空間が採用されています。</span><span class="sxs-lookup"><span data-stu-id="2d237-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="2d237-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] での名前空間のサポートは、.NET Framework での名前空間のサポートと似ています。</span><span class="sxs-lookup"><span data-stu-id="2d237-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 <span data-ttu-id="2d237-105">次の例のように、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、2 とおりの形式で USING 句を指定できます。1 つは略称的な別名を指定する修飾名前空間、もう 1 つは別名を指定しない非修飾名前空間です。</span><span class="sxs-lookup"><span data-stu-id="2d237-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="2d237-106">名前解決ルール</span><span class="sxs-lookup"><span data-stu-id="2d237-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="2d237-107">識別子がローカル スコープ内で解決できない場合、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ではグローバル スコープ (名前空間) で名前が探索されます。</span><span class="sxs-lookup"><span data-stu-id="2d237-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2d237-108">は、まず識別子 (プレフィックス) と修飾名前空間の 1 つを照合します。</span><span class="sxs-lookup"><span data-stu-id="2d237-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="2d237-109">一致が見つかった場合は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] により、指定された名前空間で、その識別子の残りの部分の解決が試みられます。</span><span class="sxs-lookup"><span data-stu-id="2d237-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="2d237-110">一致が見つからなかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2d237-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="2d237-111">次に、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] により、すべての (プロローグで指定された) 非修飾名前空間で識別子の検索が試みられます。</span><span class="sxs-lookup"><span data-stu-id="2d237-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="2d237-112">その識別子が属している名前空間を一意に特定できた場合は、その場所が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d237-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="2d237-113">同じ識別子に対して複数の名前空間が見つかった場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2d237-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="2d237-114">識別子に対応する名前空間を特定できなかった場合、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、次の例のように、名前が 1 つ外側のスコープ (<xref:System.Data.Common.DbCommand> オブジェクトまたは <xref:System.Data.Common.DbConnection> オブジェクト) に渡されます。</span><span class="sxs-lookup"><span data-stu-id="2d237-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="2d237-115">.NET Framework との違い</span><span class="sxs-lookup"><span data-stu-id="2d237-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="2d237-116">.NET Framework では、部分修飾名前空間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d237-116">In the .NET Framework, you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2d237-117">では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2d237-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="2d237-118">ADO.NET の使用法</span><span class="sxs-lookup"><span data-stu-id="2d237-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="2d237-119">クエリは、ADO.NET の <xref:System.Data.Common.DbCommand> オブジェクトを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="2d237-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="2d237-120"><xref:System.Data.Common.DbCommand> オブジェクトは、<xref:System.Data.Common.DbConnection> オブジェクトに対して構築できます。</span><span class="sxs-lookup"><span data-stu-id="2d237-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="2d237-121">名前空間を <xref:System.Data.Common.DbCommand> オブジェクトや <xref:System.Data.Common.DbConnection> オブジェクトの一部として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d237-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="2d237-122">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] によってクエリ自体の内部で識別子を解決できなかった場合は、同様のルールに従って、外側の名前空間が調査されます。</span><span class="sxs-lookup"><span data-stu-id="2d237-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d237-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d237-123">See also</span></span>

- [<span data-ttu-id="2d237-124">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="2d237-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="2d237-125">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="2d237-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
