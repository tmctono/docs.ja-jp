---
title: Entity Framework 用 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: d81499961e7e47bba3b2594ddddd192c87a4a936
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195463"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="ac981-102">Entity Framework 用 SqlClient</span><span class="sxs-lookup"><span data-stu-id="ac981-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="ac981-103">このセクションでは、.NET Framework Data Provider for SQL Server (SqlClient) について説明します。これによって、Microsoft SQL Server 上で Entity Framework が機能できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac981-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="ac981-104">Provider スキーマ属性</span><span class="sxs-lookup"><span data-stu-id="ac981-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="ac981-105">`Provider` は、ストア スキーマ定義言語 (SSDL) の `Schema` 要素の属性です。</span><span class="sxs-lookup"><span data-stu-id="ac981-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="ac981-106">SqlClient を使用するには、文字列 "System.Data.SqlClient" を `Provider` 要素の `Schema` 属性に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac981-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="ac981-107">ProviderManifestToken スキーマ属性</span><span class="sxs-lookup"><span data-stu-id="ac981-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="ac981-108">`ProviderManifestToken` は、SSDL の`Schema` 要素の必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ac981-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="ac981-109">このトークンは、オフライン シナリオ用のプロバイダー マニフェストを読み込むために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac981-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="ac981-110">詳細については`ProviderManifestToken`属性は、「[スキーマ要素 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)します。</span><span class="sxs-lookup"><span data-stu-id="ac981-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="ac981-111">SqlClient は、異なるバージョンの SQL Server 用データ プロバイダーとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac981-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="ac981-112">これらのバージョンでは機能が異なります。</span><span class="sxs-lookup"><span data-stu-id="ac981-112">These versions have different capabilities.</span></span> <span data-ttu-id="ac981-113">たとえば、[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] では、`varchar(max)` で導入された `nvarchar(max)` 型および [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ac981-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="ac981-114">SqlClient は、SQL Server の各バージョンに対応する次のプロバイダー マニフェスト トークンを生成し、受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ac981-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="ac981-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="ac981-115">SQL Server 2000</span></span>|<span data-ttu-id="ac981-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="ac981-116">SQL Server 2005</span></span>|<span data-ttu-id="ac981-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="ac981-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="ac981-118">2000</span><span class="sxs-lookup"><span data-stu-id="ac981-118">2000</span></span>|<span data-ttu-id="ac981-119">2005</span><span class="sxs-lookup"><span data-stu-id="ac981-119">2005</span></span>|<span data-ttu-id="ac981-120">2008</span><span class="sxs-lookup"><span data-stu-id="ac981-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ac981-121">Visual Studio 2010 以降で、 [ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))SQL Server 2000 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ac981-121">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="ac981-122">プロバイダーの名前空間名</span><span class="sxs-lookup"><span data-stu-id="ac981-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="ac981-123">すべてのプロバイダーで名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac981-123">All providers must specify a namespace.</span></span> <span data-ttu-id="ac981-124">このプロパティによって、型や関数など、プロバイダーが特定のコンストラクターに使用するプレフィックスを Entity Framework に通知できます。</span><span class="sxs-lookup"><span data-stu-id="ac981-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="ac981-125">SqlClient プロバイダー マニフェストの名前空間は `SqlServer` です。</span><span class="sxs-lookup"><span data-stu-id="ac981-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="ac981-126">名前空間の詳細については、次を参照してください。[名前空間](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac981-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="ac981-127">種類</span><span class="sxs-lookup"><span data-stu-id="ac981-127">Types</span></span>  
 <span data-ttu-id="ac981-128">Entity Framework 用の SqlClient プロバイダーは、概念モデルの型と SQL Server 型の間のマッピング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac981-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="ac981-129">詳細については、次を参照してください。[エンティティ FrameworkTypes 用 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac981-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="ac981-130">関数</span><span class="sxs-lookup"><span data-stu-id="ac981-130">Functions</span></span>  
 <span data-ttu-id="ac981-131">Entity Framework 用の SqlClient プロバイダーは、プロバイダーがサポートする関数の一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac981-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="ac981-132">サポートされている関数の一覧は、次を参照してください。 [Entity Framework の関数の SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac981-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac981-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ac981-133">In This Section</span></span>  
 [<span data-ttu-id="ac981-134">Entity Framework 用 SqlClient 関数</span><span class="sxs-lookup"><span data-stu-id="ac981-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="ac981-135">Entity Framework 型用 SqlClient</span><span class="sxs-lookup"><span data-stu-id="ac981-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="ac981-136">Entity Framework 用の .NET Framework Data Provider for SQL Server (SqlClient) の既知の問題</span><span class="sxs-lookup"><span data-stu-id="ac981-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac981-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac981-137">See also</span></span>

- [<span data-ttu-id="ac981-138">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="ac981-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="ac981-139">言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ac981-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [<span data-ttu-id="ac981-140">Entity Framework 用 SqlClient プロバイダーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="ac981-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
