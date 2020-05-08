---
title: 正規関数
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: f8ca9e2027e82db89e91287fda02d2014d53f325
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854516"
---
# <a name="canonical-functions"></a><span data-ttu-id="b9044-102">正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-102">Canonical Functions</span></span>
<span data-ttu-id="b9044-103">このセクションでは、すべてのデータ プロバイダーがサポートし、あらゆるクエリ テクノロジで使用されている正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="b9044-104">正規関数は、プロバイダーが拡張することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9044-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="b9044-105">これらの正規関数は、プロバイダーの対応するデータ ソース機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b9044-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="b9044-106">これによって、全データ ソースに共通する形式で表現される関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b9044-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="b9044-107">これらの正規関数はデータ ソースから独立しているため、正規関数の引数の型と戻り値の型は、概念モデルの型の語句で定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9044-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="b9044-108">ただし、データ ソースの中には概念モデルのすべての型をサポートしていないものもあります。</span><span class="sxs-lookup"><span data-stu-id="b9044-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="b9044-109">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリで正規関数を使用すると、適切な関数がデータ ソースで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b9044-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="b9044-110">すべての正規関数は、NULL が入力された場合の動作と明示的に指定されたエラー状況の両方を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="b9044-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="b9044-111">ストア プロバイダーはその動作に従う必要がありますが、Entity Framework にはこの動作が適用されません。</span><span class="sxs-lookup"><span data-stu-id="b9044-111">Store providers should comply with that behavior, but Entity Framework does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="b9044-112">LINQ のシナリオの場合、Entity Framework に対するクエリでは、基になるデータ ソース内のメソッドへの CLR メソッドのマッピングも行われます。</span><span class="sxs-lookup"><span data-stu-id="b9044-112">For LINQ scenarios, queries against the Entity Framework involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="b9044-113">特定の一連のメソッドが適切にマップされるように、CLR メソッドはデータ ソースに関係なく正規関数にマップされます。</span><span class="sxs-lookup"><span data-stu-id="b9044-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="b9044-114">正規関数の名前空間</span><span class="sxs-lookup"><span data-stu-id="b9044-114">Canonical Functions Namespace</span></span>  
 <span data-ttu-id="b9044-115">正規関数の名前空間は <xref:System.Data.Metadata.Edm> です。</span><span class="sxs-lookup"><span data-stu-id="b9044-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="b9044-116"><xref:System.Data.Metadata.Edm> 名前空間は、自動的にすべてのクエリに含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9044-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="b9044-117">ただし、<xref:System.Data.Metadata.Edm> 名前空間に正規関数と同じ名前の関数を含む別の名前空間がインポートされている場合は、名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9044-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9044-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b9044-118">In This Section</span></span>  
 [<span data-ttu-id="b9044-119">集計正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-119">Aggregate Canonical Functions</span></span>](aggregate-canonical-functions.md)  
 <span data-ttu-id="b9044-120">集計 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-121">数値演算正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-121">Math Canonical Functions</span></span>](math-canonical-functions.md)  
 <span data-ttu-id="b9044-122">数学 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-123">文字列正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-123">String Canonical Functions</span></span>](string-canonical-functions.md)  
 <span data-ttu-id="b9044-124">文字列 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-125">日付と時刻の正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-125">Date and Time Canonical Functions</span></span>](date-and-time-canonical-functions.md)  
 <span data-ttu-id="b9044-126">日付および時刻の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-127">ビット単位の正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-127">Bitwise Canonical Functions</span></span>](bitwise-canonical-functions.md)  
 <span data-ttu-id="b9044-128">ビット単位の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-129">空間関数</span><span class="sxs-lookup"><span data-stu-id="b9044-129">Spatial Functions</span></span>](spatial-functions.md)  
 <span data-ttu-id="b9044-130">空間に関する [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の正規関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="b9044-131">その他の正規関数</span><span class="sxs-lookup"><span data-stu-id="b9044-131">Other Canonical Functions</span></span>](other-canonical-functions.md)  
 <span data-ttu-id="b9044-132">ビット単位、日付/時刻、文字列、数学、または集計に分類されない関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9044-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9044-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9044-133">See also</span></span>

- [<span data-ttu-id="b9044-134">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="b9044-134">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="b9044-135">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="b9044-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b9044-136">概念モデル正規関数と SQL Server 関数とのマッピング</span><span class="sxs-lookup"><span data-stu-id="b9044-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="b9044-137">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="b9044-137">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)
