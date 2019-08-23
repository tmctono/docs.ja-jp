---
title: ADO.NET でのデータ型のマッピング
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: ddb3c1c5551336ace66bab53af3beb83b6cd2d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950410"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="11324-102">ADO.NET でのデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="11324-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="11324-103">.NET Framework は共通型システムを基にしています。このシステムは実行時の型の宣言、使用、および管理方法を定義するものです。</span><span class="sxs-lookup"><span data-stu-id="11324-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="11324-104">値型と参照型の両方から構成されており、これらはすべて <xref:System.Object> 基本型から派生します。</span><span class="sxs-lookup"><span data-stu-id="11324-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="11324-105">データ ソースを操作するときは、データ型が明示的に指定されていない場合はデータ プロバイダーから推論されます。</span><span class="sxs-lookup"><span data-stu-id="11324-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="11324-106">たとえば、<xref:System.Data.DataSet> オブジェクトは、特定のデータ ソースには依存しません。</span><span class="sxs-lookup"><span data-stu-id="11324-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="11324-107">`DataSet` 内のデータはデータ ソースから取得され、変更は `DataAdapter` によってデータ ソースに反映されます。</span><span class="sxs-lookup"><span data-stu-id="11324-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="11324-108">これは、がデータ`DataAdapter`ソースの<xref:System.Data.DataTable>値`DataSet`を使用してのに fill を行うときに、内の列の`DataTable`結果として得られるデータ型が、.NET Framework データプロバイダーに固有の型ではなく、.NET Framework 型であることを意味します。は、データソースへの接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="11324-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="11324-109">同様に、が`DataReader`データソースから値を返す場合、結果の値は .NET Framework 型のローカル変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="11324-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="11324-110">の`Fill`操作`DataAdapter` と`Get`のメソッドの両方について、.NETFramework型は.NETFrameworkデータプロバイダーから返された値から推論されます。`DataReader`</span><span class="sxs-lookup"><span data-stu-id="11324-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="11324-111">返される値の型がわかっている場合は、推論されるデータ型を使用するのではなく、`DataReader` の型指定されたアクセサー メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11324-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="11324-112">型指定されたアクセサーメソッドを使用すると、特定の .NET Framework 型として値を返すことで、より優れたパフォーマンスが得られます。これにより、追加の型変換が不要になります。</span><span class="sxs-lookup"><span data-stu-id="11324-112">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11324-113">.NET Framework データプロバイダーのデータ型の Null 値は、 `DBNull.Value`によって表されます。</span><span class="sxs-lookup"><span data-stu-id="11324-113">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11324-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="11324-114">In This Section</span></span>  
 [<span data-ttu-id="11324-115">SQL Server データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="11324-115">SQL Server Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <span data-ttu-id="11324-116">推論されたデータ型マッピングおよび <xref:System.Data.SqlClient> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="11324-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="11324-117">OLE DB データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="11324-117">OLE DB Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <span data-ttu-id="11324-118">推論されたデータ型マッピングおよび <xref:System.Data.OleDb> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="11324-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="11324-119">ODBC データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="11324-119">ODBC Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <span data-ttu-id="11324-120">推論されたデータ型マッピングおよび <xref:System.Data.Odbc> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="11324-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="11324-121">Oracle データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="11324-121">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="11324-122">推論されたデータ型マッピングおよび <xref:System.Data.OracleClient> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="11324-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="11324-123">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="11324-123">Floating-Point Numbers</span></span>](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 <span data-ttu-id="11324-124">開発者が浮動小数点数を扱う際の発生頻度の高い問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="11324-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11324-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="11324-125">See also</span></span>

- [<span data-ttu-id="11324-126">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11324-126">SQL Server Data Types and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="11324-127">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="11324-127">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="11324-128">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="11324-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="11324-129">共通型システム</span><span class="sxs-lookup"><span data-stu-id="11324-129">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="11324-130">[変換 (型を)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="11324-130">[Converting Types](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="11324-131">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="11324-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
