---
title: SQL Server データ型と ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155459"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="4c2f9-102">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c2f9-102">SQL Server Data Types and ADO.NET</span></span>

<span data-ttu-id="4c2f9-103">SQL Server と .NET Framework は異なる型システムに基づいているので、両者間でデータ損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="4c2f9-104">データの整合性を維持するために、.NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) では、SQL Server データを処理するための型指定されたアクセサー メソッドが提供されています。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="4c2f9-105"><xref:System.Data.SqlDbType> クラスの列挙値を使用して、<xref:System.Data.SqlClient.SqlParameter> データ型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="4c2f9-106">SQL Server と .NET Framework の間のデータ型マッピングがわかる詳細な説明と表については、「[SQL Server データ型のマッピング](../sql-server-data-type-mappings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="4c2f9-107">SQL Server 2008 では、業務上のニーズに対応して、日時データ、構造化データ、半構造化データ、および非構造化データを扱うための新しいデータ型が導入されました。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="4c2f9-108">新しいデータ型は、SQL Server 2008 オンライン ブックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="4c2f9-109">アプリケーションで使用可能な SQL Server のデータ型は、使用する SQL Server のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="4c2f9-110">詳細については、次の表にある各バージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="4c2f9-111">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="4c2f9-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="4c2f9-112">データ型 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4c2f9-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="4c2f9-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c2f9-113">In This Section</span></span>  

 [<span data-ttu-id="4c2f9-114">SqlTypes と DataSet</span><span class="sxs-lookup"><span data-stu-id="4c2f9-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="4c2f9-115">`SqlTypes` 内の `DataSet` に対する型のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="4c2f9-116">null 値の処理</span><span class="sxs-lookup"><span data-stu-id="4c2f9-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="4c2f9-117">null 値と 3 値ロジックの使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="4c2f9-118">GUID と uniqueidentifier 値の比較</span><span class="sxs-lookup"><span data-stu-id="4c2f9-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="4c2f9-119">SQL Server と .NET Framework での GUID および uniqueidentifier 値の使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="4c2f9-120">日付と時刻のデータ</span><span class="sxs-lookup"><span data-stu-id="4c2f9-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="4c2f9-121">SQL Server 2008 で導入された新しい日付と時刻のデータ型の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4c2f9-122">大きな UDT</span><span class="sxs-lookup"><span data-stu-id="4c2f9-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="4c2f9-123">SQL Server 2008 で導入された大きな値の UDT からデータを取り出す方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="4c2f9-124">SQL Server における XML データ</span><span class="sxs-lookup"><span data-stu-id="4c2f9-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="4c2f9-125">SQL Server から取得した XML データを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c2f9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c2f9-126">Reference</span></span>  

 <xref:System.Data.DataSet>  
 <span data-ttu-id="4c2f9-127">`DataSet` クラスおよびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="4c2f9-128">`SqlTypes` 名前空間およびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="4c2f9-129">`SqlDbType` 列挙体およびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="4c2f9-130">`DbType` 列挙型およびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2f9-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2f9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c2f9-131">See also</span></span>

- [<span data-ttu-id="4c2f9-132">SQL Server データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="4c2f9-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="4c2f9-133">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="4c2f9-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="4c2f9-134">テーブル値パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c2f9-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="4c2f9-135">SQL Server のバイナリ データと大きな値のデータ</span><span class="sxs-lookup"><span data-stu-id="4c2f9-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="4c2f9-136">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="4c2f9-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
