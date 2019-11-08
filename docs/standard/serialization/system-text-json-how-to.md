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
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740435"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="8c508-102">.NET で JSON をシリアル化および逆シリアル化する方法</span><span class="sxs-lookup"><span data-stu-id="8c508-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c508-103">JSON シリアル化のドキュメントは構築中です。</span><span class="sxs-lookup"><span data-stu-id="8c508-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="8c508-104">この記事では、すべてのシナリオについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="8c508-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="8c508-105">詳細については、GitHub の dotnet/corefx リポジトリにある system.string に[関する問題](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)を調べてください。特に、「 [json 機能-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)」というラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="8c508-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="8c508-106">この記事では、<xref:System.Text.Json> 名前空間を使用して、JavaScript Object Notation (JSON) との間でシリアル化および逆シリアル化を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c508-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8c508-107">指示とサンプルコードは、ライブラリを直接使用します。 [ASP.NET Core](/aspnet/core/)などのフレームワークでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="8c508-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="8c508-108">名前空間</span><span class="sxs-lookup"><span data-stu-id="8c508-108">Namespaces</span></span>

<span data-ttu-id="8c508-109"><xref:System.Text.Json> 名前空間には、すべてのエントリポイントと主要な型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c508-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="8c508-110"><xref:System.Text.Json.Serialization> 名前空間には、シリアル化と逆シリアル化に固有の高度なシナリオとカスタマイズのための属性と Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c508-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="8c508-111">この記事に示されているコード例では、次のいずれかまたは両方の名前空間に `using` ディレクティブが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c508-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="8c508-112"><xref:System.Runtime.Serialization> 名前空間の属性は、現在 `System.Text.Json`ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="8c508-113">.NET オブジェクトを JSON に書き込む方法 (シリアル化)</span><span class="sxs-lookup"><span data-stu-id="8c508-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="8c508-114">JSON を文字列またはファイルに書き込むには、<xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8c508-115">次の例では、JSON を文字列として作成します。</span><span class="sxs-lookup"><span data-stu-id="8c508-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="8c508-116">次の例では、同期コードを使用して JSON ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c508-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="8c508-117">次の例では、非同期コードを使用して JSON ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c508-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="8c508-118">前の例では、シリアル化する型の型の推定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="8c508-119">`Serialize()` のオーバーロードは、ジェネリック型パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c508-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="8c508-120">シリアル化の例</span><span class="sxs-lookup"><span data-stu-id="8c508-120">Serialization example</span></span>

<span data-ttu-id="8c508-121">コレクションと入れ子になったクラスを含む型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-121">Here's an example type that contains collections and nested classes:</span></span>

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

<span data-ttu-id="8c508-122">前の型のインスタンスをシリアル化した JSON 出力は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="8c508-123">既定では、JSON 出力が縮小されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="8c508-124">次の例では、同じ JSON が書式設定されています (空白とインデントで整形されています)。</span><span class="sxs-lookup"><span data-stu-id="8c508-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="8c508-125">UTF-8 にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="8c508-125">Serialize to UTF-8</span></span>

<span data-ttu-id="8c508-126">UTF-8 にシリアル化するには、<xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="8c508-127"><xref:System.Text.Json.Utf8JsonWriter> を受け取る <xref:System.Text.Json.JsonSerializer.Serialize%2A> のオーバーロードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="8c508-128">UTF-8 へのシリアル化は、文字列ベースのメソッドを使用するよりも約5-10% 高速です。</span><span class="sxs-lookup"><span data-stu-id="8c508-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="8c508-129">違いは、バイト (UTF-8) を文字列 (UTF-16) に変換する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="8c508-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="8c508-130">シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="8c508-130">Serialization behavior</span></span>

