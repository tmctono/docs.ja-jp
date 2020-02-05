---
title: の概要
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: d5dc9cf7081c6876118914a0b95853a5a7ca5e57
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980341"
---
# <a name="adonet-overview"></a><span data-ttu-id="2896b-102">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="2896b-102">ADO.NET Overview</span></span>
<span data-ttu-id="2896b-103">ADO.NET は、SQL Server や XML などのデータ ソースや、OLE DB や ODBC 経由で公開されるデータ ソースに対する一貫性を持ったアクセス機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="2896b-103">ADO.NET provides consistent access to data sources such as SQL Server and XML, and to data sources exposed through OLE DB and ODBC.</span></span> <span data-ttu-id="2896b-104">データを共有する消費者向けアプリケーションで ADO.NET を使用することで、そのようなデータ ソースへの接続や、データ ソースに格納されているデータの取得、操作、更新を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2896b-104">Data-sharing consumer applications can use ADO.NET to connect to these data sources and retrieve, handle, and update the data that they contain.</span></span>  
  
 <span data-ttu-id="2896b-105">ADO.NET は、データ操作の中からデータ アクセス機能を分離し、個別にまたは組み合わせて使用できる、独立したコンポーネントへと分解します。</span><span class="sxs-lookup"><span data-stu-id="2896b-105">ADO.NET separates data access from data manipulation into discrete components that can be used separately or in tandem.</span></span> <span data-ttu-id="2896b-106">ADO.NET には、データベースとの接続、コマンドの実行、および結果の取得を行うための .NET Framework データ プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2896b-106">ADO.NET includes .NET Framework data providers for connecting to a database, executing commands, and retrieving results.</span></span> <span data-ttu-id="2896b-107">この結果は直接処理され、ADO.NET <xref:System.Data.DataSet> オブジェクトに格納されます。この結果は、ユーザーに暫定的に公開したり、複数のソースからのデータと組み合わせたり、層間で受け渡したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2896b-107">Those results are either processed directly, placed in an ADO.NET <xref:System.Data.DataSet> object in order to be exposed to the user in an ad hoc manner, combined with data from multiple sources, or passed between tiers.</span></span> <span data-ttu-id="2896b-108">`DataSet` オブジェクトを .NET Framework データ プロバイダーに関係なく使用した場合でも、アプリケーションにとってローカルなデータや XML から提供されたデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2896b-108">The `DataSet` object can also be used independently of a .NET Framework data provider to manage data local to the application or sourced from XML.</span></span>  
  
 <span data-ttu-id="2896b-109">ADO.NET クラスは System.Data.dll にあり、System.Xml.dll に含まれている XML クラスに統合されています。</span><span class="sxs-lookup"><span data-stu-id="2896b-109">The ADO.NET classes are found in System.Data.dll, and are integrated with the XML classes found in System.Xml.dll.</span></span> <span data-ttu-id="2896b-110">データベースに接続してデータを取得し、そのデータをコンソールウィンドウに表示するサンプルコードについては、「 [ADO.NET コード例](ado-net-code-examples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2896b-110">For sample code that connects to a database, retrieves data from it, and then displays that data in a console window, see [ADO.NET Code Examples](ado-net-code-examples.md).</span></span>  
  
 <span data-ttu-id="2896b-111">マネージド コードを作成する開発者は、ADO.NET により、ネイティブのコンポーネント オブジェクト モデル (COM) 開発者が ActiveX Data Object (ADO) によって利用できる機能と同等の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="2896b-111">ADO.NET provides functionality to developers who write managed code similar to the functionality provided to native component object model (COM) developers by ActiveX Data Objects (ADO).</span></span> <span data-ttu-id="2896b-112">.NET アプリケーションでのデータのアクセスには、ADO ではなく ADO.NET を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2896b-112">We recommend that you use ADO.NET, not ADO, for accessing data in your .NET applications.</span></span>  
  
 <span data-ttu-id="2896b-113">ADO.NET は、.NET Framework におけるデータ アクセスの最も直接的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="2896b-113">ADO.NET provides the most direct method of data access within the .NET Framework.</span></span> <span data-ttu-id="2896b-114">基になるストレージモデルではなく、概念モデルに対するアプリケーションの動作を可能にする高レベルの抽象化については、 [ADO.NET Entity Framework](./ef/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2896b-114">For a higher-level abstraction that allows applications to work against a conceptual model instead of the underlying storage model, see the [ADO.NET Entity Framework](./ef/index.md).</span></span>  
  
 <span data-ttu-id="2896b-115">**プライバシー**に関する声明: System.data.oracleclient、system.data.sqlserverce、System.string、、および system.string の各アセンブリは、ユーザーのプライベートデータと非プライベートデータを区別しません。Dll、、および system.string の各アセンブリは、ユーザーのプライベートデータと非プライベートデータを区別しません。</span><span class="sxs-lookup"><span data-stu-id="2896b-115">**Privacy Statement**: The System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll, and System.Data.DataSetExtensions.dll assemblies do not distinguish between a user's private data and non-private data.</span></span>  <span data-ttu-id="2896b-116">これらのアセンブリによって、ユーザーの個人データの収集、格納、送信が実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2896b-116">These assemblies do not collect, store, or transport any user's private data.</span></span> <span data-ttu-id="2896b-117">ただし、サードパーティ製のアプリケーションでこれらのアセンブリが使用され、ユーザーの個人データの収集、格納、送信が行われる可能性はあります。</span><span class="sxs-lookup"><span data-stu-id="2896b-117">However, third-party applications might collect, store, or transport a user's private data using these assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2896b-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2896b-118">In This Section</span></span>  
 [<span data-ttu-id="2896b-119">ADO.NET のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2896b-119">ADO.NET Architecture</span></span>](ado-net-architecture.md)  
 <span data-ttu-id="2896b-120">ADO.NET のアーキテクチャとコンポーネントの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-120">Provides an overview of the architecture and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="2896b-121">ADO.NET テクノロジのオプションとガイドライン</span><span class="sxs-lookup"><span data-stu-id="2896b-121">ADO.NET Technology Options and Guidelines</span></span>](ado-net-technology-options-and-guidelines.md)  
 <span data-ttu-id="2896b-122">エンティティ データ プラットフォームに含まれている製品とテクノロジを説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-122">Describes the products and technologies included with the Entity Data Platform.</span></span>  
  
 [<span data-ttu-id="2896b-123">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2896b-123">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)  
 <span data-ttu-id="2896b-124">ADO.NET での統合言語クエリ (LINQ) の実装方法を説明し、関連項目へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="2896b-124">Describes how Language-Integrated Query (LINQ) is implemented in ADO.NET and provides links to relevant topics.</span></span>  
  
 [<span data-ttu-id="2896b-125">.NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="2896b-125">.NET Framework Data Providers</span></span>](data-providers.md)  
 <span data-ttu-id="2896b-126">.NET Framework データ プロバイダーと、ADO.NET に同梱される .NET Framework データ プロバイダーのデザインの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-126">Provides an overview of the design of the .NET Framework data provider and of the .NET Framework data providers that are included with ADO.NET.</span></span>  
  
 [<span data-ttu-id="2896b-127">ADO.NET データセット</span><span class="sxs-lookup"><span data-stu-id="2896b-127">ADO.NET DataSets</span></span>](ado-net-datasets.md)  
 <span data-ttu-id="2896b-128">`DataSet` のデザインとコンポーネントの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-128">Provides an overview of the `DataSet` design and components.</span></span>  
  
 [<span data-ttu-id="2896b-129">ADO.NET での side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="2896b-129">Side-by-Side Execution in ADO.NET</span></span>](side-by-side-execution.md)  
 <span data-ttu-id="2896b-130">ADO.NET のバージョン間の相違と、その相違が side-by-side 実行とアプリケーションの互換性に及ぼす影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-130">Discusses differences in ADO.NET versions and their effect on side-by-side execution and application compatibility.</span></span>  
  
 [<span data-ttu-id="2896b-131">ADO.NET のコード例</span><span class="sxs-lookup"><span data-stu-id="2896b-131">ADO.NET Code Examples</span></span>](ado-net-code-examples.md)  
 <span data-ttu-id="2896b-132">ADO.NET データ プロバイダーを使用してデータを取得するコード サンプルです。</span><span class="sxs-lookup"><span data-stu-id="2896b-132">Provides code samples that retrieve data using the ADO.NET data providers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2896b-133">関連セクション</span><span class="sxs-lookup"><span data-stu-id="2896b-133">Related Sections</span></span>  
 [<span data-ttu-id="2896b-134">ADO.NET の新機能</span><span class="sxs-lookup"><span data-stu-id="2896b-134">What's New in ADO.NET</span></span>](whats-new.md)  
 <span data-ttu-id="2896b-135">ADO.NET の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-135">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="2896b-136">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="2896b-136">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="2896b-137">ADO.NET を使用する場合の安全なコーディング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-137">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="2896b-138">ADO.NET でのデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="2896b-138">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)  
 <span data-ttu-id="2896b-139">.NET Framework データ型と .NET Framework データ プロバイダーとの間のデータ型のマッピングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-139">Describes data type mappings between .NET Framework data types and the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="2896b-140">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="2896b-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="2896b-141">データ ソースへの接続、データの取得、データの変更の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2896b-141">Describes how to connect to a data source, retrieve data, and modify data.</span></span> <span data-ttu-id="2896b-142">これには、`DataReaders` と `DataAdapters` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2896b-142">This includes `DataReaders` and `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2896b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="2896b-143">See also</span></span>

- [<span data-ttu-id="2896b-144">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2896b-144">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="2896b-145">Visual Studio でのデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="2896b-145">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
