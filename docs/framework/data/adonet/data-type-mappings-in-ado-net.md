---
title: データ型のマップ
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 610cdc1a679b0c51125075076120e12db97da421
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980198"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="6ee3f-102">ADO.NET でのデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ee3f-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="6ee3f-103">.NET Framework は共通型システムを基にしています。このシステムは実行時の型の宣言、使用、および管理方法を定義するものです。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="6ee3f-104">値型と参照型の両方から構成されており、これらはすべて <xref:System.Object> 基本型から派生します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="6ee3f-105">データ ソースを操作するときは、データ型が明示的に指定されていない場合はデータ プロバイダーから推論されます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="6ee3f-106">たとえば、<xref:System.Data.DataSet> オブジェクトは、特定のデータ ソースには依存しません。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="6ee3f-107">`DataSet` 内のデータはデータ ソースから取得され、変更は `DataAdapter` によってデータ ソースに反映されます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="6ee3f-108">つまり、`DataAdapter` が `DataSet` 内の <xref:System.Data.DataTable> にデータソースの値を格納する場合、`DataTable` 内の列の結果のデータ型は、データソースへの接続に使用される .NET Framework データプロバイダーに固有の型ではなく、.NET Framework 型になります。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="6ee3f-109">同様に、`DataReader` がデータソースから値を返す場合、結果の値は .NET Framework 型のローカル変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="6ee3f-110">`DataAdapter` の `Fill` 操作と `DataReader`の `Get` メソッドの両方について、.NET Framework 型は .NET Framework データプロバイダーから返された値から推論されます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="6ee3f-111">返される値の型がわかっている場合は、推論されるデータ型を使用するのではなく、`DataReader` の型指定されたアクセサー メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="6ee3f-112">型指定されたアクセサーメソッドを使用すると、特定の .NET Framework 型として値を返すことで、より優れたパフォーマンスが得られます。これにより、追加の型変換が不要になります。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-112">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ee3f-113">.NET Framework データプロバイダーのデータ型の Null 値は `DBNull.Value`によって表されます。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-113">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ee3f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ee3f-114">In This Section</span></span>  
 [<span data-ttu-id="6ee3f-115">SQL Server データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ee3f-115">SQL Server Data Type Mappings</span></span>](sql-server-data-type-mappings.md)  
 <span data-ttu-id="6ee3f-116">推論されたデータ型マッピングおよび <xref:System.Data.SqlClient> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="6ee3f-117">OLE DB データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ee3f-117">OLE DB Data Type Mappings</span></span>](ole-db-data-type-mappings.md)  
 <span data-ttu-id="6ee3f-118">推論されたデータ型マッピングおよび <xref:System.Data.OleDb> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="6ee3f-119">ODBC データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ee3f-119">ODBC Data Type Mappings</span></span>](odbc-data-type-mappings.md)  
 <span data-ttu-id="6ee3f-120">推論されたデータ型マッピングおよび <xref:System.Data.Odbc> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="6ee3f-121">Oracle データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ee3f-121">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="6ee3f-122">推論されたデータ型マッピングおよび <xref:System.Data.OracleClient> のデータ アクセサー メソッドを一覧で示します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="6ee3f-123">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="6ee3f-123">Floating-Point Numbers</span></span>](floating-point-numbers.md)  
 <span data-ttu-id="6ee3f-124">開発者が浮動小数点数を扱う際の発生頻度の高い問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ee3f-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee3f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ee3f-125">See also</span></span>

- [<span data-ttu-id="6ee3f-126">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ee3f-126">SQL Server Data Types and ADO.NET</span></span>](./sql/sql-server-data-types.md)
- [<span data-ttu-id="6ee3f-127">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="6ee3f-127">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="6ee3f-128">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="6ee3f-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="6ee3f-129">共通型システム</span><span class="sxs-lookup"><span data-stu-id="6ee3f-129">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="6ee3f-130">[変換 (型を)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6ee3f-130">[Converting Types](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="6ee3f-131">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6ee3f-131">ADO.NET Overview</span></span>](ado-net-overview.md)