* <span data-ttu-id="8c508-131">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="8c508-132">[除外するプロパティを指定](#exclude-properties-from-serialization)できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="8c508-133">[既定のエンコーダー](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)は、非 ascii 文字、ascii 範囲内の HTML を区別する文字、および[JSON 仕様](https://tools.ietf.org/html/rfc8259#section-7)に従ってエスケープする必要がある文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="8c508-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="8c508-134">既定では、JSON は縮小されています。</span><span class="sxs-lookup"><span data-stu-id="8c508-134">By default, JSON is minified.</span></span> <span data-ttu-id="8c508-135">[JSON はかなり印刷](#serialize-to-formatted-json)できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="8c508-136">既定では、JSON 名の大文字と小文字の区別は .NET 名と一致します。</span><span class="sxs-lookup"><span data-stu-id="8c508-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="8c508-137">[JSON 名の大文字と小文字](#customize-json-names-and-values)の区別をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8c508-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="8c508-138">循環参照が検出され、例外がスローされました。</span><span class="sxs-lookup"><span data-stu-id="8c508-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="8c508-139">詳細については、GitHub の dotnet/corefx リポジトリにある[循環参照に関する問題](https://github.com/dotnet/corefx/issues/38579)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="8c508-140">現在、フィールドは除外されています。</span><span class="sxs-lookup"><span data-stu-id="8c508-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="8c508-141">サポートされている種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c508-141">Supported types include:</span></span>

* <span data-ttu-id="8c508-142">数値型、文字列、ブール値など、JavaScript プリミティブにマップされる .NET プリミティブ。</span><span class="sxs-lookup"><span data-stu-id="8c508-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="8c508-143">ユーザー定義の[Plain OLD CLR オブジェクト (POCOs)](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="8c508-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="8c508-144">1次元配列とジャグ配列 (`ArrayName[][]`)。</span><span class="sxs-lookup"><span data-stu-id="8c508-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="8c508-145">`Dictionary<string,TValue>` `TValue` が `object`、`JsonElement`、または POCO です。</span><span class="sxs-lookup"><span data-stu-id="8c508-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="8c508-146">次の名前空間のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8c508-146">Collections from the following namespaces.</span></span> <span data-ttu-id="8c508-147">詳細については、GitHub の dotnet/corefx リポジトリの[コレクションサポートに関する問題](https://github.com/dotnet/corefx/issues/36643)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="8c508-148">[カスタムコンバーターを実装](system-text-json-converters-how-to.md)して、追加の型を処理したり、組み込みのコンバーターでサポートされていない機能を提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c508-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="8c508-149">JSON を .NET オブジェクトに読み込む方法 (逆シリアル化)</span><span class="sxs-lookup"><span data-stu-id="8c508-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="8c508-150">文字列またはファイルから逆シリアル化するには、<xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8c508-151">次の例では、文字列から JSON を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8c508-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="8c508-152">同期コードを使用してファイルから逆シリアル化するには、次の例に示すように、ファイルを文字列に読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8c508-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="8c508-153">非同期コードを使用してファイルから逆シリアル化するには、<xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="8c508-154">型とそれに対応する JSON の例については、「[シリアル化の例](#serialization-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="8c508-155">UTF-8 からの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="8c508-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="8c508-156">UTF-8 から逆シリアル化するには、次の例に示すように、`Utf8JsonReader` または `ReadOnlySpan<byte>`を受け取る <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> オーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="8c508-157">この例では、JSON が jsonUtf8Bytes という名前のバイト配列にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8c508-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="8c508-158">逆シリアル化の動作</span><span class="sxs-lookup"><span data-stu-id="8c508-158">Deserialization behavior</span></span>

* <span data-ttu-id="8c508-159">既定では、プロパティ名の照合では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="8c508-160">[大文字と小文字を区別](#case-insensitive-property-matching)しないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="8c508-161">JSON に読み取り専用プロパティの値が含まれている場合、この値は無視され、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="8c508-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="8c508-162">パラメーターなしのコンストラクターを使用しない参照型への逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="8c508-163">変更できないオブジェクトまたは読み取り専用プロパティへの逆シリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="8c508-164">詳細については、変更できない[オブジェクトのサポートに関する](https://github.com/dotnet/corefx/issues/38569)github の問題と、github の dotnet/corefx リポジトリの[読み取り専用プロパティのサポート](https://github.com/dotnet/corefx/issues/38163)に関する問題を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="8c508-165">既定では、列挙型は数値としてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8c508-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="8c508-166">[列挙型名を文字列としてシリアル化](#enums-as-strings)できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="8c508-167">フィールドはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-167">Fields aren't supported.</span></span>
* <span data-ttu-id="8c508-168">既定では、JSON のコメントまたは末尾のコンマによって例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8c508-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="8c508-169">[コメントと末尾のコンマを許可](#allow-comments-and-trailing-commas)できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="8c508-170">[既定の最大の深さ](xref:System.Text.Json.JsonReaderOptions.MaxDepth)は64です。</span><span class="sxs-lookup"><span data-stu-id="8c508-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="8c508-171">組み込みのコンバーターでサポートされていない機能を提供するために、[カスタムコンバーターを実装](system-text-json-converters-how-to.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="8c508-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="8c508-172">書式設定された JSON にシリアル化する</span><span class="sxs-lookup"><span data-stu-id="8c508-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="8c508-173">JSON 出力を整形するには、<xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-174">シリアル化され、整形された JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

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

## <a name="customize-json-names-and-values"></a><span data-ttu-id="8c508-175">JSON の名前と値をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8c508-175">Customize JSON names and values</span></span>

<span data-ttu-id="8c508-176">既定では、プロパティ名とディクショナリキーは、大文字と小文字を含め、JSON の出力では変更されません。</span><span class="sxs-lookup"><span data-stu-id="8c508-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="8c508-177">列挙値は数値として表されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="8c508-178">このセクションでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c508-178">This section explains how to:</span></span>

* <span data-ttu-id="8c508-179">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8c508-179">Customize individual property names</span></span>
* <span data-ttu-id="8c508-180">すべてのプロパティ名を camel 形式に変換します</span><span class="sxs-lookup"><span data-stu-id="8c508-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="8c508-181">カスタムプロパティの名前付けポリシーを実装する</span><span class="sxs-lookup"><span data-stu-id="8c508-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="8c508-182">ディクショナリキーを camel 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="8c508-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="8c508-183">列挙型を文字列および camel 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="8c508-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="8c508-184">JSON プロパティの名前と値の特別な処理を必要とするその他のシナリオでは、[カスタムコンバーターを実装](system-text-json-converters-how-to.md)できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="8c508-185">個々のプロパティ名をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8c508-185">Customize individual property names</span></span>

<span data-ttu-id="8c508-186">個々のプロパティの名前を設定するには、 [[Jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="8c508-187">シリアル化し、結果として得られる JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-187">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="8c508-188">この属性によって設定されるプロパティ名:</span><span class="sxs-lookup"><span data-stu-id="8c508-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="8c508-189">シリアル化と逆シリアル化の両方の方向で適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="8c508-190">は、プロパティの名前付けポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="8c508-191">すべての JSON プロパティ名にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="8c508-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="8c508-192">すべての JSON プロパティ名にキャメルケースを使用するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> を `JsonNamingPolicy.CamelCase`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-193">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8c508-194">Camel 形式のプロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="8c508-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="8c508-195">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8c508-196">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="8c508-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8c508-197">このため、この例の JSON プロパティ名 `Wind` は camel 形式ではありません。</span><span class="sxs-lookup"><span data-stu-id="8c508-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="8c508-198">カスタム JSON プロパティの名前付けポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="8c508-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="8c508-199">カスタム JSON プロパティの名前付けポリシーを使用するには、次の例に示すように、<xref:System.Text.Json.JsonNamingPolicy> から派生するクラスを作成し、<xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="8c508-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="8c508-200">次に、[<xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>] プロパティを名前付けポリシークラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-201">シリアル化と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-201">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="8c508-202">JSON プロパティの名前付けポリシー:</span><span class="sxs-lookup"><span data-stu-id="8c508-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="8c508-203">シリアル化および逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8c508-204">は `[JsonPropertyName]` 属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="8c508-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8c508-205">このため、この例の JSON プロパティ名 `Wind` は大文字ではありません。</span><span class="sxs-lookup"><span data-stu-id="8c508-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="8c508-206">Camel ケースディクショナリキー</span><span class="sxs-lookup"><span data-stu-id="8c508-206">Camel case dictionary keys</span></span>

<span data-ttu-id="8c508-207">シリアル化するオブジェクトのプロパティが `Dictionary<string,TValue>`型である場合は、`string` キーを camel 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="8c508-208">これを行うには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> を `JsonNamingPolicy.CamelCase`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-209">キーと値の `"ColdMinTemp", 20` ペアを持つ `TemperatureRanges` という名前のディクショナリを使用してオブジェクトをシリアル化すると `"HotMinTemp", 40`、次の例のように JSON 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="8c508-210">ディクショナリキーの camel ケースの名前付けポリシーは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="8c508-211">ディクショナリを逆シリアル化すると、`DictionaryKeyPolicy`に `JsonNamingPolicy.CamelCase` を指定した場合でも、キーが JSON ファイルと一致します。</span><span class="sxs-lookup"><span data-stu-id="8c508-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="8c508-212">列挙 (文字列として)</span><span class="sxs-lookup"><span data-stu-id="8c508-212">Enums as strings</span></span>

<span data-ttu-id="8c508-213">既定では、列挙型は数値としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="8c508-214">列挙型名を文字列としてシリアル化するには、<xref:System.Text.Json.Serialization.JsonStringEnumConverter>を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="8c508-215">たとえば、列挙型を持つ次のクラスをシリアル化する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="8c508-216">概要が `Hot`の場合、既定では、シリアル化された JSON の数値は3になります。</span><span class="sxs-lookup"><span data-stu-id="8c508-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="8c508-217">次のサンプルコードでは、代わりに列挙型名をシリアル化し、camel 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="8c508-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="8c508-218">結果として得られる JSON は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="8c508-219">文字列としての列挙型のサポートは、次の例に示すように、逆シリアル化にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="8c508-220">シリアル化からプロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="8c508-220">Exclude properties from serialization</span></span>

<span data-ttu-id="8c508-221">既定では、すべてのパブリックプロパティがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="8c508-222">一部のオプションが JSON 出力に表示されないようにするには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8c508-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="8c508-223">ここでは、を除外する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c508-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="8c508-224">個々のプロパティ</span><span class="sxs-lookup"><span data-stu-id="8c508-224">Individual properties</span></span>
* <span data-ttu-id="8c508-225">すべての読み取り専用プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c508-225">All read-only properties</span></span>
* <span data-ttu-id="8c508-226">すべての null 値プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c508-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="8c508-227">個々のプロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="8c508-227">Exclude individual properties</span></span>

<span data-ttu-id="8c508-228">個々のプロパティを無視するには、 [[Jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="8c508-229">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-229">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="8c508-230">すべての読み取り専用プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="8c508-230">Exclude all read-only properties</span></span>

<span data-ttu-id="8c508-231">パブリックゲッターが含まれていてもパブリック setter がない場合、プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="8c508-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="8c508-232">すべての読み取り専用プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-233">シリアル化する型と JSON 出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-233">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="8c508-234">このオプションは、シリアル化にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-234">This option applies only to serialization.</span></span> <span data-ttu-id="8c508-235">逆シリアル化中、読み取り専用プロパティは既定では無視されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="8c508-236">すべての null 値プロパティを除外する</span><span class="sxs-lookup"><span data-stu-id="8c508-236">Exclude all null value properties</span></span>

<span data-ttu-id="8c508-237">すべての null 値プロパティを除外するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-238">シリアル化し、JSON 出力を行うオブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="8c508-239">property</span><span class="sxs-lookup"><span data-stu-id="8c508-239">Property</span></span> |<span data-ttu-id="8c508-240">[値]</span><span class="sxs-lookup"><span data-stu-id="8c508-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="8c508-241">日付</span><span class="sxs-lookup"><span data-stu-id="8c508-241">Date</span></span>    | <span data-ttu-id="8c508-242">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8c508-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="8c508-243">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="8c508-243">TemperatureC</span></span>| <span data-ttu-id="8c508-244">25</span><span class="sxs-lookup"><span data-stu-id="8c508-244">25</span></span> |
| <span data-ttu-id="8c508-245">まとめ</span><span class="sxs-lookup"><span data-stu-id="8c508-245">Summary</span></span>| <span data-ttu-id="8c508-246">null</span><span class="sxs-lookup"><span data-stu-id="8c508-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="8c508-247">この設定は、シリアル化と逆シリアル化に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="8c508-248">逆シリアル化に対する影響については、「[逆シリアル化するときに null を無視する](#ignore-null-when-deserializing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="8c508-249">文字エンコードのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8c508-249">Customize character encoding</span></span>

<span data-ttu-id="8c508-250">既定では、シリアライザーは ASCII 以外のすべての文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="8c508-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="8c508-251">つまり、`xxxxx` が文字の Unicode コードである `\uxxxx` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8c508-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="8c508-252">たとえば、`Summary` プロパティがキリルжаркоに設定されている場合、次の例に示すように `WeatherForecast` オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="8c508-253">言語文字セットのシリアル化</span><span class="sxs-lookup"><span data-stu-id="8c508-253">Serialize language character sets</span></span>

<span data-ttu-id="8c508-254">1つ以上の言語の文字セットをシリアル化するには、次の例に示すように、<xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>のインスタンスを作成するときに[Unicode 範囲](xref:System.Text.Unicode.UnicodeRanges)を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-255">このコードは、キリル文字とギリシャ文字をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="8c508-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="8c508-256">キリル文字は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="8c508-257">すべての言語を指定するには、<xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="8c508-258">特定の文字のシリアル化</span><span class="sxs-lookup"><span data-stu-id="8c508-258">Serialize specific characters</span></span>

<span data-ttu-id="8c508-259">別の方法として、エスケープせずにを使用して許可する個々の文字を指定する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="8c508-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="8c508-260">次の例では、жаркоの最初の2つの文字のみをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="8c508-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8c508-261">上記のコードによって生成される JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="8c508-262">すべての文字をシリアル化する</span><span class="sxs-lookup"><span data-stu-id="8c508-262">Serialize all characters</span></span>

<span data-ttu-id="8c508-263">エスケープを最小限に抑えるには、次の例に示すように <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="8c508-264">既定のエンコーダーとは異なり、`UnsafeRelaxedJsonEscaping` エンコーダーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="8c508-265">では、`<`、`>`、`&`、`'`など、HTML に依存する文字はエスケープされません。</span><span class="sxs-lookup"><span data-stu-id="8c508-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="8c508-266">では、クライアントとサーバーが*文字セット*に対して無効になった場合に発生する可能性のある、XSS または情報漏えい攻撃に対する追加の多層防御は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="8c508-267">は、エスケープ解除された文字の通過を許可する既定のエンコーダーよりも制限があります。</span><span class="sxs-lookup"><span data-stu-id="8c508-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="8c508-268">クライアントが結果のペイロードを UTF-8 でエンコードされた JSON として解釈することがわかっている場合にのみ、unsafe エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="8c508-269">たとえば、サーバーが応答ヘッダー `Content-Type: application/json; charset=utf-8`を送信している場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="8c508-270">未加工の `UnsafeRelaxedJsonEscaping` 出力が HTML ページまたは `<script>` 要素に出力されないようにします。</span><span class="sxs-lookup"><span data-stu-id="8c508-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="8c508-271">派生クラスのプロパティのシリアル化</span><span class="sxs-lookup"><span data-stu-id="8c508-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="8c508-272">コンパイル時にシリアル化する型を指定する場合、ポリモーフィックシリアル化はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8c508-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="8c508-273">たとえば、`WeatherForecast` クラスと派生クラス `WeatherForecastWithWind`があるとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="8c508-274">また、コンパイル時に `Serialize` メソッドの型引数が `WeatherForecast`であるとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="8c508-275">このシナリオでは、`weatherForecast` オブジェクトが実際には `WeatherForecastWithWind` オブジェクトであっても、`WindSpeed` プロパティはシリアル化されません。</span><span class="sxs-lookup"><span data-stu-id="8c508-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="8c508-276">基本クラスのプロパティのみがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="8c508-277">この動作は、派生したランタイムによって作成された型でデータが誤って公開されるのを防ぐためのものです。</span><span class="sxs-lookup"><span data-stu-id="8c508-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="8c508-278">派生型のプロパティをシリアル化するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="8c508-279">実行時に型を指定できるようにする <xref:System.Text.Json.JsonSerializer.Serialize%2A> のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="8c508-280">`object`としてシリアル化するオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8c508-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="8c508-281">前の例のシナリオでは、どちらの方法でも、`WindSpeed` プロパティが JSON 出力に含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="8c508-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="8c508-282">ポリモーフィックな逆シリアル化については、「[ポリモーフィックな逆シリアル化のサポート](system-text-json-converters-how-to.md#support-polymorphic-deserialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="8c508-283">コメントと末尾のコンマを許可する</span><span class="sxs-lookup"><span data-stu-id="8c508-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="8c508-284">JSON では、コメントと末尾のコンマは既定で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="8c508-285">JSON でコメントを許可するには、<xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> プロパティを `JsonCommentHandling.Skip`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="8c508-286">また、末尾のコンマを許可するには、<xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="8c508-287">次の例では、両方を許可する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="8c508-288">次に、コメントと末尾のコンマを含む JSON の例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="8c508-289">大文字と小文字を区別しないプロパティ照合</span><span class="sxs-lookup"><span data-stu-id="8c508-289">Case-insensitive property matching</span></span>

<span data-ttu-id="8c508-290">既定では、逆シリアル化では、JSON とターゲットオブジェクトのプロパティの間で大文字と小文字が区別されるプロパティ名の一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="8c508-291">この動作を変更するには、<xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="8c508-292">Camel 形式のプロパティ名を持つ JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="8c508-293">Pascal 形式のプロパティ名を持つ次の型に逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="8c508-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="handle-overflow-json"></a><span data-ttu-id="8c508-294">Overflow JSON の処理</span><span class="sxs-lookup"><span data-stu-id="8c508-294">Handle overflow JSON</span></span>

<span data-ttu-id="8c508-295">逆シリアル化中に、対象の型のプロパティで表されないデータを JSON で受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="8c508-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8c508-296">たとえば、対象の型が次のようになっているとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="8c508-297">逆シリアル化される JSON は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c508-297">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="8c508-298">示されている型に表示されている JSON を逆シリアル化すると、`DatesAvailable` と `SummaryWords` のプロパティがなくなり、失われます。</span><span class="sxs-lookup"><span data-stu-id="8c508-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8c508-299">これらのプロパティなどの追加データをキャプチャするには、 [Jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)属性を `Dictionary<string,object>` 型または `Dictionary<string,JsonElement>`型のプロパティに適用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="8c508-300">前に示した JSON をこのサンプル型に逆シリアル化すると、余分なデータが `ExtensionData` プロパティのキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="8c508-301">property</span><span class="sxs-lookup"><span data-stu-id="8c508-301">Property</span></span> |<span data-ttu-id="8c508-302">[値]</span><span class="sxs-lookup"><span data-stu-id="8c508-302">Value</span></span>  |<span data-ttu-id="8c508-303">ノート</span><span class="sxs-lookup"><span data-stu-id="8c508-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="8c508-304">日付</span><span class="sxs-lookup"><span data-stu-id="8c508-304">Date</span></span>    | <span data-ttu-id="8c508-305">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8c508-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="8c508-306">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="8c508-306">TemperatureC</span></span>| <span data-ttu-id="8c508-307">0</span><span class="sxs-lookup"><span data-stu-id="8c508-307">0</span></span> | <span data-ttu-id="8c508-308">大文字と小文字が区別されない (JSON で`temperatureC`) ため、プロパティが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="8c508-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="8c508-309">まとめ</span><span class="sxs-lookup"><span data-stu-id="8c508-309">Summary</span></span> | <span data-ttu-id="8c508-310">熱い</span><span class="sxs-lookup"><span data-stu-id="8c508-310">Hot</span></span> ||
| <span data-ttu-id="8c508-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8c508-311">ExtensionData</span></span> | <span data-ttu-id="8c508-312">temperatureC:25</span><span class="sxs-lookup"><span data-stu-id="8c508-312">temperatureC: 25</span></span> |<span data-ttu-id="8c508-313">大文字と小文字が一致しなかったため、この JSON プロパティは余分で、ディクショナリ内のキーと値のペアになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="8c508-314">使用可能な日:</span><span class="sxs-lookup"><span data-stu-id="8c508-314">DatesAvailable:</span></span><br>  <span data-ttu-id="8c508-315">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8c508-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="8c508-316">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8c508-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="8c508-317">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="8c508-318">概要語:</span><span class="sxs-lookup"><span data-stu-id="8c508-318">SummaryWords:</span></span><br><span data-ttu-id="8c508-319">Cool</span><span class="sxs-lookup"><span data-stu-id="8c508-319">Cool</span></span><br><span data-ttu-id="8c508-320">強風</span><span class="sxs-lookup"><span data-stu-id="8c508-320">Windy</span></span><br><span data-ttu-id="8c508-321">Humid</span><span class="sxs-lookup"><span data-stu-id="8c508-321">Humid</span></span> |<span data-ttu-id="8c508-322">JSON からの追加のプロパティはキーと値のペアになり、値オブジェクトとして配列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="8c508-323">ターゲットオブジェクトがシリアル化されると、拡張データのキーと値のペアは、受信 JSON の場合と同様に JSON プロパティになります。</span><span class="sxs-lookup"><span data-stu-id="8c508-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="8c508-324">JSON には `ExtensionData` プロパティ名が表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8c508-325">この動作により、JSON は、逆シリアル化されない余分なデータを失うことなく、ラウンドトリップを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8c508-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="8c508-326">逆シリアル化時に null を無視する</span><span class="sxs-lookup"><span data-stu-id="8c508-326">Ignore null when deserializing</span></span>

<span data-ttu-id="8c508-327">既定では、JSON のプロパティが null の場合、対象オブジェクト内の対応するプロパティは null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="8c508-328">場合によっては、ターゲットプロパティに既定値が設定されていて、null 値を使用して既定値をオーバーライドしないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8c508-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="8c508-329">たとえば、次のコードがターゲットオブジェクトを表しているとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="8c508-330">次の JSON が逆シリアル化されたとします。</span><span class="sxs-lookup"><span data-stu-id="8c508-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="8c508-331">逆シリアル化後、`WeatherForecastWithDefault` オブジェクトの `Summary` プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="8c508-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="8c508-332">この動作を変更するには、次の例に示すように、<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="8c508-333">このオプションを使用すると、逆シリアル化後に、`WeatherForecastWithDefault` オブジェクトの `Summary` プロパティが既定値の "No summary" になります。</span><span class="sxs-lookup"><span data-stu-id="8c508-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="8c508-334">JSON 内の Null 値は、有効な場合にのみ無視されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="8c508-335">Null 非許容値型に対して Null 値を指定すると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="8c508-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="8c508-336">詳細については、GitHub の dotnet/corefx リポジトリにある[null 非許容の値型に関する問題](https://github.com/dotnet/corefx/issues/40922)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c508-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="8c508-337">Utf8JsonReader、Utf8JsonWriter、JsonDocument</span><span class="sxs-lookup"><span data-stu-id="8c508-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="8c508-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> は、UTF-8 でエンコードされた JSON テキスト用の高パフォーマンス、低割り当て、転送のみのリーダーです。`ReadOnlySpan<byte>` から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="8c508-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="8c508-339">`Utf8JsonReader` は、カスタムパーサーとデシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="8c508-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="8c508-340"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> メソッドは、内部で `Utf8JsonReader` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="8c508-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> は、`String`、`Int32`、`DateTime`などの一般的な .NET 型から、UTF-8 でエンコードされた JSON テキストを書き込むための高パフォーマンスの方法です。</span><span class="sxs-lookup"><span data-stu-id="8c508-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="8c508-342">ライターは、カスタムシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="8c508-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="8c508-343"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> メソッドは、内部で `Utf8JsonWriter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c508-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="8c508-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> は、`Utf8JsonReader`を使用して、読み取り専用ドキュメントオブジェクトモデル (DOM) を構築する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8c508-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="8c508-345">DOM は、JSON ペイロード内のデータへのランダムアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c508-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="8c508-346">ペイロードを構成する JSON 要素には、<xref:System.Text.Json.JsonElement> の種類を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8c508-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="8c508-347">`JsonElement` には、JSON テキストを共通の .NET 型に変換するための Api と共に配列とオブジェクトの列挙子が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8c508-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="8c508-348">`JsonDocument` は <xref:System.Text.Json.JsonDocument.RootElement> プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="8c508-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="8c508-349">以下のセクションでは、これらのツールを使用して JSON の読み取りと書き込みを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c508-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="8c508-350">データへのアクセスに JsonDocument を使用する</span><span class="sxs-lookup"><span data-stu-id="8c508-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="8c508-351">次の例は、<xref:System.Text.Json.JsonDocument> クラスを使用して、データへのランダムアクセスを行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c508-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="8c508-352">上記のコードでは次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="8c508-352">The preceding code:</span></span>

* <span data-ttu-id="8c508-353">は、分析する JSON が `jsonString`という名前の文字列に含まれていると想定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="8c508-354">`Grade` プロパティを持つ `Students` 配列内のオブジェクトの平均グレードを計算します。</span><span class="sxs-lookup"><span data-stu-id="8c508-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="8c508-355">学年のない学生に対して既定のグレード70を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8c508-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="8c508-356">各イテレーションで `count` 変数をインクリメントして生徒をカウントします。</span><span class="sxs-lookup"><span data-stu-id="8c508-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="8c508-357">別の方法として、<xref:System.Text.Json.JsonElement.GetArrayLength%2A>を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8c508-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="8c508-358">このコードで処理される JSON の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="8c508-359">JsonDocument を使用した JSON の記述</span><span class="sxs-lookup"><span data-stu-id="8c508-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="8c508-360">次の例は、<xref:System.Text.Json.JsonDocument>から JSON を書き込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c508-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="8c508-361">上記のコードでは次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="8c508-361">The preceding code:</span></span>

* <span data-ttu-id="8c508-362">JSON ファイルを読み取り、データを `JsonDocument`に読み込み、書式設定された (非常に印刷された) JSON をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8c508-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="8c508-363"><xref:System.Text.Json.JsonDocumentOptions> を使用して、入力 JSON 内のコメントを許可しますが、無視することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="8c508-364">完了すると、はライターで <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c508-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="8c508-365">別の方法として、破棄されたときにライターを autoflush することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c508-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="8c508-366">コード例によって処理される JSON 入力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="8c508-367">その結果、次のような整形出力の JSON 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8c508-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="8c508-368">Utf8JsonWriter を使用する</span><span class="sxs-lookup"><span data-stu-id="8c508-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="8c508-369">次の例は、<xref:System.Text.Json.Utf8JsonWriter> クラスの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c508-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

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

## <a name="use-utf8jsonreader"></a><span data-ttu-id="8c508-370">Utf8JsonReader を使用する</span><span class="sxs-lookup"><span data-stu-id="8c508-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="8c508-371">次の例は、<xref:System.Text.Json.Utf8JsonReader> クラスの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c508-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

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

<span data-ttu-id="8c508-372">上記のコードでは、`jsonUtf8` 変数が、UTF-8 としてエンコードされた有効な JSON を含むバイト配列であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8c508-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="8c508-373">Utf8JsonReader を使用してデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="8c508-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="8c508-374">次の例は、ファイルを同期的に読み取り、値を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c508-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="8c508-375">上記のコードでは次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="8c508-375">The preceding code:</span></span>

* <span data-ttu-id="8c508-376">は、ファイルが UTF-16 としてエンコードされているものと想定し、UTF-8 にトランスコードします。</span><span class="sxs-lookup"><span data-stu-id="8c508-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="8c508-377">UTF-8 としてエンコードされたファイルは、次のコードを使用して、`ReadOnlySpan<byte>`に直接読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8c508-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="8c508-378">JSON にオブジェクトの配列が含まれており、各オブジェクトに文字列型の "name" プロパティが含まれていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="8c508-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="8c508-379">オブジェクトをカウントし、"大学" で終わるプロパティ値を `name` します。</span><span class="sxs-lookup"><span data-stu-id="8c508-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="8c508-380">上記のコードが読み取ることができる JSON のサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c508-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="8c508-381">結果として生成される概要メッセージは、"2 ~ 4 個の名前が ' 大学 ' で終わっています" です。</span><span class="sxs-lookup"><span data-stu-id="8c508-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="8c508-382">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8c508-382">Additional resources</span></span>

* [<span data-ttu-id="8c508-383">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="8c508-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8c508-384">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="8c508-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="8c508-385">System.string のカスタムコンバーターを作成する</span><span class="sxs-lookup"><span data-stu-id="8c508-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8c508-386">System.string での DateTime と DateTimeOffset のサポート</span><span class="sxs-lookup"><span data-stu-id="8c508-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
