---
title: .Net を使用してC# JSON をシリアル化および逆シリアル化する方法
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3d3dc0011562e25854938aff857f2832a5978b49
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283331"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="729bc-102">.NET で JSON をシリアル化および逆シリアル化する方法</span><span class="sxs-lookup"><span data-stu-id="729bc-102">How to serialize and deserialize JSON in .NET</span></span>

<span data-ttu-id="729bc-103">この記事では、<xref:System.Text.Json> 名前空間を使用して、JavaScript Object Notation (JSON) との間でシリアル化および逆シリアル化を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="729bc-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="729bc-104">指示とサンプルコードは、ライブラリを直接使用します。 [ASP.NET Core](/aspnet/core/)などのフレームワークでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="729bc-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="729bc-105">シリアル化のサンプルコードの大部分では、JSON を "見栄えよく" するように `true` に <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> を設定します (ユーザーが読みやすくするためにインデントと空白文字が使用されます)。</span><span class="sxs-lookup"><span data-stu-id="729bc-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="729bc-106">実稼働環境で使用する場合は、通常、この設定の `false` の既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="729bc-107">名前空間</span><span class="sxs-lookup"><span data-stu-id="729bc-107">Namespaces</span></span>

<span data-ttu-id="729bc-108"><xref:System.Text.Json> 名前空間には、すべてのエントリポイントと主要な型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="729bc-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="729bc-109"><xref:System.Text.Json.Serialization> 名前空間には、シリアル化と逆シリアル化に固有の高度なシナリオとカスタマイズのための属性と Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="729bc-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="729bc-110">この記事に示されているコード例では、次のいずれかまたは両方の名前空間に `using` ディレクティブが必要です。</span><span class="sxs-lookup"><span data-stu-id="729bc-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="729bc-111"><xref:System.Runtime.Serialization> 名前空間の属性は、現在 `System.Text.Json`ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="729bc-112">.NET オブジェクトを JSON に書き込む方法 (シリアル化)</span><span class="sxs-lookup"><span data-stu-id="729bc-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="729bc-113">JSON を文字列またはファイルに書き込むには、<xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="729bc-114">次の例では、JSON を文字列として作成します。</span><span class="sxs-lookup"><span data-stu-id="729bc-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-115">次の例では、同期コードを使用して JSON ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="729bc-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-116">次の例では、非同期コードを使用して JSON ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="729bc-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-117">前の例では、シリアル化する型の型の推定を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="729bc-118">`Serialize()` のオーバーロードは、ジェネリック型パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="729bc-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="729bc-119">シリアル化の例</span><span class="sxs-lookup"><span data-stu-id="729bc-119">Serialization example</span></span>

<span data-ttu-id="729bc-120">コレクションと入れ子になったクラスを含むクラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="729bc-121">前の型のインスタンスをシリアル化した JSON 出力は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="729bc-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="729bc-122">既定では、JSON 出力が縮小されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="729bc-123">次の例では、同じ JSON が書式設定されています (空白とインデントで整形されています)。</span><span class="sxs-lookup"><span data-stu-id="729bc-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="729bc-124">UTF-8 にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="729bc-124">Serialize to UTF-8</span></span>

<span data-ttu-id="729bc-125">UTF-8 にシリアル化するには、<xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-126"><xref:System.Text.Json.Utf8JsonWriter> を受け取る <xref:System.Text.Json.JsonSerializer.Serialize%2A> のオーバーロードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="729bc-127">UTF-8 へのシリアル化は、文字列ベースのメソッドを使用するよりも約5-10% 高速です。</span><span class="sxs-lookup"><span data-stu-id="729bc-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="729bc-128">違いは、バイト (UTF-8) を文字列 (UTF-16) に変換する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="729bc-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="729bc-129">シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="729bc-129">Serialization behavior</span></span>

