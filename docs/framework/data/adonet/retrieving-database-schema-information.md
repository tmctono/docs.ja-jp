---
title: データベース スキーマ情報の取得
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782729"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="34d4d-102">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="34d4d-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="34d4d-103">データベースからのスキーマ情報の取得は、スキーマの検出プロセスによって行われます。</span><span class="sxs-lookup"><span data-stu-id="34d4d-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="34d4d-104">スキーマ検出を使用すると、アプリケーションは、特定のデータベースのデータベーススキーマ (*メタデータ*とも呼ばれます) に関する情報を検索して返すように要求できます。</span><span class="sxs-lookup"><span data-stu-id="34d4d-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="34d4d-105">テーブル、列、ストアド プロシージャなどの各種のデータベース スキーマ要素は、スキーマ コレクションを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="34d4d-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="34d4d-106">各スキーマ コレクションには、使用されているプロバイダーに固有の各種のスキーマ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34d4d-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="34d4d-107">各 .NET Framework マネージプロバイダーは、 **Connection**クラスに**getschema**メソッドを実装します。また、 **getschema**メソッドから返されるスキーマ情報は、 <xref:System.Data.DataTable>の形式になります。</span><span class="sxs-lookup"><span data-stu-id="34d4d-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="34d4d-108">**GetSchema**メソッドは、返されるスキーマコレクションを指定し、返される情報量を制限するためのオプションのパラメーターを提供する、オーバーロードされたメソッドです。</span><span class="sxs-lookup"><span data-stu-id="34d4d-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="34d4d-109">OLE DB、ODBC、Oracle、および SqlClient の .NET Framework データプロバイダーには、 **DataReader**の列メタデータを記述する DataTable を返す**getschematable**メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="34d4d-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="34d4d-110">.NET Framework Data Provider for OLE DB では、<xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> オブジェクトの <xref:System.Data.OleDb.OleDbConnection> メソッドを使ってスキーマ情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="34d4d-111">引数として、 **getoledbschematable**は、 <xref:System.Data.OleDb.OleDbSchemaGuid>返されるスキーマ情報を識別するを受け取り、返された列に対する制限の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="34d4d-112">**Getoledbschematable**は、 <xref:System.Data.DataTable>要求されたスキーマ情報を格納したを返します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34d4d-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="34d4d-113">In This Section</span></span>  
 [<span data-ttu-id="34d4d-114">GetSchema およびスキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="34d4d-115">**GetSchema**メソッドと、それを使用してデータベースからスキーマ情報を取得および制限する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="34d4d-116">スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="34d4d-116">Schema Restrictions</span></span>  
 <span data-ttu-id="34d4d-117">**GetSchema**で使用できるスキーマの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="34d4d-118">共通のスキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="34d4d-119">すべての .NET Framework マネージド プロバイダーでサポートされる共通のスキーマ コレクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="34d4d-120">SQL Server スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="34d4d-121">.NET Framework Provider for SQL Server でサポートされるスキーマ コレクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="34d4d-122">Oracle スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="34d4d-123">.NET Framework Provider for Oracle でサポートされるスキーマ コレクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="34d4d-124">ODBC スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="34d4d-125">ODBC ドライバーのスキーマ コレクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="34d4d-126">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="34d4d-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="34d4d-127">OLE DB プロバイダーのスキーマ コレクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="34d4d-128">参照</span><span class="sxs-lookup"><span data-stu-id="34d4d-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="34d4d-129"><xref:System.Data.Common.DbConnection>クラスの**GetSchema**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="34d4d-130"><xref:System.Data.Odbc.OdbcConnection>クラスの**GetSchema**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="34d4d-131"><xref:System.Data.OleDb.OleDbConnection>クラスの**GetSchema**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="34d4d-132"><xref:System.Data.OracleClient.OracleConnection>クラスの**GetSchema**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="34d4d-133"><xref:System.Data.SqlClient.SqlConnection>クラスの**GetSchema**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="34d4d-134"><xref:System.Data.Common.DbDataReader>クラスの**getschematable**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="34d4d-135"><xref:System.Data.Odbc.OdbcDataReader>クラスの**getschematable**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="34d4d-136"><xref:System.Data.OleDb.OleDbDataReader>クラスの**getschematable**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="34d4d-137"><xref:System.Data.OracleClient.OracleDataReader>クラスの**getschematable**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="34d4d-138"><xref:System.Data.SqlClient.SqlDataReader>クラスの**getschematable**メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34d4d-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d4d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="34d4d-139">See also</span></span>

- [<span data-ttu-id="34d4d-140">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="34d4d-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="34d4d-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="34d4d-141">ADO.NET Overview</span></span>](ado-net-overview.md)
