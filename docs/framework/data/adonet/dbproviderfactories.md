---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208816"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="c7a40-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="c7a40-102">DbProviderFactories</span></span>
<span data-ttu-id="c7a40-103"><xref:System.Data.Common> 名前空間には、特定のデータ ソースを使用するための <xref:System.Data.Common.DbProviderFactory> インスタンスを作成するクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c7a40-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="c7a40-104"><xref:System.Data.Common.DbProviderFactory> インスタンスを作成し、データ プロバイダーに関する情報をそのインスタンスに渡すと、`DbProviderFactory` はあらかじめ提供された情報に基づいて厳密に型指定された正しいオブジェクトを判断して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c7a40-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="c7a40-105">.NET Framework バージョン 4 以降では、<xref:System.Data.Odbc>、<xref:System.Data.OleDb>、<xref:System.Data.SqlClient>、および <xref:System.Data.OracleClient> などのデータ プロバイダーは machine.config ファイルに表示されなくなりますが、カスタム プロバイダーは表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a40-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7a40-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c7a40-106">In This Section</span></span>  
 [<span data-ttu-id="c7a40-107">ファクトリ モデルの概要</span><span class="sxs-lookup"><span data-stu-id="c7a40-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="c7a40-108">ファクトリ デザイン パターンとプログラミング インターフェイスの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c7a40-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="c7a40-109">DbProviderFactory の取得</span><span class="sxs-lookup"><span data-stu-id="c7a40-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="c7a40-110">インストールされているデータ プロバイダーの一覧を取得したり、<xref:System.Data.Common.DbConnection> から `DbProviderFactory` を作成したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7a40-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="c7a40-111">DbConnection、DbCommand、および DbException</span><span class="sxs-lookup"><span data-stu-id="c7a40-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="c7a40-112"><xref:System.Data.Common.DbCommand> と <xref:System.Data.Common.DbDataReader> の作成方法のほか、<xref:System.Data.Common.DbException> を使ったデータ エラーの処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7a40-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="c7a40-113">DbDataAdapter を使用したデータの変更</span><span class="sxs-lookup"><span data-stu-id="c7a40-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="c7a40-114"><xref:System.Data.Common.DbCommandBuilder> と <xref:System.Data.Common.DbDataAdapter> を使用して、データを取得したり変更したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7a40-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a40-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7a40-115">See also</span></span>

- [<span data-ttu-id="c7a40-116">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="c7a40-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="c7a40-117">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c7a40-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
