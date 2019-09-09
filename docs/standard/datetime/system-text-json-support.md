---
title: TimeOffset support in での DateTime と DateTimeOffset のサポート
description: System.string ライブラリでの DateTime 型と DateTimeOffset 型のサポートの概要について説明します。
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 5bff01b10b2bdea4fdcfee86e348c47f44d50103
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374473"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a><span data-ttu-id="851dc-103">TimeOffset support in での DateTime と DateTimeOffset のサポート</span><span class="sxs-lookup"><span data-stu-id="851dc-103">DateTime and DateTimeOffset support in System.Text.Json</span></span>

<span data-ttu-id="851dc-104">System.string ライブラリは、ISO 8601:-2019 拡張プロファイルに従っ<xref:System.DateTime>て<xref:System.DateTimeOffset> 、との値を解析して書き込みます。</span><span class="sxs-lookup"><span data-stu-id="851dc-104">The System.Text.Json library parses and writes <xref:System.DateTime> and <xref:System.DateTimeOffset> values according to the ISO 8601:-2019 extended profile.</span></span>
<span data-ttu-id="851dc-105">[コンバーター](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)は、を使用した<xref:System.Text.Json.JsonSerializer>シリアル化と逆シリアル化のためのカスタムサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="851dc-105">[Converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) provide custom support for serializing and deserializing with <xref:System.Text.Json.JsonSerializer>.</span></span>

## <a name="support-for-the-iso-8601-12019-format"></a><span data-ttu-id="851dc-106">ISO 8601-1:2019 形式のサポート</span><span class="sxs-lookup"><span data-stu-id="851dc-106">Support for the ISO 8601-1:2019 format</span></span>

<span data-ttu-id="851dc-107"><xref:System.Text.Json.JsonSerializer> <xref:System.DateTime> <xref:System.DateTimeOffset> 、 、<xref:System.Text.Json.Utf8JsonReader> 、および<xref:System.Text.Json.JsonElement>の各型は、ISO 8601-1:2019 形式の拡張プロファイルに従って、解析および書き込みとテキスト表現を行います。たとえば、2019-07-26t16 のようになります。 <xref:System.Text.Json.Utf8JsonWriter>: 59:57-05:00。</span><span class="sxs-lookup"><span data-stu-id="851dc-107">The <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>, and <xref:System.Text.Json.JsonElement> types parse and write <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations according to the extended profile of the ISO 8601-1:2019 format; for example, 2019-07-26T16:59:57-05:00.</span></span>

<span data-ttu-id="851dc-108"><xref:System.DateTime>および<xref:System.DateTimeOffset>データは、次の<xref:System.Text.Json.JsonSerializer>方法でシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="851dc-108"><xref:System.DateTime> and <xref:System.DateTimeOffset> data can be serialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

<span data-ttu-id="851dc-109">また、次のように<xref:System.Text.Json.JsonSerializer>して逆シリアル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="851dc-109">They can also be deserialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

<span data-ttu-id="851dc-110">既定のオプションでは<xref:System.DateTime> 、 <xref:System.DateTimeOffset>入力およびテキスト表現は拡張 ISO 8601-1:2019 プロファイルに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="851dc-110">With default options, input <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations must conform to the extended ISO 8601-1:2019 profile.</span></span>
<span data-ttu-id="851dc-111">プロファイルに準拠していない表現を逆シリアル化<xref:System.Text.Json.JsonSerializer>しようとする<xref:System.Text.Json.JsonException>と、がスローされます。</span><span class="sxs-lookup"><span data-stu-id="851dc-111">Attempting to deserialize representations that don't conform to the profile will cause <xref:System.Text.Json.JsonSerializer> to throw a <xref:System.Text.Json.JsonException>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

<span data-ttu-id="851dc-112">は<xref:System.Text.Json.JsonDocument> 、JSON ペイロードの内容 (や<xref:System.DateTimeOffset>表現を含む) <xref:System.DateTime>への構造化されたアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="851dc-112">The <xref:System.Text.Json.JsonDocument> provides structured access to the contents of a JSON payload, including <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span> <span data-ttu-id="851dc-113">次の例では、温度のコレクションを指定した場合に、月曜日の平均温度を計算できる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="851dc-113">The example below shows how, when given a collection of temperatures, the average temperature on Mondays can be calculated:</span></span>

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

