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
ms.openlocfilehash: 3c988a0151f57b67db19f41aeb88c6fb9b808cb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179199"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="0d0be-102">.NET で JSON をシリアル化および逆シリアル化する方法</span><span class="sxs-lookup"><span data-stu-id="0d0be-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d0be-103">JSON シリアル化のドキュメントは構築中です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="0d0be-104">この記事では、すべてのシナリオについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="0d0be-105">詳細については、GitHub の dotnet/corefx リポジトリにある system.string に[関する問題](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)を調べてください。特に、「 [json 機能-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)」というラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="0d0be-106">この記事では、<xref:System.Text.Json> 名前空間を使用して、JavaScript Object Notation (JSON) との間でシリアル化および逆シリアル化を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="0d0be-107">指示とサンプルコードは、ライブラリを直接使用します。 [ASP.NET Core](/aspnet/core/)などのフレームワークでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="0d0be-108">名前空間</span><span class="sxs-lookup"><span data-stu-id="0d0be-108">Namespaces</span></span>

<span data-ttu-id="0d0be-109">@No__t-0 名前空間には、すべてのエントリポイントと主な型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="0d0be-110">@No__t-0 名前空間には、シリアル化と逆シリアル化に固有の高度なシナリオとカスタマイズのための属性と Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="0d0be-111">したがって、この記事に示されているコード例では、次のいずれかまたは両方の `using` ディレクティブが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="0d0be-112">@No__t-0 名前空間の属性は、`System.Text.Json` では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="0d0be-113">.NET オブジェクトを JSON に書き込む方法 (シリアル化)</span><span class="sxs-lookup"><span data-stu-id="0d0be-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="0d0be-114">JSON を文字列に書き込むには、<xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0d0be-115">次の例では、ジェネリック型パラメーターと共にオーバーロードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="0d0be-116">ジェネリック型パラメーターを省略し、代わりにジェネリック型の推定を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="0d0be-117">シリアル化される型の例を次に示します。これには、コレクションと入れ子になったクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="0d0be-118">既定では、JSON 出力が縮小されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="0d0be-119">次の例では、同じ JSON が書式設定されています (空白とインデントで整形されています)。</span><span class="sxs-lookup"><span data-stu-id="0d0be-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="0d0be-120">@No__t-0 のオーバーロードを使用すると、<xref:System.IO.Stream> にシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="0d0be-121">@No__t-0 のオーバーロードの非同期バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="0d0be-122">UTF-8 にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="0d0be-122">Serialize to UTF-8</span></span>

<span data-ttu-id="0d0be-123">UTF-8 にシリアル化するには、<xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="0d0be-124">別の方法として、<xref:System.Text.Json.Utf8JsonWriter> を受け取る @no__t 0 のオーバーロードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="0d0be-125">UTF-8 へのシリアル化は、文字列ベースのメソッドを使用するよりも約 5-10% 高速です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="0d0be-126">違いは、バイト (UTF-8) を文字列 (UTF-16) に変換する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="0d0be-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="0d0be-127">シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="0d0be-127">Serialization behavior</span></span>

