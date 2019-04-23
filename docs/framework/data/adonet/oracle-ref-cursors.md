---
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: b23b0f07d7755fed820481a3ad1fe831ae3f5224
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213169"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="06f6c-102">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="06f6c-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="06f6c-103">.NET Framework Data Provider for Oracle のサポート、Oracle **REF CURSOR**データ型。</span><span class="sxs-lookup"><span data-stu-id="06f6c-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="06f6c-104">データ プロバイダーを使用して Oracle REF CURSOR を操作するときは、次の動作を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06f6c-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06f6c-105">動作の中には、Microsoft OLE DB Provider for Oracle (MSDAORA) の動作と異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="06f6c-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
-   <span data-ttu-id="06f6c-106">パフォーマンス上の理由から、Data Provider for Oracle は自動的にバインドしない**REF CURSOR**データ型は、MSDAORA よう、明示的に指定する場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
-   <span data-ttu-id="06f6c-107">データ プロバイダーでは、REF CURSOR パラメーターの指定に使用する {resultset} エスケープのような、ODBC エスケープ シーケンスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06f6c-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="06f6c-108">REF Cursor を返すストアド プロシージャを実行するにパラメーターを定義する必要があります、<xref:System.Data.OracleClient.OracleParameterCollection>で、<xref:System.Data.OracleClient.OracleType>の**カーソル**と<xref:System.Data.OracleClient.OracleParameter.Direction%2A>の**出力**します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="06f6c-109">データ プロバイダーでは、REF CURSOR のバインドは出力パラメーターとしてのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06f6c-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="06f6c-110">プロバイダーは、入力パラメーターとしての REF CURSOR はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="06f6c-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
-   <span data-ttu-id="06f6c-111">パラメーター値からの <xref:System.Data.OracleClient.OracleDataReader> の取得はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06f6c-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="06f6c-112">値は、コマンドを実行すると <xref:System.DBNull> 型になります。</span><span class="sxs-lookup"><span data-stu-id="06f6c-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
-   <span data-ttu-id="06f6c-113">唯一**CommandBehavior**の REF Cursor で動作する列挙値 (を呼び出すときに、たとえば、 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) は**CloseConnection**; 他のすべてのユーザーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="06f6c-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
-   <span data-ttu-id="06f6c-114">内の REF Cursor の順序、 **OracleDataReader**内のパラメーターの順序によっては、 **OracleParameterCollection**します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="06f6c-115"><xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> プロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="06f6c-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
-   <span data-ttu-id="06f6c-116">PL/SQL**テーブル**データ型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06f6c-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="06f6c-117">ただし、REF CURSOR は、さらに効果的です。</span><span class="sxs-lookup"><span data-stu-id="06f6c-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="06f6c-118">使用する場合、**テーブル**MSDAORA で OLE DB .NET データ プロバイダーを使用して、データ型します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06f6c-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="06f6c-119">In This Section</span></span>  
 [<span data-ttu-id="06f6c-120">REF CURSOR の例</span><span class="sxs-lookup"><span data-stu-id="06f6c-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="06f6c-121">次の 3 つの例を使って REF CURSOR の使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="06f6c-122">OracleDataReader の REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="06f6c-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="06f6c-123">REF CURSOR パラメーターを返しして値を読み取る PL/SQL ストアド プロシージャを実行する方法を示します、 **OracleDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="06f6c-124">OracleDataReader を使用した複数の REF CURSOR からのデータの取得</span><span class="sxs-lookup"><span data-stu-id="06f6c-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="06f6c-125">2 つの REF CURSOR パラメーターを返しを使用して値を読み取る PL/SQL ストアド プロシージャを実行する方法を示します、 **OracleDataReader**します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="06f6c-126">1 つまたは複数の REF CURSOR を使用した DataSet の値の設定</span><span class="sxs-lookup"><span data-stu-id="06f6c-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="06f6c-127">2 つの REF CURSOR パラメーターを返し、返された行を <xref:System.Data.DataSet> に入力する、PL/SQL ストアド プロシージャを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06f6c-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f6c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="06f6c-128">See also</span></span>

- [<span data-ttu-id="06f6c-129">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="06f6c-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="06f6c-130">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="06f6c-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