<span data-ttu-id="851dc-114">準拠<xref:System.DateTime>していない形式<xref:System.Text.Json.JsonDocument>のペイロードで平均温度を計算しようとすると<xref:System.FormatException>、がをスローします。</span><span class="sxs-lookup"><span data-stu-id="851dc-114">Attempting to compute the average temperature given a payload with non-compliant <xref:System.DateTime> representations will cause <xref:System.Text.Json.JsonDocument> to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

<span data-ttu-id="851dc-115">下位レベル<xref:System.Text.Json.Utf8JsonWriter>の書き込み<xref:System.DateTime>と<xref:System.DateTimeOffset>データ:</span><span class="sxs-lookup"><span data-stu-id="851dc-115">The lower level <xref:System.Text.Json.Utf8JsonWriter> writes <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<span data-ttu-id="851dc-116"><xref:System.Text.Json.Utf8JsonReader>と<xref:System.DateTime>データ<xref:System.DateTimeOffset>を解析します。</span><span class="sxs-lookup"><span data-stu-id="851dc-116"><xref:System.Text.Json.Utf8JsonReader> parses <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

<span data-ttu-id="851dc-117">に<xref:System.Text.Json.Utf8JsonReader>準拠していない形式を読み取ろうとすると、 <xref:System.FormatException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="851dc-117">Attempting to read non-compliant formats with <xref:System.Text.Json.Utf8JsonReader> will cause it to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a><span data-ttu-id="851dc-118"><xref:System.DateTime> と<xref:System.DateTimeOffset>のカスタムサポート<xref:System.Text.Json.JsonSerializer></span><span class="sxs-lookup"><span data-stu-id="851dc-118">Custom support for <xref:System.DateTime> and <xref:System.DateTimeOffset> in <xref:System.Text.Json.JsonSerializer></span></span>