* <span data-ttu-id="729bc-130">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="729bc-131">[除外するプロパティを指定](#exclude-properties-from-serialization)できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="729bc-132">[既定のエンコーダー](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)は、非 ascii 文字、ascii 範囲内の HTML を区別する文字、および[RFC 8259 JSON 仕様](https://tools.ietf.org/html/rfc8259#section-7)に従ってエスケープされる必要がある文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="729bc-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="729bc-133">既定では、JSON は縮小されています。</span><span class="sxs-lookup"><span data-stu-id="729bc-133">By default, JSON is minified.</span></span> <span data-ttu-id="729bc-134">[JSON はかなり印刷](#serialize-to-formatted-json)できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="729bc-135">既定では、JSON 名の大文字と小文字の区別は .NET 名と一致します。</span><span class="sxs-lookup"><span data-stu-id="729bc-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="729bc-136">[JSON 名の大文字と小文字](#customize-json-names-and-values)の区別をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="729bc-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="729bc-137">循環参照が検出され、例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="729bc-137">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="729bc-138">詳細については、GitHub の dotnet/corefx リポジトリの[循環参照に関する問題 38579](https://github.com/dotnet/corefx/issues/38579)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-138">For more information, see [issue 38579 on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="729bc-139">現在、フィールドは除外されています。</span><span class="sxs-lookup"><span data-stu-id="729bc-139">Currently, fields are excluded.</span></span>

<span data-ttu-id="729bc-140">サポートされている種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="729bc-140">Supported types include:</span></span>

* <span data-ttu-id="729bc-141">数値型、文字列、ブール値など、JavaScript プリミティブにマップされる .NET プリミティブ。</span><span class="sxs-lookup"><span data-stu-id="729bc-141">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="729bc-142">ユーザー定義の[Plain OLD CLR オブジェクト (POCOs)](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="729bc-142">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="729bc-143">1次元配列とジャグ配列 (`ArrayName[][]`)。</span><span class="sxs-lookup"><span data-stu-id="729bc-143">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="729bc-144">`Dictionary<string,TValue>` `TValue` が `object`、`JsonElement`、または POCO です。</span><span class="sxs-lookup"><span data-stu-id="729bc-144">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="729bc-145">次の名前空間のコレクション。</span><span class="sxs-lookup"><span data-stu-id="729bc-145">Collections from the following namespaces.</span></span> <span data-ttu-id="729bc-146">詳細については、GitHub の dotnet/corefx リポジトリの[コレクションサポートに関する問題](https://github.com/dotnet/corefx/issues/36643)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-146">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="729bc-147">[カスタムコンバーターを実装](system-text-json-converters-how-to.md)して、追加の型を処理したり、組み込みのコンバーターでサポートされていない機能を提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="729bc-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="729bc-148">JSON を .NET オブジェクトに読み込む方法 (逆シリアル化)</span><span class="sxs-lookup"><span data-stu-id="729bc-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="729bc-149">文字列またはファイルから逆シリアル化するには、<xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="729bc-150">次の例では、文字列から JSON を読み取り、[シリアル化の例](#serialization-example)で前に示した `WeatherForecast` クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="729bc-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-151">同期コードを使用してファイルから逆シリアル化するには、次の例に示すように、ファイルを文字列に読み取ります。</span><span class="sxs-lookup"><span data-stu-id="729bc-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-152">非同期コードを使用してファイルから逆シリアル化するには、<xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="729bc-153">UTF-8 からの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="729bc-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="729bc-154">UTF-8 から逆シリアル化するには、次の例に示すように、`Utf8JsonReader` または `ReadOnlySpan<byte>`を受け取る <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> オーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="729bc-155">この例では、JSON が jsonUtf8Bytes という名前のバイト配列にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="729bc-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="729bc-156">逆シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="729bc-156">Deserialization behavior</span></span>

* <span data-ttu-id="729bc-157">既定では、プロパティ名の照合では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="729bc-158">[大文字と小文字を区別](#case-insensitive-property-matching)しないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="729bc-159">JSON に読み取り専用プロパティの値が含まれている場合、この値は無視され、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="729bc-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="729bc-160">パラメーターなしのコンストラクターを使用しない参照型への逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="729bc-161">変更できないオブジェクトまたは読み取り専用プロパティへの逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="729bc-162">詳細については、github の dotnet/corefx リポジトリで、[変更不可のオブジェクトのサポートに関する github の問題 38569](https://github.com/dotnet/corefx/issues/38569)を参照し、[読み取り専用プロパティのサポートに38163を発行](https://github.com/dotnet/corefx/issues/38163)してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-162">For more information, see GitHub [issue 38569 on immutable object support](https://github.com/dotnet/corefx/issues/38569) and [issue 38163 on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="729bc-163">既定では、列挙型は数値としてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="729bc-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="729bc-164">[列挙型名を文字列としてシリアル化](#enums-as-strings)できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="729bc-165">フィールドはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-165">Fields aren't supported.</span></span>
* <span data-ttu-id="729bc-166">既定では、JSON のコメントまたは末尾のコンマによって例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="729bc-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="729bc-167">[コメントと末尾のコンマを許可](#allow-comments-and-trailing-commas)できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="729bc-168">[既定の最大の深さ](xref:System.Text.Json.JsonReaderOptions.MaxDepth)は64です。</span><span class="sxs-lookup"><span data-stu-id="729bc-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="729bc-169">組み込みのコンバーターでサポートされていない機能を提供するために、[カスタムコンバーターを実装](system-text-json-converters-how-to.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="729bc-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="729bc-170">書式設定された JSON にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="729bc-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="729bc-171">JSON 出力を整形するには、<xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="729bc-172">シリアル化され、整形された JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="729bc-173">JSON の名前と値をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="729bc-173">Customize JSON names and values</span></span>

<span data-ttu-id="729bc-174">既定では、プロパティ名とディクショナリキーは、大文字と小文字を含め、JSON の出力では変更されません。</span><span class="sxs-lookup"><span data-stu-id="729bc-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="729bc-175">列挙値は数値として表されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="729bc-176">このセクションでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="729bc-176">This section explains how to:</span></span>

* [<span data-ttu-id="729bc-177">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="729bc-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="729bc-178">すべてのプロパティ名を camel 形式に変換します</span><span class="sxs-lookup"><span data-stu-id="729bc-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="729bc-179">カスタムプロパティの名前付けポリシーを実装する</span><span class="sxs-lookup"><span data-stu-id="729bc-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="729bc-180">ディクショナリキーを camel 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="729bc-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="729bc-181">列挙型を文字列および camel 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="729bc-181">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="729bc-182">JSON プロパティの名前と値の特別な処理を必要とするその他のシナリオでは、[カスタムコンバーターを実装](system-text-json-converters-how-to.md)できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="729bc-183">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="729bc-183">Customize individual property names</span></span>

<span data-ttu-id="729bc-184">個々のプロパティの名前を設定するには、 [[Jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="729bc-185">シリアル化し、結果として得られる JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="729bc-186">この属性によって設定されるプロパティ名:</span><span class="sxs-lookup"><span data-stu-id="729bc-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="729bc-187">シリアル化と逆シリアル化の両方の方向で適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="729bc-188">は、プロパティの名前付けポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="729bc-189">すべての JSON プロパティ名にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="729bc-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="729bc-190">すべての JSON プロパティ名にキャメルケースを使用するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> を `JsonNamingPolicy.CamelCase`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="729bc-191">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="729bc-192">Camel 形式のプロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="729bc-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="729bc-193">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="729bc-194">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="729bc-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="729bc-195">このため、この例の JSON プロパティ名 `Wind` は camel 形式ではありません。</span><span class="sxs-lookup"><span data-stu-id="729bc-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="729bc-196">カスタム JSON プロパティの名前付けポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="729bc-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="729bc-197">カスタム JSON プロパティの名前付けポリシーを使用するには、次の例に示すように、<xref:System.Text.Json.JsonNamingPolicy> から派生するクラスを作成し、<xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="729bc-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="729bc-198">次に、[<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>] プロパティを名前付けポリシークラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-199">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="729bc-200">JSON プロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="729bc-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="729bc-201">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="729bc-202">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="729bc-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="729bc-203">このため、この例の JSON プロパティ名 `Wind` は大文字ではありません。</span><span class="sxs-lookup"><span data-stu-id="729bc-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="729bc-204">Camel ケースディクショナリキー</span><span class="sxs-lookup"><span data-stu-id="729bc-204">Camel case dictionary keys</span></span>

<span data-ttu-id="729bc-205">シリアル化するオブジェクトのプロパティが `Dictionary<string,TValue>`型である場合は、`string` キーを camel 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="729bc-206">これを行うには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> を `JsonNamingPolicy.CamelCase`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-207">キーと値の `"ColdMinTemp", 20` ペアを持つ `TemperatureRanges` という名前のディクショナリを使用してオブジェクトをシリアル化すると `"HotMinTemp", 40`、次の例のように JSON 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="729bc-208">ディクショナリキーの camel ケースの名前付けポリシーは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="729bc-209">ディクショナリを逆シリアル化すると、`DictionaryKeyPolicy`に `JsonNamingPolicy.CamelCase` を指定した場合でも、キーが JSON ファイルと一致します。</span><span class="sxs-lookup"><span data-stu-id="729bc-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="729bc-210">列挙 (文字列として)</span><span class="sxs-lookup"><span data-stu-id="729bc-210">Enums as strings</span></span>

<span data-ttu-id="729bc-211">既定では、列挙型は数値としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="729bc-212">列挙型名を文字列としてシリアル化するには、<xref:System.Text.Json.Serialization.JsonStringEnumConverter>を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="729bc-213">たとえば、列挙型を持つ次のクラスをシリアル化する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="729bc-214">概要が `Hot`の場合、既定では、シリアル化された JSON の数値は3になります。</span><span class="sxs-lookup"><span data-stu-id="729bc-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="729bc-215">次のサンプルコードでは、数値ではなく列挙型名をシリアル化し、名前を camel 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="729bc-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-216">結果として得られる JSON は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="729bc-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="729bc-217">列挙文字列名も、次の例に示すように逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="729bc-218">シリアル化からプロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="729bc-218">Exclude properties from serialization</span></span>

<span data-ttu-id="729bc-219">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="729bc-220">一部のオプションが JSON 出力に表示されないようにするには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="729bc-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="729bc-221">ここでは、を除外する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="729bc-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="729bc-222">個々のプロパティ</span><span class="sxs-lookup"><span data-stu-id="729bc-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="729bc-223">すべての読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="729bc-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="729bc-224">すべての null 値プロパティ</span><span class="sxs-lookup"><span data-stu-id="729bc-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="729bc-225">個々のプロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="729bc-225">Exclude individual properties</span></span>

<span data-ttu-id="729bc-226">個々のプロパティを無視するには、 [[Jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="729bc-227">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="729bc-228">すべての読み取り専用プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="729bc-228">Exclude all read-only properties</span></span>

<span data-ttu-id="729bc-229">パブリックゲッターが含まれていてもパブリック setter がない場合、プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="729bc-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="729bc-230">すべての読み取り専用プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-231">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="729bc-232">このオプションは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-232">This option applies only to serialization.</span></span> <span data-ttu-id="729bc-233">逆シリアル化中、読み取り専用プロパティは既定では無視されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="729bc-234">すべての null 値プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="729bc-234">Exclude all null value properties</span></span>

<span data-ttu-id="729bc-235">すべての null 値プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-236">シリアル化し、JSON 出力を行うオブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="729bc-237">property</span><span class="sxs-lookup"><span data-stu-id="729bc-237">Property</span></span> |<span data-ttu-id="729bc-238">[値]</span><span class="sxs-lookup"><span data-stu-id="729bc-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="729bc-239">日付</span><span class="sxs-lookup"><span data-stu-id="729bc-239">Date</span></span>    | <span data-ttu-id="729bc-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="729bc-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="729bc-241">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="729bc-241">TemperatureCelsius</span></span>| <span data-ttu-id="729bc-242">25</span><span class="sxs-lookup"><span data-stu-id="729bc-242">25</span></span> |
| <span data-ttu-id="729bc-243">概要</span><span class="sxs-lookup"><span data-stu-id="729bc-243">Summary</span></span>| <span data-ttu-id="729bc-244">null</span><span class="sxs-lookup"><span data-stu-id="729bc-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="729bc-245">この設定は、シリアル化と逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="729bc-246">逆シリアル化に対する影響については、「[逆シリアル化するときに null を無視する](#ignore-null-when-deserializing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-246">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="729bc-247">文字エンコードのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="729bc-247">Customize character encoding</span></span>

<span data-ttu-id="729bc-248">既定では、シリアライザーは ASCII 以外のすべての文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="729bc-248">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="729bc-249">つまり、`xxxx` が文字の Unicode コードである `\uxxxx` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="729bc-249">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="729bc-250">たとえば、`Summary` プロパティがキリルжаркоに設定されている場合、次の例に示すように `WeatherForecast` オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-250">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="729bc-251">言語文字セットのシリアル化</span><span class="sxs-lookup"><span data-stu-id="729bc-251">Serialize language character sets</span></span>

<span data-ttu-id="729bc-252">エスケープせずに1つ以上の言語の文字セットをシリアル化するには、次の例に示すように、<xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>のインスタンスを作成するときに[Unicode 範囲](xref:System.Text.Unicode.UnicodeRanges)を指定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-252">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="729bc-253">このコードでは、キリル文字やギリシャ文字はエスケープされません。</span><span class="sxs-lookup"><span data-stu-id="729bc-253">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="729bc-254">`Summary` プロパティがキリルжаркоに設定されている場合、次の例に示すように `WeatherForecast` オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-254">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="729bc-255">エスケープせずにすべての言語セットをシリアル化するには、<xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-255">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="729bc-256">特定の文字のシリアル化</span><span class="sxs-lookup"><span data-stu-id="729bc-256">Serialize specific characters</span></span>

<span data-ttu-id="729bc-257">別の方法として、エスケープせずにを使用して許可する個々の文字を指定する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="729bc-257">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="729bc-258">次の例では、жаркоの最初の2つの文字のみをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="729bc-258">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="729bc-259">上記のコードによって生成される JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-259">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="729bc-260">すべての文字をシリアル化する</span><span class="sxs-lookup"><span data-stu-id="729bc-260">Serialize all characters</span></span>

<span data-ttu-id="729bc-261">エスケープを最小限に抑えるには、次の例に示すように <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-261">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="729bc-262">既定のエンコーダーと比較して、`UnsafeRelaxedJsonEscaping` エンコーダーでは、エスケープ解除された文字を通過できるようにすることが制限されています。</span><span class="sxs-lookup"><span data-stu-id="729bc-262">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="729bc-263">`<`、`>`、`&`、`'`など、HTML に依存する文字はエスケープされません。</span><span class="sxs-lookup"><span data-stu-id="729bc-263">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="729bc-264">XSS または情報漏えい攻撃 (クライアントとサーバーが*文字セット*に対して無効な場合に発生する可能性があります) に対する追加の多層防御は提供されません。</span><span class="sxs-lookup"><span data-stu-id="729bc-264">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="729bc-265">クライアントが結果のペイロードを UTF-8 でエンコードされた JSON として解釈することがわかっている場合にのみ、unsafe エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-265">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="729bc-266">たとえば、サーバーが応答ヘッダー `Content-Type: application/json; charset=utf-8`を送信している場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-266">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="729bc-267">未加工の `UnsafeRelaxedJsonEscaping` 出力が HTML ページまたは `<script>` 要素に出力されないようにします。</span><span class="sxs-lookup"><span data-stu-id="729bc-267">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="729bc-268">派生クラスのプロパティのシリアル化</span><span class="sxs-lookup"><span data-stu-id="729bc-268">Serialize properties of derived classes</span></span>

<span data-ttu-id="729bc-269">コンパイル時にシリアル化する型を指定する場合、ポリモーフィックシリアル化はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="729bc-269">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="729bc-270">たとえば、`WeatherForecast` クラスと派生クラス `WeatherForecastWithWind`があるとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-270">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="729bc-271">また、コンパイル時に `Serialize` メソッドの型引数が `WeatherForecast`であるとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-271">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="729bc-272">このシナリオでは、`weatherForecast` オブジェクトが実際には `WeatherForecastWithWind` オブジェクトであっても、`WindSpeed` プロパティはシリアル化されません。</span><span class="sxs-lookup"><span data-stu-id="729bc-272">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="729bc-273">基本クラスのプロパティのみがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-273">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="729bc-274">この動作は、派生したランタイムによって作成された型でデータが誤って公開されるのを防ぐためのものです。</span><span class="sxs-lookup"><span data-stu-id="729bc-274">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="729bc-275">派生型のプロパティをシリアル化するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-275">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="729bc-276">実行時に型を指定できるようにする <xref:System.Text.Json.JsonSerializer.Serialize%2A> のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-276">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="729bc-277">`object`としてシリアル化するオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="729bc-277">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="729bc-278">前の例のシナリオでは、どちらの方法でも、`WindSpeed` プロパティが JSON 出力に含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="729bc-278">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="729bc-279">ポリモーフィックな逆シリアル化については、「[ポリモーフィックな逆シリアル化のサポート](system-text-json-converters-how-to.md#support-polymorphic-deserialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-279">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="729bc-280">コメントと末尾のコンマを許可する</span><span class="sxs-lookup"><span data-stu-id="729bc-280">Allow comments and trailing commas</span></span>

<span data-ttu-id="729bc-281">JSON では、コメントと末尾のコンマは既定で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-281">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="729bc-282">JSON でコメントを許可するには、<xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> プロパティを `JsonCommentHandling.Skip`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-282">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="729bc-283">また、末尾のコンマを許可するには、<xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-283">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="729bc-284">次の例では、両方を許可する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-284">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-285">次に、コメントと末尾のコンマを含む JSON の例を示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-285">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="729bc-286">大文字と小文字を区別しないプロパティ照合</span><span class="sxs-lookup"><span data-stu-id="729bc-286">Case-insensitive property matching</span></span>

<span data-ttu-id="729bc-287">既定では、逆シリアル化では、JSON とターゲットオブジェクトのプロパティの間で大文字と小文字が区別されるプロパティ名の一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-287">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="729bc-288">この動作を変更するには、<xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-288">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-289">Camel 形式のプロパティ名を持つ JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-289">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="729bc-290">Pascal 形式のプロパティ名を持つ次の型に逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="729bc-290">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="729bc-291">Overflow JSON の処理</span><span class="sxs-lookup"><span data-stu-id="729bc-291">Handle overflow JSON</span></span>

<span data-ttu-id="729bc-292">逆シリアル化中に、対象の型のプロパティで表されないデータを JSON で受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="729bc-292">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="729bc-293">たとえば、対象の型が次のようになっているとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-293">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="729bc-294">逆シリアル化される JSON は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="729bc-294">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="729bc-295">示されている型に表示されている JSON を逆シリアル化すると、`DatesAvailable` と `SummaryWords` のプロパティがなくなり、失われます。</span><span class="sxs-lookup"><span data-stu-id="729bc-295">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="729bc-296">これらのプロパティなどの追加データをキャプチャするには、 [Jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)属性を `Dictionary<string,object>` 型または `Dictionary<string,JsonElement>`型のプロパティに適用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-296">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="729bc-297">前に示した JSON をこのサンプル型に逆シリアル化すると、余分なデータが `ExtensionData` プロパティのキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="729bc-297">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="729bc-298">property</span><span class="sxs-lookup"><span data-stu-id="729bc-298">Property</span></span> |<span data-ttu-id="729bc-299">[値]</span><span class="sxs-lookup"><span data-stu-id="729bc-299">Value</span></span>  |<span data-ttu-id="729bc-300">注</span><span class="sxs-lookup"><span data-stu-id="729bc-300">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="729bc-301">日付</span><span class="sxs-lookup"><span data-stu-id="729bc-301">Date</span></span>    | <span data-ttu-id="729bc-302">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="729bc-302">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="729bc-303">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="729bc-303">TemperatureCelsius</span></span>| <span data-ttu-id="729bc-304">0</span><span class="sxs-lookup"><span data-stu-id="729bc-304">0</span></span> | <span data-ttu-id="729bc-305">大文字と小文字が区別されない (JSON で`temperatureCelsius`) ため、プロパティが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="729bc-305">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="729bc-306">概要</span><span class="sxs-lookup"><span data-stu-id="729bc-306">Summary</span></span> | <span data-ttu-id="729bc-307">熱い</span><span class="sxs-lookup"><span data-stu-id="729bc-307">Hot</span></span> ||
| <span data-ttu-id="729bc-308">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="729bc-308">ExtensionData</span></span> | <span data-ttu-id="729bc-309">temperatureCelsius:25</span><span class="sxs-lookup"><span data-stu-id="729bc-309">temperatureCelsius: 25</span></span> |<span data-ttu-id="729bc-310">大文字と小文字が一致しなかったため、この JSON プロパティは余分で、ディクショナリ内のキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="729bc-310">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="729bc-311">使用可能な日:</span><span class="sxs-lookup"><span data-stu-id="729bc-311">DatesAvailable:</span></span><br>  <span data-ttu-id="729bc-312">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="729bc-312">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="729bc-313">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="729bc-313">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="729bc-314">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-314">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="729bc-315">概要語:</span><span class="sxs-lookup"><span data-stu-id="729bc-315">SummaryWords:</span></span><br><span data-ttu-id="729bc-316">Cool</span><span class="sxs-lookup"><span data-stu-id="729bc-316">Cool</span></span><br><span data-ttu-id="729bc-317">強風</span><span class="sxs-lookup"><span data-stu-id="729bc-317">Windy</span></span><br><span data-ttu-id="729bc-318">Humid</span><span class="sxs-lookup"><span data-stu-id="729bc-318">Humid</span></span> |<span data-ttu-id="729bc-319">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-319">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="729bc-320">ターゲットオブジェクトがシリアル化されると、拡張データのキーと値のペアは、受信 JSON の場合と同様に JSON プロパティになります。</span><span class="sxs-lookup"><span data-stu-id="729bc-320">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="729bc-321">JSON には `ExtensionData` プロパティ名が表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-321">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="729bc-322">この動作により、JSON は、逆シリアル化されない余分なデータを失うことなく、ラウンドトリップを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="729bc-322">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="729bc-323">逆シリアル化時に null を無視する</span><span class="sxs-lookup"><span data-stu-id="729bc-323">Ignore null when deserializing</span></span>

<span data-ttu-id="729bc-324">既定では、JSON のプロパティが null の場合、対象オブジェクト内の対応するプロパティは null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-324">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="729bc-325">場合によっては、ターゲットプロパティに既定値が設定されていて、null 値を使用して既定値をオーバーライドしないことがあります。</span><span class="sxs-lookup"><span data-stu-id="729bc-325">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="729bc-326">たとえば、次のコードがターゲットオブジェクトを表しているとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-326">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="729bc-327">次の JSON が逆シリアル化されたとします。</span><span class="sxs-lookup"><span data-stu-id="729bc-327">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="729bc-328">逆シリアル化後、`WeatherForecastWithDefault` オブジェクトの `Summary` プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="729bc-328">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="729bc-329">この動作を変更するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-329">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-330">このオプションを使用すると、逆シリアル化後に、`WeatherForecastWithDefault` オブジェクトの `Summary` プロパティが既定値の "No summary" になります。</span><span class="sxs-lookup"><span data-stu-id="729bc-330">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="729bc-331">JSON 内の Null 値は、有効な場合にのみ無視されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-331">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="729bc-332">Null 非許容値型に対して Null 値を指定すると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="729bc-332">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="729bc-333">詳細については、GitHub の dotnet/corefx リポジトリの[null 非許容値型に対する40922の問題](https://github.com/dotnet/corefx/issues/40922)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729bc-333">For more information, see [issue 40922 on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="729bc-334">Utf8JsonReader、Utf8JsonWriter、JsonDocument</span><span class="sxs-lookup"><span data-stu-id="729bc-334">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="729bc-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> は、UTF-8 でエンコードされた JSON テキスト用の高パフォーマンス、低割り当て、転送のみのリーダーです。`ReadOnlySpan<byte>` から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="729bc-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="729bc-336">`Utf8JsonReader` は、カスタムパーサーとデシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="729bc-336">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="729bc-337"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドは、内部で `Utf8JsonReader` を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-337">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="729bc-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> は、`String`、`Int32`、`DateTime`などの一般的な .NET 型から、UTF-8 でエンコードされた JSON テキストを書き込むための高パフォーマンスの方法です。</span><span class="sxs-lookup"><span data-stu-id="729bc-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="729bc-339">ライターは、カスタムシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="729bc-339">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="729bc-340"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> メソッドは、内部で `Utf8JsonWriter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="729bc-340">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="729bc-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> は、`Utf8JsonReader`を使用して、読み取り専用ドキュメントオブジェクトモデル (DOM) を構築する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="729bc-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="729bc-342">DOM は、JSON ペイロード内のデータへのランダムアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="729bc-342">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="729bc-343">ペイロードを構成する JSON 要素には、<xref:System.Text.Json.JsonElement> の種類を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="729bc-343">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="729bc-344">`JsonElement` 型は、JSON テキストを共通の .NET 型に変換するための Api と共に配列とオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="729bc-344">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="729bc-345">`JsonDocument` は <xref:System.Text.Json.JsonDocument.RootElement> プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="729bc-345">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="729bc-346">以下のセクションでは、これらのツールを使用して JSON の読み取りと書き込みを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="729bc-346">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="729bc-347">データへのアクセスに JsonDocument を使用する</span><span class="sxs-lookup"><span data-stu-id="729bc-347">Use JsonDocument for access to data</span></span>

<span data-ttu-id="729bc-348">次の例は、JSON 文字列内のデータへのランダムアクセスに <xref:System.Text.Json.JsonDocument> クラスを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="729bc-348">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="729bc-349">上のコードでは以下の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="729bc-349">The preceding code:</span></span>

* <span data-ttu-id="729bc-350">は、分析する JSON が `jsonString`という名前の文字列に含まれていると想定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-350">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="729bc-351">`Grade` プロパティを持つ `Students` 配列内のオブジェクトの平均グレードを計算します。</span><span class="sxs-lookup"><span data-stu-id="729bc-351">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="729bc-352">学年のない学生に対して既定のグレード70を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="729bc-352">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="729bc-353">各イテレーションで `count` 変数をインクリメントして生徒をカウントします。</span><span class="sxs-lookup"><span data-stu-id="729bc-353">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="729bc-354">別の方法として、次の例に示すように <xref:System.Text.Json.JsonElement.GetArrayLength%2A>を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="729bc-354">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="729bc-355">このコードで処理される JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-355">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="729bc-356">JsonDocument を使用した JSON の記述</span><span class="sxs-lookup"><span data-stu-id="729bc-356">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="729bc-357">次の例は、<xref:System.Text.Json.JsonDocument>から JSON を書き込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="729bc-357">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="729bc-358">上のコードでは以下の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="729bc-358">The preceding code:</span></span>

* <span data-ttu-id="729bc-359">JSON ファイルを読み取り、データを `JsonDocument`に読み込み、書式設定された (非常に印刷された) JSON をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="729bc-359">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="729bc-360"><xref:System.Text.Json.JsonDocumentOptions> を使用して、入力 JSON 内のコメントを許可しますが、無視することを指定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-360">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="729bc-361">完了すると、はライターで <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="729bc-361">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="729bc-362">別の方法として、破棄されたときにライターを autoflush することもできます。</span><span class="sxs-lookup"><span data-stu-id="729bc-362">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="729bc-363">コード例によって処理される JSON 入力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-363">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="729bc-364">その結果、次のような整形出力の JSON 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="729bc-364">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="729bc-365">Utf8JsonWriter を使用する</span><span class="sxs-lookup"><span data-stu-id="729bc-365">Use Utf8JsonWriter</span></span>

<span data-ttu-id="729bc-366">次の例は、<xref:System.Text.Json.Utf8JsonWriter> クラスの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="729bc-366">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="729bc-367">Utf8JsonReader を使用する</span><span class="sxs-lookup"><span data-stu-id="729bc-367">Use Utf8JsonReader</span></span>

<span data-ttu-id="729bc-368">次の例は、<xref:System.Text.Json.Utf8JsonReader> クラスの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="729bc-368">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="729bc-369">上記のコードでは、`jsonUtf8` 変数が、UTF-8 としてエンコードされた有効な JSON を含むバイト配列であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="729bc-369">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="729bc-370">Utf8JsonReader を使用してデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="729bc-370">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="729bc-371">次の例は、ファイルを同期的に読み取り、値を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="729bc-371">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="729bc-372">上のコードでは以下の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="729bc-372">The preceding code:</span></span>

* <span data-ttu-id="729bc-373">は、ファイルが UTF-16 としてエンコードされているものと想定し、UTF-8 にトランスコードします。</span><span class="sxs-lookup"><span data-stu-id="729bc-373">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="729bc-374">UTF-8 としてエンコードされたファイルは、次のコードを使用して、`ReadOnlySpan<byte>`に直接読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="729bc-374">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="729bc-375">JSON にオブジェクトの配列が含まれており、各オブジェクトに文字列型の "name" プロパティが含まれていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="729bc-375">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="729bc-376">オブジェクトをカウントし、"大学" で終わるプロパティ値を `name` します。</span><span class="sxs-lookup"><span data-stu-id="729bc-376">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="729bc-377">上記のコードが読み取ることができる JSON のサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="729bc-377">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="729bc-378">結果として生成される概要メッセージは、"2 ~ 4 個の名前が ' 大学 ' で終わっています" です。</span><span class="sxs-lookup"><span data-stu-id="729bc-378">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="729bc-379">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="729bc-379">Additional resources</span></span>

* [<span data-ttu-id="729bc-380">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="729bc-380">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="729bc-381">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="729bc-381">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="729bc-382">System.string のカスタムコンバーターを作成する</span><span class="sxs-lookup"><span data-stu-id="729bc-382">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="729bc-383">System.string での DateTime と DateTimeOffset のサポート</span><span class="sxs-lookup"><span data-stu-id="729bc-383">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="729bc-384">Dotnet/corefx リポジトリに記載されている GitHub の問題 (json 機能-doc)</span><span class="sxs-lookup"><span data-stu-id="729bc-384">GitHub issues in the dotnet/corefx repository labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
