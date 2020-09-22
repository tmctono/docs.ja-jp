---
title: 日付と時刻のデータ
description: .NET Framework Data Provider for SQL Server で日付と時刻の情報を処理するためのデータ型について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: 43b3349b2a35385dcc49d0866e0695b08eac2d2e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551492"
---
# <a name="date-and-time-data"></a><span data-ttu-id="c8824-103">日付と時刻のデータ</span><span class="sxs-lookup"><span data-stu-id="c8824-103">Date and Time Data</span></span>
<span data-ttu-id="c8824-104">SQL Server 2008 では、日付と時刻の情報を扱うための新しいデータ型が導入されました。</span><span class="sxs-lookup"><span data-stu-id="c8824-104">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="c8824-105">新しいデータ型には、日付と時刻の別個のデータ型と、範囲、有効桁数、タイム ゾーン処理が向上した拡張データ型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8824-105">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="c8824-106">.NET Framework 3.5 Service Pack (SP) 1 以降では、.NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) が SQL Server 2008 データベース エンジンの新機能すべてをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8824-106">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="c8824-107">SqlClient でこれらの新機能を使用するには、.NET Framework 3.5 SP1 以降をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8824-107">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="c8824-108">SQL Server 2008 より前のバージョンの SQL Server では、日付と時刻に使用できるデータ型には `datetime` と `smalldatetime` の 2 つしかありませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8824-108">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="c8824-109">どちらのデータ型も日付値と時刻値の両方を保持するため、日付と時刻のどちらか一方の値のみを使用するのが困難でした。</span><span class="sxs-lookup"><span data-stu-id="c8824-109">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="c8824-110">さらに、これらのデータ型では、1753 年に英国でグレゴリオ暦が導入された後の日付のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8824-110">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="c8824-111">もう 1 つの制限事項は、これらの古いデータ型がタイムゾーンに対応していないことです。これにより、複数のタイムゾーンからのデータの操作が困難になります。</span><span class="sxs-lookup"><span data-stu-id="c8824-111">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="c8824-112">SQL Server のデータ型に関する完全な説明は、SQL Server オンライン ブックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="c8824-112">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="c8824-113">次の表は、バージョン別の日付と時刻のデータに関する初歩的なトピックの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c8824-113">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 <span data-ttu-id="c8824-114">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="c8824-114">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="c8824-115">[日時データの使用](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="c8824-115">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="c8824-116">SQL Server 2008 で導入された日付/時刻データ型</span><span class="sxs-lookup"><span data-stu-id="c8824-116">Date/Time Data Types Introduced in SQL Server 2008</span></span>  
 <span data-ttu-id="c8824-117">次の表は、新しい日付と時刻のデータ型の説明です。</span><span class="sxs-lookup"><span data-stu-id="c8824-117">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="c8824-118">SQL Server のデータ型</span><span class="sxs-lookup"><span data-stu-id="c8824-118">SQL Server data type</span></span>|<span data-ttu-id="c8824-119">説明</span><span class="sxs-lookup"><span data-stu-id="c8824-119">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="c8824-120">データ型 `date` の範囲は 01 年 1 月 1 日から 9999 年 12 月 31 日までで、精度は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="c8824-120">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="c8824-121">既定値は 1900 年 1 月 1 日です。</span><span class="sxs-lookup"><span data-stu-id="c8824-121">The default value is January 1, 1900.</span></span> <span data-ttu-id="c8824-122">記憶領域のサイズは 3 バイトです。</span><span class="sxs-lookup"><span data-stu-id="c8824-122">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="c8824-123">`time` データ型は、24 時間形式で時刻値のみを格納します。</span><span class="sxs-lookup"><span data-stu-id="c8824-123">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="c8824-124">`time` データ型は、00:00:00.0000000 から 23:59:59.9999999 の範囲で、100 ナノ秒の精度です。</span><span class="sxs-lookup"><span data-stu-id="c8824-124">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="c8824-125">既定値は 00:00: 00.0000000 (午前 0 時) です。</span><span class="sxs-lookup"><span data-stu-id="c8824-125">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="c8824-126">`time` データ型はユーザー定義による 1 秒未満の時間の有効桁数をサポートし、記憶領域のサイズは、指定された有効桁数に応じて 3 バイト～ 6 バイトになります。</span><span class="sxs-lookup"><span data-stu-id="c8824-126">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="c8824-127">`datetime2` データ型では、`date` データ型と `time` データ型の範囲と精度が 1 つのデータ型に結合されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-127">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="c8824-128">既定値と文字列リテラルの形式は、`date` データ型および `time` データ型で定義されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="c8824-128">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="c8824-129">`datetimeoffset` データ型は、`datetime2` のすべての機能に加えて、タイム ゾーン オフセットを持ちます。</span><span class="sxs-lookup"><span data-stu-id="c8824-129">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="c8824-130">タイム ゾーン オフセットは、[+&#124;-] HH:MM として表されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-130">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="c8824-131">HH は、タイム ゾーン オフセットの時間数を表す 00 ～ 14 の 2 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="c8824-131">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="c8824-132">MM は、タイム ゾーン オフセットの付加的な分数を表す 0 ～ 59 の 2 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="c8824-132">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="c8824-133">時刻の精度は 100 ナノ秒までサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8824-133">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="c8824-134">必須の + または - 記号は、ローカル時刻を取得するために、UTC (協定世界時またはグリニッジ標準時) からタイム ゾーン オフセットを加算するか減算するかを示します。</span><span class="sxs-lookup"><span data-stu-id="c8824-134">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c8824-135">`Type System Version` キーワードの使用方法の詳細については、「<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8824-135">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="c8824-136">日付書式と表記順序</span><span class="sxs-lookup"><span data-stu-id="c8824-136">Date Format and Date Order</span></span>  
 <span data-ttu-id="c8824-137">SQL Server が日付と時刻の値をどのように処理するかは、型システムのバージョンとサーバーのバージョンだけでなく、サーバーの既定の言語と書式設定にも左右されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-137">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="c8824-138">ある言語の日付形式に対して機能する日付文字列は、別の言語および日付形式の設定を使用する接続によってクエリが実行された場合に認識されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8824-138">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="c8824-139">Transact-SQL SET LANGUAGE ステートメントでは、日付部分の順序を決定する DATEFORMAT を暗黙的に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8824-139">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="c8824-140">接続に対して SET DATEFORMAT Transact-SQL ステートメントを使用して、MDY、DMY、YMD、YDM、MYD、DYM の順序で日付部分を並べ替えることにより、日付値を明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8824-140">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="c8824-141">接続に対して DATEFORMAT を指定しない場合、SQL Server では接続に関連付けられている既定の言語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-141">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="c8824-142">たとえば、' 01/02/03' の日付文字列は、米国英語の言語設定のサーバーでは MDY (2003 年 1 月 2 日) として解釈され、英国英語の言語設定のサーバーでは DMY (2003 年 2 月 1 日) として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-142">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="c8824-143">年は、SQL Server の終了年の規則に従って決定されます。この規則では、世紀の値を割り当てるための終了日が定義されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-143">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="c8824-144">詳しくは、「[two digit year cutoff オプション](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8824-144">For more information, see [two digit year cutoff Option](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8824-145">YDM 日付書式は、文字列形式から `date`、`time`、`datetime2`、または `datetimeoffset` に変換する場合にはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c8824-145">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="c8824-146">SQL Server による日付と時刻のデータの解釈方法について詳しくは、「[日時データの使用](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8824-146">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="c8824-147">Date/Time データ型とパラメーター</span><span class="sxs-lookup"><span data-stu-id="c8824-147">Date/Time Data Types and Parameters</span></span>  
 <span data-ttu-id="c8824-148">新しい日付型と時刻型をサポートするために、<xref:System.Data.SqlDbType> には、次の列挙値が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c8824-148">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="c8824-149"><xref:System.Data.SqlClient.SqlParameter> のデータ型は、前の <xref:System.Data.SqlDbType> 列挙型のいずれかの値を使って指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8824-149">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span>

> [!NOTE]
> <span data-ttu-id="c8824-150">`SqlParameter` の `DbType` プロパティは `SqlDbType.Date` に設定できません。</span><span class="sxs-lookup"><span data-stu-id="c8824-150">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="c8824-151"><xref:System.Data.SqlClient.SqlParameter> オブジェクトの <xref:System.Data.SqlClient.SqlParameter.DbType%2A> プロパティを特定の `SqlParameter` 列挙値に設定することによって、<xref:System.Data.DbType> の型をジェネリックに指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8824-151">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="c8824-152"><xref:System.Data.DbType> データ型と `datetime2` データ型をサポートするために、`datetimeoffset` には、次の列挙値が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c8824-152">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
- <span data-ttu-id="c8824-153">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="c8824-153">DbType.DateTime2</span></span>  
  
- <span data-ttu-id="c8824-154">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-154">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="c8824-155">これらの新しい列挙値は、以前のバージョンの .NET Framework に存在した `Date`、`Time`、および `DateTime` の各列挙値を補います。</span><span class="sxs-lookup"><span data-stu-id="c8824-155">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c8824-156">パラメーター オブジェクトの .NET Framework データ プロバイダー型は、パラメーター オブジェクトの値の .NET Framework 型か、またはパラメーター オブジェクトの `DbType` から推論されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-156">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="c8824-157">新しい date 型と time 型をサポートするための新しい <xref:System.Data.SqlTypes> データ型は導入されていません。</span><span class="sxs-lookup"><span data-stu-id="c8824-157">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="c8824-158">次の表に、SQL Server 2008 の日付と時刻のデータ型と CLR データ型のマッピングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8824-158">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="c8824-159">SQL Server のデータ型</span><span class="sxs-lookup"><span data-stu-id="c8824-159">SQL Server data type</span></span>|<span data-ttu-id="c8824-160">.NET Framework 型</span><span class="sxs-lookup"><span data-stu-id="c8824-160">.NET Framework type</span></span>|<span data-ttu-id="c8824-161">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="c8824-161">System.Data.SqlDbType</span></span>|<span data-ttu-id="c8824-162">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="c8824-162">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="c8824-163">date</span><span class="sxs-lookup"><span data-stu-id="c8824-163">date</span></span>|<span data-ttu-id="c8824-164">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-164">System.DateTime</span></span>|<span data-ttu-id="c8824-165">Date</span><span class="sxs-lookup"><span data-stu-id="c8824-165">Date</span></span>|<span data-ttu-id="c8824-166">Date</span><span class="sxs-lookup"><span data-stu-id="c8824-166">Date</span></span>|  
|<span data-ttu-id="c8824-167">時間</span><span class="sxs-lookup"><span data-stu-id="c8824-167">time</span></span>|<span data-ttu-id="c8824-168">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="c8824-168">System.TimeSpan</span></span>|<span data-ttu-id="c8824-169">時刻</span><span class="sxs-lookup"><span data-stu-id="c8824-169">Time</span></span>|<span data-ttu-id="c8824-170">時刻</span><span class="sxs-lookup"><span data-stu-id="c8824-170">Time</span></span>|  
|<span data-ttu-id="c8824-171">datetime2</span><span class="sxs-lookup"><span data-stu-id="c8824-171">datetime2</span></span>|<span data-ttu-id="c8824-172">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-172">System.DateTime</span></span>|<span data-ttu-id="c8824-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="c8824-173">DateTime2</span></span>|<span data-ttu-id="c8824-174">DateTime2</span><span class="sxs-lookup"><span data-stu-id="c8824-174">DateTime2</span></span>|  
|<span data-ttu-id="c8824-175">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="c8824-175">datetimeoffset</span></span>|<span data-ttu-id="c8824-176">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-176">System.DateTimeOffset</span></span>|<span data-ttu-id="c8824-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-177">DateTimeOffset</span></span>|<span data-ttu-id="c8824-178">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-178">DateTimeOffset</span></span>|  
|<span data-ttu-id="c8824-179">datetime</span><span class="sxs-lookup"><span data-stu-id="c8824-179">datetime</span></span>|<span data-ttu-id="c8824-180">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-180">System.DateTime</span></span>|<span data-ttu-id="c8824-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-181">DateTime</span></span>|<span data-ttu-id="c8824-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-182">DateTime</span></span>|  
|<span data-ttu-id="c8824-183">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="c8824-183">smalldatetime</span></span>|<span data-ttu-id="c8824-184">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-184">System.DateTime</span></span>|<span data-ttu-id="c8824-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-185">DateTime</span></span>|<span data-ttu-id="c8824-186">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-186">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="c8824-187">SqlParameter プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8824-187">SqlParameter Properties</span></span>  
 <span data-ttu-id="c8824-188">次の表は、日付と時刻のデータ型に関係する `SqlParameter` プロパティの説明です。</span><span class="sxs-lookup"><span data-stu-id="c8824-188">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="c8824-189">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8824-189">Property</span></span>|<span data-ttu-id="c8824-190">説明</span><span class="sxs-lookup"><span data-stu-id="c8824-190">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="c8824-191">値が null 許容であるかどうかを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c8824-191">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="c8824-192">サーバーに NULL パラメーター値を送る場合は、<xref:System.DBNull> (Visual Basic の場合は `null`) ではなく、`Nothing` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8824-192">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="c8824-193">データベースの NULL 値の詳細については、「 [Handling Null Values](handling-null-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8824-193">For more information about database nulls, see [Handling Null Values](handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="c8824-194">その値の最大桁数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c8824-194">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="c8824-195">この設定は日付と時刻のデータ型では無視されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-195">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="c8824-196">小数点以下の桁数を取得または設定します。これは `Time`、`DateTime2`、`DateTimeOffset` の時刻部分の値の処理で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-196">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="c8824-197">既定値は 0 で、これは実際のスケールが値から推論され、サーバーに送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c8824-197">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="c8824-198">日付と時刻のデータ型では無視されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-198">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="c8824-199">パラメーター値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c8824-199">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="c8824-200">パラメーター値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c8824-200">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c8824-201">時刻の値が 0 と 24 の間にない場合は、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c8824-201">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="c8824-202">パラメーターの作成</span><span class="sxs-lookup"><span data-stu-id="c8824-202">Creating Parameters</span></span>  
 <span data-ttu-id="c8824-203"><xref:System.Data.SqlClient.SqlParameter> オブジェクトは、そのコンストラクターを使って作成できるほか、<xref:System.Data.SqlClient.SqlCommand> の <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> メソッドを呼び出して、`Add`<xref:System.Data.SqlClient.SqlParameterCollection> コレクションにそれを追加することによって作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8824-203">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="c8824-204">`Add` メソッドは、入力としてコンストラクター引数または既存のパラメーター オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c8824-204">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="c8824-205">このトピックの次のセクションでは、日付と時刻のパラメーターを指定する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8824-205">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="c8824-206">パラメーターの使用に関するその他の例については、「[パラメーターおよびパラメーター データ型の構成](../configuring-parameters-and-parameter-data-types.md)」および「[DataAdapter パラメーター](../dataadapter-parameters.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8824-206">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="c8824-207">Date の例</span><span class="sxs-lookup"><span data-stu-id="c8824-207">Date Example</span></span>  
 <span data-ttu-id="c8824-208">次のコード フラグメントは、`date` パラメーターの指定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8824-208">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="c8824-209">Time の例</span><span class="sxs-lookup"><span data-stu-id="c8824-209">Time Example</span></span>  
 <span data-ttu-id="c8824-210">次のコード フラグメントは、`time` パラメーターの指定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8824-210">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="c8824-211">Datetime2 の例</span><span class="sxs-lookup"><span data-stu-id="c8824-211">Datetime2 Example</span></span>  
 <span data-ttu-id="c8824-212">次のコード フラグメントは、`datetime2` パラメーターの日付と時刻の指定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8824-212">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="c8824-213">DateTimeOffSet の例</span><span class="sxs-lookup"><span data-stu-id="c8824-213">DateTimeOffSet Example</span></span>  
 <span data-ttu-id="c8824-214">次のコード フラグメントは、`DateTimeOffSet` パラメーターの日付と時刻、およびタイム ゾーン オフセット 0 を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8824-214">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="c8824-215">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="c8824-215">AddWithValue</span></span>  
 <span data-ttu-id="c8824-216">次のコード フラグメントに示すように、<xref:System.Data.SqlClient.SqlCommand> の `AddWithValue` メソッドを使用してパラメーターを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8824-216">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="c8824-217">ただし、`AddWithValue` メソッドでは、パラメーターの <xref:System.Data.SqlClient.SqlParameter.DbType%2A> または <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8824-217">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="c8824-218">`@date` パラメーターは、サーバー上の `date`、`datetime`、または `datetime2` データ型にマッピングできます。</span><span class="sxs-lookup"><span data-stu-id="c8824-218">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="c8824-219">新しい `datetime` データ型を使用する場合は、パラメーターの <xref:System.Data.SqlDbType> プロパティをインスタンスのデータ型に明示的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8824-219">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="c8824-220"><xref:System.Data.SqlDbType.Variant> を使用するか、または暗黙的にパラメーター値を指定すると、`datetime` データ型および `smalldatetime` データ型との下位互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8824-220">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="c8824-221">次の表は、どの CLR 型からどの `SqlDbTypes` が推論されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="c8824-221">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="c8824-222">CLR 型</span><span class="sxs-lookup"><span data-stu-id="c8824-222">CLR type</span></span>|<span data-ttu-id="c8824-223">推定される SqlDbType</span><span class="sxs-lookup"><span data-stu-id="c8824-223">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="c8824-224">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-224">DateTime</span></span>|<span data-ttu-id="c8824-225">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="c8824-225">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="c8824-226">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="c8824-226">TimeSpan</span></span>|<span data-ttu-id="c8824-227">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="c8824-227">SqlDbType.Time</span></span>|  
|<span data-ttu-id="c8824-228">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-228">DateTimeOffset</span></span>|<span data-ttu-id="c8824-229">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c8824-229">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="c8824-230">日付と時刻データの取得</span><span class="sxs-lookup"><span data-stu-id="c8824-230">Retrieving Date and Time Data</span></span>  
 <span data-ttu-id="c8824-231">SQL Server 2008 の日付値および時刻値を取得するためのメソッドを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c8824-231">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="c8824-232">SqlClient のメソッド</span><span class="sxs-lookup"><span data-stu-id="c8824-232">SqlClient method</span></span>|<span data-ttu-id="c8824-233">説明</span><span class="sxs-lookup"><span data-stu-id="c8824-233">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="c8824-234">指定された列の値を <xref:System.DateTime> 構造体として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-234">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="c8824-235">指定された列の値を <xref:System.DateTimeOffset> 構造体として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-235">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="c8824-236">そのフィールドの基になるプロバイダー固有の型である型を返します。</span><span class="sxs-lookup"><span data-stu-id="c8824-236">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="c8824-237">新しい日付と時刻の型に対して `GetFieldType` と同じ型を返します。</span><span class="sxs-lookup"><span data-stu-id="c8824-237">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="c8824-238">指定された列の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-238">Retrieves the value of the specified column.</span></span> <span data-ttu-id="c8824-239">新しい日付と時刻の型に対して `GetValue` と同じ型を返します。</span><span class="sxs-lookup"><span data-stu-id="c8824-239">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="c8824-240">指定した配列内の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-240">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="c8824-241">列の値を <xref:System.Data.SqlTypes.SqlString> として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-241">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="c8824-242">データを `SqlString` として表現できない場合、<xref:System.InvalidCastException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="c8824-242">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="c8824-243">列データをその既定の `SqlDbType` として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-243">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="c8824-244">新しい日付と時刻の型に対して `GetValue` と同じ型を返します。</span><span class="sxs-lookup"><span data-stu-id="c8824-244">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="c8824-245">指定した配列内の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-245">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="c8824-246">Type System Version が SQL Server 2005 に設定されている場合、列の値を文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-246">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="c8824-247">データを文字列として表現できない場合、<xref:System.InvalidCastException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="c8824-247">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="c8824-248">指定された列の値を <xref:System.TimeSpan> 構造体として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-248">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="c8824-249">指定した列の値を、その基になる CLR 型として取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-249">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="c8824-250">配列内の列の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8824-250">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="c8824-251">結果セットのメタデータを記述する <xref:System.Data.DataTable> を返します。</span><span class="sxs-lookup"><span data-stu-id="c8824-251">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c8824-252">新しい日付と時刻の `SqlDbTypes` は、SQL Server でインプロセスで実行されているコードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c8824-252">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="c8824-253">そのような型の 1 つがサーバーに渡されると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="c8824-253">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="c8824-254">日付値と時刻値のリテラル指定</span><span class="sxs-lookup"><span data-stu-id="c8824-254">Specifying Date and Time Values as Literals</span></span>  
 <span data-ttu-id="c8824-255">日付と時刻のデータ型は、さまざまなリテラル文字列形式を使用して指定できます。SQL Server は、実行時にそれらを内部の日付/時刻構造体に変換します。</span><span class="sxs-lookup"><span data-stu-id="c8824-255">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="c8824-256">SQL Server では、一重引用符 (') で囲まれた日付と時刻のデータが認識されます。</span><span class="sxs-lookup"><span data-stu-id="c8824-256">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="c8824-257">次の例に、いくつかの形式を示します。</span><span class="sxs-lookup"><span data-stu-id="c8824-257">The following examples demonstrate some formats:</span></span>  
  
- <span data-ttu-id="c8824-258">アルファベットの日付形式 (`'October 15, 2006'` など)。</span><span class="sxs-lookup"><span data-stu-id="c8824-258">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
- <span data-ttu-id="c8824-259">数値の日付形式 (`'10/15/2006'`など)。</span><span class="sxs-lookup"><span data-stu-id="c8824-259">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
- <span data-ttu-id="c8824-260">区切られていない文字列形式 (`'20061015'` など。これは ISO 標準日付形式を使用している場合、2006 年 10 月 15 日と解釈される)。</span><span class="sxs-lookup"><span data-stu-id="c8824-260">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8824-261">すべてのリテラル文字列形式と、日付と時刻のデータ型のその他の機能に関する完全なドキュメントについては、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8824-261">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c8824-262">時刻の値が 0 と 24 の間にない場合は、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c8824-262">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="c8824-263">SQL Server オンライン ブックの関連トピック</span><span class="sxs-lookup"><span data-stu-id="c8824-263">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="c8824-264">SQL Server での日付値と時刻値の使用方法の詳細については、SQL Server オンライン ブックで以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8824-264">For more information about working with date and time values in SQL Server, see the following resources in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="c8824-265">トピック</span><span class="sxs-lookup"><span data-stu-id="c8824-265">Topic</span></span>|<span data-ttu-id="c8824-266">説明</span><span class="sxs-lookup"><span data-stu-id="c8824-266">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c8824-267">日付と時刻のデータ型および関数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c8824-267">Date and Time Data Types and Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|<span data-ttu-id="c8824-268">Transact-SQL の日付と時刻のデータ型および関数の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8824-268">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|<span data-ttu-id="c8824-269">[日時データの使用](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="c8824-269">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>|<span data-ttu-id="c8824-270">日付と時刻のデータ型と関数の情報、および使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8824-270">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="c8824-271">データ型 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c8824-271">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)|<span data-ttu-id="c8824-272">SQL Server でのシステム データ型について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8824-272">Describes system data types in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8824-273">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8824-273">See also</span></span>

- [<span data-ttu-id="c8824-274">SQL Server データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="c8824-274">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="c8824-275">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="c8824-275">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="c8824-276">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c8824-276">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="c8824-277">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c8824-277">ADO.NET Overview</span></span>](../ado-net-overview.md)