<span data-ttu-id="851dc-119">シリアライザーでカスタムの解析または書式設定を実行する場合は、[カスタムコンバーター](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)を実装できます。</span><span class="sxs-lookup"><span data-stu-id="851dc-119">If you want the serializer to perform custom parsing or formatting, you can implement [custom converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).</span></span>
<span data-ttu-id="851dc-120">以下は例です。</span><span class="sxs-lookup"><span data-stu-id="851dc-120">Here are a few examples:</span></span>

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a><span data-ttu-id="851dc-121">および`DateTime(Offset).Parse`を使用する`DateTime(Offset).ToString`</span><span class="sxs-lookup"><span data-stu-id="851dc-121">Using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`</span></span>

<span data-ttu-id="851dc-122">入力<xref:System.DateTime>または<xref:System.DateTimeOffset>テキスト表現の形式を特定できない場合は`DateTime(Offset).Parse` 、コンバーターの読み取りロジックでメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="851dc-122">If you can't determine the formats of your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations, you can use the `DateTime(Offset).Parse` method in your converter read logic.</span></span> <span data-ttu-id="851dc-123">これにより、を使用できるようになります。さまざまな<xref:System.DateTime>形式と<xref:System.DateTimeOffset>テキスト形式のサポート (iso 8601 以外の文字列や iso 8601 形式の拡張 iso 8601-1:2019 プロファイルに準拠していないなど) のサポート。</span><span class="sxs-lookup"><span data-stu-id="851dc-123">This allows you to use .NET's extensive support for parsing various <xref:System.DateTime> and <xref:System.DateTimeOffset> text formats, including non-ISO 8601 strings and ISO 8601 formats that don't conform to the extended ISO 8601-1:2019 profile.</span></span> <span data-ttu-id="851dc-124">この方法では、シリアライザーのネイティブ実装よりもパフォーマンスが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="851dc-124">This approach is significantly less performant than using the serializer's native implementation.</span></span>

<span data-ttu-id="851dc-125">シリアル化の場合は、コンバーター `DateTime(Offset).ToString`の書き込みロジックでメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="851dc-125">For serializing, you can use the `DateTime(Offset).ToString` method in your converter write logic.</span></span> <span data-ttu-id="851dc-126">これにより、標準<xref:System.DateTime>の<xref:System.DateTimeOffset> [日付と時刻の形式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)、および[カスタムの日付と時刻](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)の書式を使用して、との値を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="851dc-126">This allows you to write <xref:System.DateTime> and <xref:System.DateTimeOffset> values using any of the [standard date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), and the [custom date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>
<span data-ttu-id="851dc-127">これは、シリアライザーのネイティブ実装を使用する場合よりも、パフォーマンスが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="851dc-127">This is also significantly less performant than using the serializer's native implementation.</span></span>

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> <span data-ttu-id="851dc-128">を実装<xref:System.Text.Json.Serialization.JsonConverter%601>するとき`T` 、 <xref:System.DateTime>およびが`typeToConvert`の場合、パラメーター `typeof(DateTime)`は常にになります。</span><span class="sxs-lookup"><span data-stu-id="851dc-128">When implementing <xref:System.Text.Json.Serialization.JsonConverter%601>, and `T` is <xref:System.DateTime>, the `typeToConvert` parameter will always be `typeof(DateTime)`.</span></span>
<span data-ttu-id="851dc-129">パラメーターは、ポリモーフィックなケースを処理する場合や、ジェネリックを`typeof(T)`使用してパフォーマンスの高い方法を実現する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="851dc-129">The parameter is useful for handling polymorphic cases and when using generics to get `typeof(T)` in a performant way.</span></span>

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a><span data-ttu-id="851dc-130">および<xref:System.Buffers.Text.Utf8Parser>を使用する<xref:System.Buffers.Text.Utf8Formatter></span><span class="sxs-lookup"><span data-stu-id="851dc-130">Using <xref:System.Buffers.Text.Utf8Parser> and <xref:System.Buffers.Text.Utf8Formatter></span></span>

<span data-ttu-id="851dc-131">入力<xref:System.DateTime>または<xref:System.DateTimeOffset>テキスト表現が "R"、"l"、"O"、"G" のいずれかの[標準日時書式指定文字列](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)に準拠している場合、または必要に応じて、コンバーターロジックで高速 utf-8 ベースの解析および書式設定メソッドを使用できます。これらの形式のいずれかに従って書き込みます。</span><span class="sxs-lookup"><span data-stu-id="851dc-131">You can use fast UTF-8-based parsing and formatting methods in your converter logic if your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations are compliant with one of the "R", "l", "O", or "G" [standard date and time format Strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), or you want to write according to one of these formats.</span></span> <span data-ttu-id="851dc-132">これは、および`DateTime(Offset).Parse` `DateTime(Offset).ToString`を使用するよりもはるかに高速です。</span><span class="sxs-lookup"><span data-stu-id="851dc-132">This is much faster than using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`.</span></span>

