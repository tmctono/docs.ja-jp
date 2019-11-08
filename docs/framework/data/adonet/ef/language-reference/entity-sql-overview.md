---
title: Entity SQL の概要
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: e0f154ab2d9db1a1fdbaba8c72bc7e43ad71ee0b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738491"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="608f7-102">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="608f7-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="608f7-103">は、Entity Framework 内の概念モデルに対してクエリを実行できるようにする SQL に似た言語です。</span><span class="sxs-lookup"><span data-stu-id="608f7-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="608f7-104">概念モデルは、データをエンティティおよびリレーションシップとして表します。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] を使用すると、SQL を使用したユーザーにとって使い慣れた形式で、それらのエンティティやリレーションシップを照会できます。</span><span class="sxs-lookup"><span data-stu-id="608f7-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
      
 <span data-ttu-id="608f7-105">Entity Framework は、ストレージ固有のデータプロバイダーと連携して、汎用 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] をストレージ固有のクエリに変換します。</span><span class="sxs-lookup"><span data-stu-id="608f7-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="608f7-106">EntityClient プロバイダーには、エンティティ モデルに対して [!INCLUDE[esql](../../../../../../includes/esql-md.md)] コマンドを実行し、スカラー結果、結果セット、オブジェクト グラフなど、さまざまなデータ型を返すための手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="608f7-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="608f7-107"><xref:System.Data.EntityClient.EntityCommand> オブジェクトを構築する場合は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のクエリ文字列を <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> プロパティに割り当てることで、ストアド プロシージャの名前またはクエリのテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="608f7-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="608f7-108">EDM に対する <xref:System.Data.EntityClient.EntityDataReader> の実行結果は、<xref:System.Data.EntityClient.EntityCommand> によって公開されます。</span><span class="sxs-lookup"><span data-stu-id="608f7-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="608f7-109"><xref:System.Data.EntityClient.EntityDataReader> を返すコマンドを実行するには、<xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="608f7-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="608f7-110">EntityClient プロバイダーに加えて、Entity Framework を使用すると、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] を使用して概念モデルに対するクエリを実行し、エンティティ型のインスタンスである厳密に型指定された CLR オブジェクトとしてデータを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="608f7-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="608f7-111">詳細については、「[オブジェクトの操作](../working-with-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="608f7-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="608f7-112">ここでは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="608f7-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="608f7-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="608f7-113">In This Section</span></span>  
 [<span data-ttu-id="608f7-114">Entity SQL と Transact-SQL の相違点</span><span class="sxs-lookup"><span data-stu-id="608f7-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="608f7-115">Entity SQL クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="608f7-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="608f7-116">型システム</span><span class="sxs-lookup"><span data-stu-id="608f7-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="608f7-117">型定義</span><span class="sxs-lookup"><span data-stu-id="608f7-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="608f7-118">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="608f7-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="608f7-119">クエリ プランのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="608f7-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="608f7-120">名前空間</span><span class="sxs-lookup"><span data-stu-id="608f7-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="608f7-121">識別子</span><span class="sxs-lookup"><span data-stu-id="608f7-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="608f7-122">パラメーター</span><span class="sxs-lookup"><span data-stu-id="608f7-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="608f7-123">変数</span><span class="sxs-lookup"><span data-stu-id="608f7-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="608f7-124">サポートされていない式</span><span class="sxs-lookup"><span data-stu-id="608f7-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="608f7-125">リテラル</span><span class="sxs-lookup"><span data-stu-id="608f7-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="608f7-126">NULL リテラルと型推論</span><span class="sxs-lookup"><span data-stu-id="608f7-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="608f7-127">入力文字セット</span><span class="sxs-lookup"><span data-stu-id="608f7-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="608f7-128">クエリ式</span><span class="sxs-lookup"><span data-stu-id="608f7-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="608f7-129">関数</span><span class="sxs-lookup"><span data-stu-id="608f7-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="608f7-130">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="608f7-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="608f7-131">ページング</span><span class="sxs-lookup"><span data-stu-id="608f7-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="608f7-132">比較セマンティクス</span><span class="sxs-lookup"><span data-stu-id="608f7-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="608f7-133">入れ子になった Entity SQL クエリの作成</span><span class="sxs-lookup"><span data-stu-id="608f7-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="608f7-134">NULL 値が許容される構造化型</span><span class="sxs-lookup"><span data-stu-id="608f7-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="608f7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="608f7-135">See also</span></span>

- [<span data-ttu-id="608f7-136">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="608f7-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="608f7-137">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="608f7-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="608f7-138">CSDL、SSDL、および MSL 仕様</span><span class="sxs-lookup"><span data-stu-id="608f7-138">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
