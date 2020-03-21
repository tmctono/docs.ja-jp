---
title: 大きな値 (最大) データの変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 00a4ae83270bb74e9703faebfc93e26b5c069478
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174278"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="abbde-102">ADO.NET での大きい値 (max) データの変更</span><span class="sxs-lookup"><span data-stu-id="abbde-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="abbde-103">ラージ オブジェクト (LOB) データ型は、最大行サイズが 8 KB を超えるデータ型です。</span><span class="sxs-lookup"><span data-stu-id="abbde-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="abbde-104">SQL Server からは、`varchar` データ型、`nvarchar` データ型、`varbinary` データ型に `max` 指定子が提供され、2^32 バイトもの大きさの値を格納することができます。</span><span class="sxs-lookup"><span data-stu-id="abbde-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="abbde-105">テーブルの列と Transact-SQL 変数では、`varchar(max)`、`nvarchar(max)`、または `varbinary(max)` データ型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="abbde-106">ADO.NET では、`max` データ型は、`DataReader` によってフェッチすることができ、特殊な処理を行うことなく入力パラメーターと出力パラメーター両方の値として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="abbde-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="abbde-107">大きな `varchar` データ型の場合は、データを段階的に取得および更新できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="abbde-108">Transact-SQL 変数としての比較、および連結に `max` データ型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="abbde-109">このデータ型は、SELECT ステートメントの DISTINCT 句、ORDER BY 句、GROUP BY 句のほか、集約、結合、およびサブクエリでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="abbde-110">次の表は、SQL Server オンライン ブックのドキュメントへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="abbde-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="abbde-111">**SQL サーバーのドキュメント**</span><span class="sxs-lookup"><span data-stu-id="abbde-111">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="abbde-112">[大きな値のデータ型の使用](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="abbde-112">[Using Large-Value Data Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span></span>  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="abbde-113">大きい値型の制限事項</span><span class="sxs-lookup"><span data-stu-id="abbde-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="abbde-114">次の制限は、`max` データ型に適用されますが、これは小さいデータ型に対しては存在しません。</span><span class="sxs-lookup"><span data-stu-id="abbde-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="abbde-115">`sql_variant` に大きな `varchar` データ型を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="abbde-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="abbde-116">大きな `varchar` 列を、インデックスのキー列として指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="abbde-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="abbde-117">この列は、非クラスター化インデックスの付加列で許可されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="abbde-118">大きな `varchar` 列を、パーティション分割キー列として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="abbde-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="abbde-119">Transact-SQL での大きい値型の使用</span><span class="sxs-lookup"><span data-stu-id="abbde-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="abbde-120">Transact-SQL `OPENROWSET` 関数は、リモート データへの 1 回限りの接続およびアクセス方法です。</span><span class="sxs-lookup"><span data-stu-id="abbde-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="abbde-121">この関数には、OLE DB データ ソースからリモート データにアクセスするために必要な、すべての接続情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="abbde-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="abbde-122">`OPENROWSET` は、テーブル名と同じように、クエリの FROM 句で参照できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="abbde-123">OLE DB プロバイダーの機能に従って、INSERT、UPDATE、または DELETE ステートメントのターゲット テーブルとして参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="abbde-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="abbde-124">`OPENROWSET` 関数には `BULK` 行セット プロバイダーが含まれており、これによりデータをターゲット テーブルに読み込むことなく、ファイルから直接読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="abbde-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="abbde-125">これにより、`OPENROWSET` を単純な INSERT SELECT ステートメントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="abbde-126">`OPENROWSET BULK` オプション引数により、データの読み取りの開始位置および終了位置、エラーの処理、データの解釈の制御が大幅に容易になります。</span><span class="sxs-lookup"><span data-stu-id="abbde-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="abbde-127">たとえば、データ ファイルを `varbinary`、`varchar`、`nvarchar` 型の単一行、単一列の行セットとして読み取るように指定できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="abbde-128">完全な構文とオプションについては、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abbde-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="abbde-129">次の例は、写真を、AdventureWorks サンプル データベースの ProductPhoto テーブルに挿入しています。</span><span class="sxs-lookup"><span data-stu-id="abbde-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="abbde-130">`BULK OPENROWSET` プロバイダーを使用する場合は、すべての列に値を挿入しない場合でも、列名を挙げてリストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbde-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="abbde-131">この場合の主キーは ID 列として定義され、列リストから省略できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="abbde-132">また、`OPENROWSET` ステートメントの末尾で相関関係名を指定する必要があることにも注意してください。この例では ThumbnailPhoto です。</span><span class="sxs-lookup"><span data-stu-id="abbde-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="abbde-133">これは、ファイルが読み込まれる先の `ProductPhoto` テーブルの列と関連しています。</span><span class="sxs-lookup"><span data-stu-id="abbde-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,
    ThumbnailPhotoFilePath,
    LargePhoto,
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="abbde-134">UPDATE .WRITE を使用したデータの更新</span><span class="sxs-lookup"><span data-stu-id="abbde-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="abbde-135">Transact-SQL の UPDATE ステートメントには、`varchar(max)` 列、`nvarchar(max)` 列、または `varbinary(max)` 列の内容を変更するための新しい WRITE 構文があります。</span><span class="sxs-lookup"><span data-stu-id="abbde-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="abbde-136">これにより、データを部分的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="abbde-137">ここでは省略形式で UPDATE .WRITE 構文が示されています。</span><span class="sxs-lookup"><span data-stu-id="abbde-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="abbde-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="abbde-138">UPDATE</span></span>  
  
 <span data-ttu-id="abbde-139">{*\<オブジェクト>* }</span><span class="sxs-lookup"><span data-stu-id="abbde-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="abbde-140">SET</span><span class="sxs-lookup"><span data-stu-id="abbde-140">SET</span></span>  
  
 <span data-ttu-id="abbde-141">{ *column_name* = { .WRITE *expression* (@Offset式@Length、 、 、 )</span><span class="sxs-lookup"><span data-stu-id="abbde-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="abbde-142">WRITE メソッドは、*column_name* の値のセクションが変更されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="abbde-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="abbde-143">この式は *column_name* にコピーされる値で、`@Offset` は式が記述される開始位置であり、`@Length` 引数は列のセクションの長さを示します。</span><span class="sxs-lookup"><span data-stu-id="abbde-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="abbde-144">状況</span><span class="sxs-lookup"><span data-stu-id="abbde-144">If</span></span>|<span data-ttu-id="abbde-145">THEN</span><span class="sxs-lookup"><span data-stu-id="abbde-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="abbde-146">式が NULL に設定されています</span><span class="sxs-lookup"><span data-stu-id="abbde-146">The expression is set to NULL</span></span>|<span data-ttu-id="abbde-147">`@Length` は無視され、*column_name* の値は指定された `@Offset` で切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="abbde-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="abbde-148">`@Offset` は NULL です</span><span class="sxs-lookup"><span data-stu-id="abbde-148">`@Offset` is NULL</span></span>|<span data-ttu-id="abbde-149">更新操作によって既存の *column_name* の値の最後に式が追加され、`@Length` が無視されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="abbde-150">`@Offset` が column_name 値の長さを超えています</span><span class="sxs-lookup"><span data-stu-id="abbde-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="abbde-151">SQL Server はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="abbde-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="abbde-152">`@Length` は NULL です</span><span class="sxs-lookup"><span data-stu-id="abbde-152">`@Length` is NULL</span></span>|<span data-ttu-id="abbde-153">更新操作により、`column_name` 値の終わりまですべてのデータが `@Offset` から削除されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="abbde-154">`@Offset` も `@Length` も負の数にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="abbde-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abbde-155">例</span><span class="sxs-lookup"><span data-stu-id="abbde-155">Example</span></span>  
 <span data-ttu-id="abbde-156">この Transact-SQL の例では、AdventureWorks データベースの Document テーブルの `nvarchar(max)` 列である DocumentSummary の部分値を更新します。</span><span class="sxs-lookup"><span data-stu-id="abbde-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="abbde-157">置換する語、既存データ内で置換される語の開始位置 (オフセット)、置換する文字数 (長さ) を指定することにより、"components" という語が、"features" という語で置換されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="abbde-158">この例では、結果を比較するために、UPDATE ステートメントの前後に SELECT ステートメントを挿入します。</span><span class="sxs-lookup"><span data-stu-id="abbde-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="abbde-159">ADO.NET での大きい値型の使用</span><span class="sxs-lookup"><span data-stu-id="abbde-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="abbde-160">大きい値型を ADO.NET で使用するには、大きい値型を <xref:System.Data.SqlClient.SqlDataReader> で <xref:System.Data.SqlClient.SqlParameter> オブジェクトとして指定して結果セットを返すようにするか、<xref:System.Data.SqlClient.SqlDataAdapter> を使用して `DataSet`/`DataTable` に入力します。</span><span class="sxs-lookup"><span data-stu-id="abbde-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="abbde-161">大きな値の型と、それに関連する小さい値のデータ型の操作方法に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="abbde-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="abbde-162">GetSqlBytes を使用したデータ取得</span><span class="sxs-lookup"><span data-stu-id="abbde-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="abbde-163"><xref:System.Data.SqlClient.SqlDataReader> の `GetSqlBytes` メソッドを使用して、`varbinary(max)` 列の内容を取得できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="abbde-164">次のコード フラグメントは、テーブルから `varbinary(max)` データを選択する `cmd` という名前の <xref:System.Data.SqlClient.SqlCommand> オブジェクトと、データを <xref:System.Data.SqlTypes.SqlBytes> として取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="abbde-165">GetSqlChars を使用したデータの取得</span><span class="sxs-lookup"><span data-stu-id="abbde-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="abbde-166"><xref:System.Data.SqlClient.SqlDataReader> の `GetSqlChars` メソッドを使用して、`varchar(max)` 列または `nvarchar(max)` 列の内容を取得できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="abbde-167">次のコード フラグメントは、テーブルから `nvarchar(max)` データを選択する `cmd` という名前の <xref:System.Data.SqlClient.SqlCommand> オブジェクトと、データを取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="abbde-168">GetSqlBinary を使用したデータの取得</span><span class="sxs-lookup"><span data-stu-id="abbde-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="abbde-169"><xref:System.Data.SqlClient.SqlDataReader> の `GetSqlBinary` メソッドを使用して、`varbinary(max)` 列の内容を取得できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="abbde-170">次のコード フラグメントは、テーブルから `varbinary(max)` データを選択する `cmd` という名前の <xref:System.Data.SqlClient.SqlCommand> オブジェクトと、データを <xref:System.Data.SqlTypes.SqlBinary> ストリームとして取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="abbde-171">GetBytes を使用したデータの取得</span><span class="sxs-lookup"><span data-stu-id="abbde-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="abbde-172"><xref:System.Data.SqlClient.SqlDataReader> の `GetBytes` メソッドでは、バイトのストリームを、指定した列オフセットから、指定した配列オフセットから始まるバイト配列に読み取ります。</span><span class="sxs-lookup"><span data-stu-id="abbde-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="abbde-173">次のコード フラグメントは、バイト配列に対するバイトを取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="abbde-174">`GetSqlBytes` とは異なり、`GetBytes` には配列バッファーのサイズを必要とすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="abbde-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="abbde-175">GetValue を使用したデータの取得</span><span class="sxs-lookup"><span data-stu-id="abbde-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="abbde-176"><xref:System.Data.SqlClient.SqlDataReader> の `GetValue` メソッドは、指定した列オフセットから配列に値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="abbde-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="abbde-177">次のコード フラグメントは、最初の列オフセットからバイナリ データを取得した後、2 番目の列オフセットから文字列データを取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="abbde-178">大きい値型から CLR 型への変換</span><span class="sxs-lookup"><span data-stu-id="abbde-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="abbde-179">`ToString` などの任意の文字列変換メソッドを使用して、`varchar(max)` 列または `nvarchar(max)` 列の内容を変換できます。</span><span class="sxs-lookup"><span data-stu-id="abbde-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="abbde-180">次のコード フラグメントは、データを取得する `reader` という名前の <xref:System.Data.SqlClient.SqlDataReader> オブジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="abbde-181">例</span><span class="sxs-lookup"><span data-stu-id="abbde-181">Example</span></span>  
 <span data-ttu-id="abbde-182">次のコードでは、`AdventureWorks` データベースの `ProductPhoto` テーブルから名前と `LargePhoto` オブジェクトを取得し、ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="abbde-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="abbde-183">アセンブリは、<xref:System.Drawing> 名前空間への参照を使用してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbde-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="abbde-184"><xref:System.Data.SqlClient.SqlDataReader> の <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> メソッドは、`Stream` プロパティを公開する <xref:System.Data.SqlTypes.SqlBytes> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="abbde-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="abbde-185">コードではこのオブジェクトを使用して新しい `Bitmap` オブジェクトが作成され、Gif `ImageFormat` に保存されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="abbde-186">大きな値型パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="abbde-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="abbde-187"><xref:System.Data.SqlClient.SqlParameter> オブジェクトで大きな値型を使用する方法は、<xref:System.Data.SqlClient.SqlParameter> オブジェクトで小さい値型を使用する方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="abbde-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="abbde-188">次の例に示すように、大きい値型は <xref:System.Data.SqlClient.SqlParameter> 値として取得することができます。</span><span class="sxs-lookup"><span data-stu-id="abbde-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="abbde-189">このコードは、次の GetDocumentSummary ストアド プロシージャが AdventureWorks サンプル データベースに存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abbde-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="abbde-190">ストアド プロシージャでは @DocumentID という名前の入力パラメーターを受け取り、@DocumentSummary 出力パラメーターの DocumentSummary 列の内容を返します。</span><span class="sxs-lookup"><span data-stu-id="abbde-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="abbde-191">例</span><span class="sxs-lookup"><span data-stu-id="abbde-191">Example</span></span>  
 <span data-ttu-id="abbde-192">ADO.NET コードは <xref:System.Data.SqlClient.SqlConnection> オブジェクトと <xref:System.Data.SqlClient.SqlCommand> オブジェクトを作成して GetDocumentSummary ストアド プロシージャを実行し、大きな値型として格納されているドキュメントの概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="abbde-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="abbde-193">このコードによって @DocumentID 入力パラメーターの値が渡され、@DocumentSummary 出力パラメーターに戻された結果がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="abbde-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="abbde-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="abbde-194">See also</span></span>

- [<span data-ttu-id="abbde-195">SQL Server のバイナリ データと大きな値のデータ</span><span class="sxs-lookup"><span data-stu-id="abbde-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="abbde-196">SQL Server データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="abbde-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="abbde-197">ADO.NETでの SQL Server データ操作</span><span class="sxs-lookup"><span data-stu-id="abbde-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="abbde-198">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="abbde-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