<span data-ttu-id="851dc-133">次の例は、 <xref:System.DateTime> ["R" 標準形式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)に従って値をシリアル化および逆シリアル化するカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="851dc-133">This example shows a custom converter that serializes and deserializes <xref:System.DateTime> values according to [the "R" standard format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span></span>

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> <span data-ttu-id="851dc-134">"R" 標準形式の長さは常に29文字です。</span><span class="sxs-lookup"><span data-stu-id="851dc-134">The "R" standard format will always be 29 characters long.</span></span>

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a><span data-ttu-id="851dc-135">シリアライザー `DateTime(Offset).Parse`のネイティブ解析へのフォールバックとしての使用</span><span class="sxs-lookup"><span data-stu-id="851dc-135">Using `DateTime(Offset).Parse` as a fallback to the serializer's native parsing</span></span>

<span data-ttu-id="851dc-136">通常、入力<xref:System.DateTime>または<xref:System.DateTimeOffset>データが拡張 ISO 8601-1:2019 プロファイルに準拠していることが予想される場合は、シリアライザーのネイティブ解析ロジックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="851dc-136">If you generally expect your input <xref:System.DateTime> or <xref:System.DateTimeOffset> data to conform to the extended ISO 8601-1:2019 profile, you can use the serializer's native parsing logic.</span></span> <span data-ttu-id="851dc-137">また、場合によっては、フォールバックメカニズムを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="851dc-137">You can also implement a fallback mechanism just in case.</span></span>
<span data-ttu-id="851dc-138">この例では、を使用して<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>テキスト表現の解析に失敗した後に、コンバーター <xref:System.DateTime.Parse(System.String)>がを使用してデータを正常に解析することを示しています。</span><span class="sxs-lookup"><span data-stu-id="851dc-138">This example shows that, after failing to parse a <xref:System.DateTime> text representation using <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, the converter successfully parses the data using <xref:System.DateTime.Parse(System.String)>.</span></span>

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a><span data-ttu-id="851dc-139">System.string の拡張された ISO 8601-1:2019 プロファイル</span><span class="sxs-lookup"><span data-stu-id="851dc-139">The extended ISO 8601-1:2019 profile in System.Text.Json</span></span>

### <a name="date-and-time-components"></a><span data-ttu-id="851dc-140">日付と時刻のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="851dc-140">Date and time components</span></span>

<span data-ttu-id="851dc-141">で<xref:System.Text.Json>実装されている拡張 ISO 8601-1:2019 プロファイルは、日付と時刻の表現に関して次のコンポーネントを定義します。</span><span class="sxs-lookup"><span data-stu-id="851dc-141">The extended ISO 8601-1:2019 profile implemented in <xref:System.Text.Json> defines the following components for date and time representations.</span></span> <span data-ttu-id="851dc-142">これらのコンポーネントは、解析と書式設定<xref:System.DateTime>および<xref:System.DateTimeOffset>表現の際にサポートされるさまざまな粒度レベルを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="851dc-142">These components are used to define various levels of granularity supported when parsing and formatting <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span>

| <span data-ttu-id="851dc-143">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="851dc-143">Component</span></span>       | <span data-ttu-id="851dc-144">Format</span><span class="sxs-lookup"><span data-stu-id="851dc-144">Format</span></span>                      | <span data-ttu-id="851dc-145">説明</span><span class="sxs-lookup"><span data-stu-id="851dc-145">Description</span></span>                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="851dc-146">Year</span><span class="sxs-lookup"><span data-stu-id="851dc-146">Year</span></span>            | <span data-ttu-id="851dc-147">"yyyy"</span><span class="sxs-lookup"><span data-stu-id="851dc-147">"yyyy"</span></span>                      | <span data-ttu-id="851dc-148">0001-9999</span><span class="sxs-lookup"><span data-stu-id="851dc-148">0001-9999</span></span>                                                                       |
| <span data-ttu-id="851dc-149">Month</span><span class="sxs-lookup"><span data-stu-id="851dc-149">Month</span></span>           | <span data-ttu-id="851dc-150">"MM"</span><span class="sxs-lookup"><span data-stu-id="851dc-150">"MM"</span></span>                        | <span data-ttu-id="851dc-151">01-12</span><span class="sxs-lookup"><span data-stu-id="851dc-151">01-12</span></span>                                                                           |
| <span data-ttu-id="851dc-152">Day</span><span class="sxs-lookup"><span data-stu-id="851dc-152">Day</span></span>             | <span data-ttu-id="851dc-153">"dd"</span><span class="sxs-lookup"><span data-stu-id="851dc-153">"dd"</span></span>                        | <span data-ttu-id="851dc-154">01-28、01-29、01-30、01-31 (月/年)</span><span class="sxs-lookup"><span data-stu-id="851dc-154">01-28, 01-29, 01-30, 01-31 based on month/year</span></span>                                  |
| <span data-ttu-id="851dc-155">Hour</span><span class="sxs-lookup"><span data-stu-id="851dc-155">Hour</span></span>            | <span data-ttu-id="851dc-156">"HH"</span><span class="sxs-lookup"><span data-stu-id="851dc-156">"HH"</span></span>                        | <span data-ttu-id="851dc-157">00-23</span><span class="sxs-lookup"><span data-stu-id="851dc-157">00-23</span></span>                                                                           |
| <span data-ttu-id="851dc-158">Minute</span><span class="sxs-lookup"><span data-stu-id="851dc-158">Minute</span></span>          | <span data-ttu-id="851dc-159">"mm"</span><span class="sxs-lookup"><span data-stu-id="851dc-159">"mm"</span></span>                        | <span data-ttu-id="851dc-160">00-59</span><span class="sxs-lookup"><span data-stu-id="851dc-160">00-59</span></span>                                                                           |
| <span data-ttu-id="851dc-161">Second</span><span class="sxs-lookup"><span data-stu-id="851dc-161">Second</span></span>          | <span data-ttu-id="851dc-162">"ss"</span><span class="sxs-lookup"><span data-stu-id="851dc-162">"ss"</span></span>                        | <span data-ttu-id="851dc-163">00-59</span><span class="sxs-lookup"><span data-stu-id="851dc-163">00-59</span></span>                                                                           |
| <span data-ttu-id="851dc-164">2番目の分数</span><span class="sxs-lookup"><span data-stu-id="851dc-164">Second fraction</span></span> | <span data-ttu-id="851dc-165">"FFFFFFF"</span><span class="sxs-lookup"><span data-stu-id="851dc-165">"FFFFFFF"</span></span>                   | <span data-ttu-id="851dc-166">最低1桁、最大16桁</span><span class="sxs-lookup"><span data-stu-id="851dc-166">Minimum of one digit, maximum of 16 digits</span></span>                                      |
| <span data-ttu-id="851dc-167">時間のオフセット</span><span class="sxs-lookup"><span data-stu-id="851dc-167">Time offset</span></span>     | <span data-ttu-id="851dc-168">"K"</span><span class="sxs-lookup"><span data-stu-id="851dc-168">"K"</span></span>                         | <span data-ttu-id="851dc-169">"Z" または "(' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="851dc-169">Either "Z" or "('+'/'-')HH':'mm"</span></span>                                                |
| <span data-ttu-id="851dc-170">部分的な時間</span><span class="sxs-lookup"><span data-stu-id="851dc-170">Partial time</span></span>    | <span data-ttu-id="851dc-171">"HH ': ' mm ': ' ss [FFFFFFF]"</span><span class="sxs-lookup"><span data-stu-id="851dc-171">"HH':'mm':'ss[FFFFFFF]"</span></span>     | <span data-ttu-id="851dc-172">UTC オフセット情報なしの時間</span><span class="sxs-lookup"><span data-stu-id="851dc-172">Time without UTC offset information</span></span>                                             |
| <span data-ttu-id="851dc-173">完全な日付</span><span class="sxs-lookup"><span data-stu-id="851dc-173">Full date</span></span>       | <span data-ttu-id="851dc-174">"yyyy'-'mm'-'dd't'hh-' MM'-' dd"</span><span class="sxs-lookup"><span data-stu-id="851dc-174">"yyyy'-'MM'-'dd"</span></span>            | <span data-ttu-id="851dc-175">カレンダーの日付</span><span class="sxs-lookup"><span data-stu-id="851dc-175">Calendar date</span></span>                                                                   |
| <span data-ttu-id="851dc-176">フルタイム</span><span class="sxs-lookup"><span data-stu-id="851dc-176">Full time</span></span>       | <span data-ttu-id="851dc-177">"Partial time'K"</span><span class="sxs-lookup"><span data-stu-id="851dc-177">"'Partial time'K"</span></span>           | <span data-ttu-id="851dc-178">現地時刻と UTC の時差を使用した日の UTC または現地時刻</span><span class="sxs-lookup"><span data-stu-id="851dc-178">UTC of day or Local time of day with the time offset between local time and UTC</span></span> |
| <span data-ttu-id="851dc-179">日付/時刻</span><span class="sxs-lookup"><span data-stu-id="851dc-179">Date time</span></span>       | <span data-ttu-id="851dc-180">"' 完全な日付 ' ' ' ' ' ' ' は完全な時刻 '" になります。</span><span class="sxs-lookup"><span data-stu-id="851dc-180">"'Full date''T''Full time'"</span></span> | <span data-ttu-id="851dc-181">カレンダーの日付と時刻。例: 2019-07-26T16:59:57-05:00</span><span class="sxs-lookup"><span data-stu-id="851dc-181">Calendar date and time of day, e.g. 2019-07-26T16:59:57-05:00</span></span>                   |

### <a name="support-for-parsing"></a><span data-ttu-id="851dc-182">解析のサポート</span><span class="sxs-lookup"><span data-stu-id="851dc-182">Support for parsing</span></span>

<span data-ttu-id="851dc-183">解析のために次の粒度のレベルが定義されています。</span><span class="sxs-lookup"><span data-stu-id="851dc-183">The following levels of granularity are defined for parsing:</span></span>

1. <span data-ttu-id="851dc-184">' 完全な日付 '</span><span class="sxs-lookup"><span data-stu-id="851dc-184">'Full date'</span></span>
    1. <span data-ttu-id="851dc-185">"yyyy'-'mm'-'dd't'hh-' MM'-' dd"</span><span class="sxs-lookup"><span data-stu-id="851dc-185">"yyyy'-'MM'-'dd"</span></span>

2. <span data-ttu-id="851dc-186">"' Full date ' ' ' Hour ' ': ' ' Minute '"</span><span class="sxs-lookup"><span data-stu-id="851dc-186">"'Full date''T''Hour'':''Minute'"</span></span>
    1. <span data-ttu-id="851dc-187">"yyyy'-'mm'-'dd't'hh-' MM'-' + ': ' MM '</span><span class="sxs-lookup"><span data-stu-id="851dc-187">"yyyy'-'MM'-'dd'T'HH':'mm"</span></span>

3. <span data-ttu-id="851dc-188">"' 完全な日付 ' t ' ' Partial time '"</span><span class="sxs-lookup"><span data-stu-id="851dc-188">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="851dc-189">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss ' ([並べ替え可能な (" s ") 書式指定子](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="851dc-189">"yyyy'-'MM'-'dd'T'HH':'mm':'ss" ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>
    2. <span data-ttu-id="851dc-190">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="851dc-190">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

4. <span data-ttu-id="851dc-191">"' Full date ' ' ' Time Time ' ': ' ' Minute ' ' Time offset '"</span><span class="sxs-lookup"><span data-stu-id="851dc-191">"'Full date''T''Time hour'':''Minute''Time offset'"</span></span>
    1. <span data-ttu-id="851dc-192">"yyyy'-'mm'-'dd't'hh-" MM'-' Dd' T' HH ': ' mmZ "</span><span class="sxs-lookup"><span data-stu-id="851dc-192">"yyyy'-'MM'-'dd'T'HH':'mmZ"</span></span>
    2. <span data-ttu-id="851dc-193">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' Hh ': ' mm (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="851dc-193">"yyyy'-'MM'-'dd'T'HH':'mm('+'/'-')HH':'mm"</span></span>

5. <span data-ttu-id="851dc-194">' 日時 '</span><span class="sxs-lookup"><span data-stu-id="851dc-194">'Date time'</span></span>
    1. <span data-ttu-id="851dc-195">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ssZ '</span><span class="sxs-lookup"><span data-stu-id="851dc-195">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>
    2. <span data-ttu-id="851dc-196">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFFZ "</span><span class="sxs-lookup"><span data-stu-id="851dc-196">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>
    3. <span data-ttu-id="851dc-197">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' mm ': ' ss (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="851dc-197">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>
    4. <span data-ttu-id="851dc-198">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFF (' + '/'-') HH ': ' mm "</span><span class="sxs-lookup"><span data-stu-id="851dc-198">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

<span data-ttu-id="851dc-199">秒の小数部がある場合は、少なくとも1つの数字が必要です。`2019-07-26T00:00:00.`は使用できません。</span><span class="sxs-lookup"><span data-stu-id="851dc-199">If there are decimal fractions for seconds, there must be at least one digit; `2019-07-26T00:00:00.` is not allowed.</span></span>
<span data-ttu-id="851dc-200">最大16桁の小数部を使用できますが、最初の7だけが解析されます。</span><span class="sxs-lookup"><span data-stu-id="851dc-200">While up to 16 fractional digits are allowed, only the first seven are parsed.</span></span> <span data-ttu-id="851dc-201">それを超えるものはゼロと見なされます。</span><span class="sxs-lookup"><span data-stu-id="851dc-201">Anything beyond that is considered a zero.</span></span>
<span data-ttu-id="851dc-202">たとえば、 `2019-07-26T00:00:00.1234567890`はのよう`2019-07-26T00:00:00.1234567`に解析されます。</span><span class="sxs-lookup"><span data-stu-id="851dc-202">For example, `2019-07-26T00:00:00.1234567890` will be parsed as if it is `2019-07-26T00:00:00.1234567`.</span></span>
<span data-ttu-id="851dc-203">これは、この解決に限定<xref:System.DateTime>された実装との互換性を維持するためのものです。</span><span class="sxs-lookup"><span data-stu-id="851dc-203">This is to stay compatible with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>

<span data-ttu-id="851dc-204">うるう秒はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="851dc-204">Leap seconds are not supported.</span></span>

### <a name="support-for-formatting"></a><span data-ttu-id="851dc-205">書式設定のサポート</span><span class="sxs-lookup"><span data-stu-id="851dc-205">Support for formatting</span></span>

<span data-ttu-id="851dc-206">次の粒度レベルは、書式設定のために定義されています。</span><span class="sxs-lookup"><span data-stu-id="851dc-206">The following levels of granularity are defined for formatting:</span></span>

1. <span data-ttu-id="851dc-207">"' 完全な日付 ' t ' ' Partial time '"</span><span class="sxs-lookup"><span data-stu-id="851dc-207">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="851dc-208">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss ' ([並べ替え可能な (" s ") 書式指定子](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="851dc-208">"yyyy'-'MM'-'dd'T'HH':'mm':'ss"  ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>

        <span data-ttu-id="851dc-209">秒の小数部<xref:System.DateTime>を含まない、オフセット情報を使用せずに、を書式設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-209">Used to format a <xref:System.DateTime> without fractional seconds and without offset information.</span></span>

    2. <span data-ttu-id="851dc-210">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="851dc-210">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

        <span data-ttu-id="851dc-211">秒の小数部<xref:System.DateTime>のオフセット情報を使用せずに、を書式設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-211">Used to format a <xref:System.DateTime> with fractional seconds but without offset information.</span></span>

2. <span data-ttu-id="851dc-212">' 日時 '</span><span class="sxs-lookup"><span data-stu-id="851dc-212">'Date time'</span></span>
    1. <span data-ttu-id="851dc-213">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ssZ '</span><span class="sxs-lookup"><span data-stu-id="851dc-213">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>

        <span data-ttu-id="851dc-214">秒の小数部<xref:System.DateTime>を<xref:System.DateTimeOffset>含まないか、UTC オフセットを使用して、またはの書式を設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-214">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a UTC offset.</span></span>

    2. <span data-ttu-id="851dc-215">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFFZ "</span><span class="sxs-lookup"><span data-stu-id="851dc-215">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>

        <span data-ttu-id="851dc-216">秒の小数部<xref:System.DateTime>と<xref:System.DateTimeOffset> UTC オフセットを使用して、またはの書式を設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-216">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a UTC offset.</span></span>

    3. <span data-ttu-id="851dc-217">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' mm ': ' ss (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="851dc-217">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="851dc-218">秒の小数部<xref:System.DateTime>を<xref:System.DateTimeOffset>含まない、またはローカルオフセットを使用して、またはの書式を設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-218">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a local offset.</span></span>

    4. <span data-ttu-id="851dc-219">"yyyy'-'mm'-'dd't'hh-' MM'-' Dd' T' HH ': ' MM ': ' ss '. 'FFFFFFF (' + '/'-') HH ': ' mm "</span><span class="sxs-lookup"><span data-stu-id="851dc-219">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="851dc-220">秒の小数部<xref:System.DateTime>と<xref:System.DateTimeOffset>ローカルオフセットを使用して、またはの書式を設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="851dc-220">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a local offset.</span></span>