* <span data-ttu-id="0d0be-128">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="0d0be-129">[除外するプロパティを指定](#exclude-properties)できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="0d0be-130">[既定のエンコーダー](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)は、非 ascii 文字、ascii 範囲内の HTML を区別する文字、および[JSON 仕様](https://tools.ietf.org/html/rfc8259#section-7)に従ってエスケープする必要がある文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="0d0be-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="0d0be-131">既定では、JSON は縮小されています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-131">By default, JSON is minified.</span></span> <span data-ttu-id="0d0be-132">[JSON はかなり印刷](#serialize-to-formatted-json)できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="0d0be-133">既定では、JSON 名の大文字と小文字の区別は .NET 名と一致します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="0d0be-134">[JSON 名の大文字と小文字](#customize-json-names)の区別をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="0d0be-135">循環参照が検出され、例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="0d0be-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="0d0be-136">詳細については、GitHub の dotnet/corefx リポジトリにある[循環参照に関する問題](https://github.com/dotnet/corefx/issues/38579)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="0d0be-137">現在、フィールドは除外されています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="0d0be-138">サポートされている種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d0be-138">Supported types include:</span></span>

* <span data-ttu-id="0d0be-139">数値型、文字列、ブール値など、JavaScript プリミティブにマップされる .NET プリミティブ。</span><span class="sxs-lookup"><span data-stu-id="0d0be-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="0d0be-140">ユーザー定義の[Plain OLD CLR オブジェクト (POCOs)](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="0d0be-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="0d0be-141">1次元配列とジャグ配列 (`ArrayName[][]`)。</span><span class="sxs-lookup"><span data-stu-id="0d0be-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="0d0be-142">`Dictionary<string,TValue>` `TValue` は `object`、`JsonElement`、または POCO です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="0d0be-143">次の名前空間のコレクション。</span><span class="sxs-lookup"><span data-stu-id="0d0be-143">Collections from the following namespaces.</span></span> <span data-ttu-id="0d0be-144">詳細については、GitHub の dotnet/corefx リポジトリの[コレクションサポートに関する問題](https://github.com/dotnet/corefx/issues/36643)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="0d0be-145">JSON を .NET オブジェクトに読み込む方法 (逆シリアル化)</span><span class="sxs-lookup"><span data-stu-id="0d0be-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="0d0be-146">文字列から逆シリアル化するには、次の例に示すように、<xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="0d0be-147">例については、「 [serialize](#how-to-write-net-objects-to-json-serialize) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="0d0be-148">JSON オブジェクトと .NET オブジェクトは同じですが、方向が逆になっています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="0d0be-149">@No__t-0 のオーバーロードを使用すると、`Stream` から逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="0d0be-150">@No__t-0 のオーバーロードの非同期バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="0d0be-151">UTF-8 からの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="0d0be-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="0d0be-152">UTF-8 から逆シリアル化するには、次の例に示すように、`Utf8JsonReader` または `ReadOnlySpan<byte>` を受け取る @no__t 0 のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="0d0be-153">逆シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="0d0be-153">Deserialization behavior</span></span>

* <span data-ttu-id="0d0be-154">既定では、プロパティ名の照合では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="0d0be-155">[大文字と小文字を区別](#case-insensitive-property-matching)しないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="0d0be-156">JSON に読み取り専用プロパティの値が含まれている場合、この値は無視され、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="0d0be-157">パラメーターなしのコンストラクターを使用しない参照型への逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="0d0be-158">変更できないオブジェクトまたは読み取り専用プロパティへの逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="0d0be-159">詳細については、変更できない[オブジェクトのサポートに関する](https://github.com/dotnet/corefx/issues/38569)github の問題と、github の dotnet/corefx リポジトリの[読み取り専用プロパティのサポート](https://github.com/dotnet/corefx/issues/38163)に関する問題を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="0d0be-160">既定では、列挙型は数値としてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="0d0be-161">フィールドはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-161">Fields aren't supported.</span></span>
* <span data-ttu-id="0d0be-162">既定では、JSON のコメントまたは末尾のコンマによって例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="0d0be-163">必要に応じ[て、コメントと末尾のコンマを許可](#allow-comments-and-trailing-commas)できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="0d0be-164">[既定の最大の深さ](xref:System.Text.Json.JsonReaderOptions.MaxDepth)は64です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="0d0be-165">書式設定された JSON にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="0d0be-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="0d0be-166">JSON 出力を整形するには、<xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-167">シリアル化される型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-167">Here's an example type to be serialized and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="0d0be-168">コメントと末尾のコンマを許可する</span><span class="sxs-lookup"><span data-stu-id="0d0be-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="0d0be-169">JSON では、既定でコメントと末尾のコンマは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="0d0be-170">JSON でコメントを許可するには、<xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> プロパティを `JsonCommentHandling.Skip` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="0d0be-171">また、末尾のコンマを許可するには、<xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="0d0be-172">次の例では、両方を許可する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="0d0be-173">次に、コメントと末尾のコンマを含む JSON の例を示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="0d0be-174">JSON 名のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0d0be-174">Customize JSON names</span></span>

<span data-ttu-id="0d0be-175">既定では、プロパティ名とディクショナリキーは、大文字と小文字を含め、JSON の出力では変更されません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="0d0be-176">このセクションでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-176">This section explains how to:</span></span>

* <span data-ttu-id="0d0be-177">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0d0be-177">Customize individual property names</span></span>
* <span data-ttu-id="0d0be-178">すべてのプロパティ名を camel 形式に変換します</span><span class="sxs-lookup"><span data-stu-id="0d0be-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="0d0be-179">カスタムプロパティの名前付けポリシーを実装する</span><span class="sxs-lookup"><span data-stu-id="0d0be-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="0d0be-180">ディクショナリキーを camel 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="0d0be-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="0d0be-181">現在、列挙型からキャメルケースへの自動変換はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="0d0be-182">詳細については、GitHub の dotnet/corefx リポジトリでの[列挙型 camel ケースのサポートに関する問題](https://github.com/dotnet/corefx/issues/37725)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="0d0be-183">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0d0be-183">Customize individual property names</span></span>

<span data-ttu-id="0d0be-184">個々のプロパティの名前を設定するには、 [[Jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="0d0be-185">シリアル化し、結果として得られる JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-185">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0d0be-186">この属性によって設定されるプロパティ名:</span><span class="sxs-lookup"><span data-stu-id="0d0be-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="0d0be-187">シリアル化と逆シリアル化の両方の方向で適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="0d0be-188">は、プロパティの名前付けポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="0d0be-189">すべての JSON プロパティ名にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="0d0be-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="0d0be-190">すべての JSON プロパティ名にキャメルケースを使用するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> を `JsonNamingPolicy.CamelCase` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-191">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-191">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0d0be-192">Camel 形式のプロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="0d0be-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="0d0be-193">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="0d0be-194">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="0d0be-195">カスタム JSON プロパティの名前付けポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="0d0be-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="0d0be-196">カスタム JSON プロパティの名前付けポリシーを使用するには、次の例に示すように、<xref:System.Text.Json.JsonNamingPolicy> から派生し、<xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> メソッドをオーバーライドするクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="0d0be-197">次に、<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> プロパティを名前付けポリシークラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-198">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-198">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0d0be-199">JSON プロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="0d0be-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="0d0be-200">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="0d0be-201">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="0d0be-202">Camel ケースディクショナリキー</span><span class="sxs-lookup"><span data-stu-id="0d0be-202">Camel case dictionary keys</span></span>

<span data-ttu-id="0d0be-203">シリアル化するオブジェクトのプロパティの型が `Dictionary<string,TValue>` の場合、`string` キーを camel 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="0d0be-204">これを行うには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> を `JsonNamingPolicy.CamelCase` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-205">シリアル化し、JSON 出力を行うオブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="0d0be-206">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-206">Property</span></span> |<span data-ttu-id="0d0be-207">値</span><span class="sxs-lookup"><span data-stu-id="0d0be-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="0d0be-208">date</span><span class="sxs-lookup"><span data-stu-id="0d0be-208">Date</span></span>    | <span data-ttu-id="0d0be-209">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="0d0be-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="0d0be-210">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="0d0be-210">TemperatureC</span></span>| <span data-ttu-id="0d0be-211">25</span><span class="sxs-lookup"><span data-stu-id="0d0be-211">25</span></span> |
| <span data-ttu-id="0d0be-212">まとめ</span><span class="sxs-lookup"><span data-stu-id="0d0be-212">Summary</span></span>| <span data-ttu-id="0d0be-213">熱い</span><span class="sxs-lookup"><span data-stu-id="0d0be-213">Hot</span></span>|
| <span data-ttu-id="0d0be-214">TemperatureRanges</span><span class="sxs-lookup"><span data-stu-id="0d0be-214">TemperatureRanges</span></span> | <span data-ttu-id="0d0be-215">コールド、20</span><span class="sxs-lookup"><span data-stu-id="0d0be-215">Cold, 20</span></span><br><span data-ttu-id="0d0be-216">ホット、40</span><span class="sxs-lookup"><span data-stu-id="0d0be-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="0d0be-217">Camel 形式の名前付けポリシーは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="0d0be-218">プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="0d0be-218">Exclude properties</span></span>

<span data-ttu-id="0d0be-219">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="0d0be-220">一部のオプションが JSON 出力に表示されないようにするには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0be-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="0d0be-221">ここでは、を除外する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="0d0be-222">個々のプロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-222">Individual properties</span></span>
* <span data-ttu-id="0d0be-223">すべての読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-223">All read-only properties</span></span>
* <span data-ttu-id="0d0be-224">すべての null 値プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="0d0be-225">個々のプロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="0d0be-225">Exclude individual properties</span></span>

<span data-ttu-id="0d0be-226">個々のプロパティを無視するには、 [[Jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="0d0be-227">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-227">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="0d0be-228">すべての読み取り専用プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="0d0be-228">Exclude all read-only properties</span></span>

<span data-ttu-id="0d0be-229">すべての読み取り専用プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-230">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-230">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="0d0be-231">このオプションは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-231">This option applies only to serialization.</span></span> <span data-ttu-id="0d0be-232">逆シリアル化中、読み取り専用プロパティは既定では無視されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="0d0be-233">パブリックゲッターが含まれていてもパブリック setter がない場合、プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="0d0be-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="0d0be-234">すべての null 値プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="0d0be-234">Exclude all null value properties</span></span>

<span data-ttu-id="0d0be-235">すべての null 値プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0d0be-236">シリアル化し、JSON 出力を行うオブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="0d0be-237">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-237">Property</span></span> |<span data-ttu-id="0d0be-238">値</span><span class="sxs-lookup"><span data-stu-id="0d0be-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="0d0be-239">date</span><span class="sxs-lookup"><span data-stu-id="0d0be-239">Date</span></span>    | <span data-ttu-id="0d0be-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="0d0be-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="0d0be-241">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="0d0be-241">TemperatureC</span></span>| <span data-ttu-id="0d0be-242">25</span><span class="sxs-lookup"><span data-stu-id="0d0be-242">25</span></span> |
| <span data-ttu-id="0d0be-243">まとめ</span><span class="sxs-lookup"><span data-stu-id="0d0be-243">Summary</span></span>| <span data-ttu-id="0d0be-244">null</span><span class="sxs-lookup"><span data-stu-id="0d0be-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="0d0be-245">この設定は、シリアル化と逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="0d0be-246">逆シリアル化中、JSON 内の null 値は、有効な場合にのみ無視されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="0d0be-247">Null 非許容値型に対して Null 値を指定すると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="0d0be-248">詳細については、GitHub の dotnet/corefx リポジトリにある[null 非許容の値型に関する問題](https://github.com/dotnet/corefx/issues/40922)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="0d0be-249">大文字と小文字を区別しないプロパティ照合</span><span class="sxs-lookup"><span data-stu-id="0d0be-249">Case-insensitive property matching</span></span>

<span data-ttu-id="0d0be-250">既定では、逆シリアル化では、JSON とターゲットオブジェクトのプロパティの間で大文字と小文字が区別されるプロパティ名の一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="0d0be-251">この動作を変更するには、<xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="0d0be-252">Camel 形式のプロパティ名を持つ JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="0d0be-253">Pascal 形式のプロパティ名を持つ次の型に逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="0d0be-254">派生クラスのプロパティを含める</span><span class="sxs-lookup"><span data-stu-id="0d0be-254">Include properties of derived classes</span></span>

<span data-ttu-id="0d0be-255">コンパイル時にシリアル化する型を指定する場合、ポリモーフィックシリアル化はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="0d0be-256">たとえば、@no__t 0 クラスと派生クラス `WeatherForecastWithWind` があるとします。</span><span class="sxs-lookup"><span data-stu-id="0d0be-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="0d0be-257">また、コンパイル時にに渡される型またはによって推論される型が、`WeatherForecast` であるとします。 @no__t は、</span><span class="sxs-lookup"><span data-stu-id="0d0be-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="0d0be-258">このシナリオでは、@no__t 1 のオブジェクトが実際に @no__t 2 のオブジェクトであっても、`WindSpeed` プロパティはシリアル化されません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="0d0be-259">基本クラスのプロパティのみがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="0d0be-260">この動作は、派生したランタイムによって作成された型でデータが誤って公開されるのを防ぐためのものです。</span><span class="sxs-lookup"><span data-stu-id="0d0be-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="0d0be-261">派生型のプロパティをシリアル化するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="0d0be-262">実行時に型を指定できるように、<xref:System.Text.Json.JsonSerializer.Serialize%2A> のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="0d0be-263">@No__t-0 としてシリアル化するオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="0d0be-264">前の例のシナリオでは、両方の方法で `WindSpeed` プロパティが JSON 出力に含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="0d0be-265">Overflow JSON の処理</span><span class="sxs-lookup"><span data-stu-id="0d0be-265">Handle overflow JSON</span></span>

<span data-ttu-id="0d0be-266">逆シリアル化中に、対象の型のプロパティで表されないデータを JSON で受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0be-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="0d0be-267">たとえば、対象の型が次のようになっているとします。</span><span class="sxs-lookup"><span data-stu-id="0d0be-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="0d0be-268">逆シリアル化される JSON は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d0be-268">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="0d0be-269">示されている型に示されている JSON を逆シリアル化すると、`DatesAvailable` および `SummaryWords` の各プロパティには何も表示されなくなり、失われます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="0d0be-270">これらのプロパティなどの追加データをキャプチャするには、 [Jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)属性を型 `Dictionary<string,object>` または `Dictionary<string,JsonElement>` のプロパティに適用します。</span><span class="sxs-lookup"><span data-stu-id="0d0be-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="0d0be-271">前に示した JSON をこのサンプル型に逆シリアル化すると、余分なデータが `ExtensionData` プロパティのキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="0d0be-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="0d0be-272">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0d0be-272">Property</span></span> |<span data-ttu-id="0d0be-273">値</span><span class="sxs-lookup"><span data-stu-id="0d0be-273">Value</span></span>  |<span data-ttu-id="0d0be-274">メモ</span><span class="sxs-lookup"><span data-stu-id="0d0be-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="0d0be-275">date</span><span class="sxs-lookup"><span data-stu-id="0d0be-275">Date</span></span>    | <span data-ttu-id="0d0be-276">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="0d0be-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="0d0be-277">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="0d0be-277">TemperatureC</span></span>| <span data-ttu-id="0d0be-278">0</span><span class="sxs-lookup"><span data-stu-id="0d0be-278">0</span></span> | <span data-ttu-id="0d0be-279">大文字と小文字が区別されない (JSON の `temperatureC`) ため、プロパティが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="0d0be-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="0d0be-280">まとめ</span><span class="sxs-lookup"><span data-stu-id="0d0be-280">Summary</span></span> | <span data-ttu-id="0d0be-281">熱い</span><span class="sxs-lookup"><span data-stu-id="0d0be-281">Hot</span></span> ||
| <span data-ttu-id="0d0be-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="0d0be-282">ExtensionData</span></span> | <span data-ttu-id="0d0be-283">temperatureC:25</span><span class="sxs-lookup"><span data-stu-id="0d0be-283">temperatureC: 25</span></span> |<span data-ttu-id="0d0be-284">大文字と小文字が一致しなかったため、この JSON プロパティは余分で、ディクショナリ内のキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="0d0be-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="0d0be-285">使用可能な日:</span><span class="sxs-lookup"><span data-stu-id="0d0be-285">DatesAvailable:</span></span><br>  <span data-ttu-id="0d0be-286">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="0d0be-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="0d0be-287">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="0d0be-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="0d0be-288">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="0d0be-289">概要語:</span><span class="sxs-lookup"><span data-stu-id="0d0be-289">SummaryWords:</span></span><br><span data-ttu-id="0d0be-290">Cool</span><span class="sxs-lookup"><span data-stu-id="0d0be-290">Cool</span></span><br><span data-ttu-id="0d0be-291">強風</span><span class="sxs-lookup"><span data-stu-id="0d0be-291">Windy</span></span><br><span data-ttu-id="0d0be-292">Humid</span><span class="sxs-lookup"><span data-stu-id="0d0be-292">Humid</span></span> |<span data-ttu-id="0d0be-293">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="0d0be-294">ターゲットオブジェクトがシリアル化されると、拡張データのキーと値のペアは、受信 JSON の場合と同様に JSON プロパティになります。</span><span class="sxs-lookup"><span data-stu-id="0d0be-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="0d0be-295">@No__t-0 のプロパティ名が JSON に表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0be-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="0d0be-296">この動作により、JSON は、逆シリアル化されない余分なデータを失うことなく、ラウンドトリップを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0d0be-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="0d0be-297">Utf8JsonWriter を直接使用する</span><span class="sxs-lookup"><span data-stu-id="0d0be-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="0d0be-298">次の例は、<xref:System.Text.Json.Utf8JsonWriter> クラスを直接使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="0d0be-299">Utf8JsonReader を直接使用する</span><span class="sxs-lookup"><span data-stu-id="0d0be-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="0d0be-300">次の例は、<xref:System.Text.Json.Utf8JsonReader> クラスを直接使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="0d0be-301">このコードでは、@no__t 0 の変数が、UTF-8 としてエンコードされた有効な JSON を含むバイト配列であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0d0be-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

## <a name="additional-resources"></a><span data-ttu-id="0d0be-302">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="0d0be-302">Additional resources</span></span>

* [<span data-ttu-id="0d0be-303">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="0d0be-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0d0be-304">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="0d0be-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="0d0be-305">System.string での DateTime と DateTimeOffset のサポート</span><span class="sxs-lookup"><span data-stu-id="0d0be-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
