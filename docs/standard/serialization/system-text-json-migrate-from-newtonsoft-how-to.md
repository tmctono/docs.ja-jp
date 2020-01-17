---
title: Newtonsoft. Json から .NET への移行
author: tdykstra
ms.author: tdykstra
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 01f94bcfce97da8c71b1b709baa34c2b7509a5e5
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116688"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="5a25b-102">Newtonsoft. Json から system.string に移行する方法</span><span class="sxs-lookup"><span data-stu-id="5a25b-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="5a25b-103">この記事では、 [Newtonsoft. Json](https://www.newtonsoft.com/json)から <xref:System.Text.Json>に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

 <span data-ttu-id="5a25b-104">`System.Text.Json` は、主にパフォーマンス、セキュリティ、および標準への準拠に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-104">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="5a25b-105">既定の動作にはいくつかの重要な違いがあり、`Newtonsoft.Json`との機能の同等性はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-105">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="5a25b-106">一部のシナリオでは、`System.Text.Json` に組み込まれている機能はありませんが、推奨される回避策があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-106">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="5a25b-107">他のシナリオでは、回避策は現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-107">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="5a25b-108">アプリケーションが不足している機能に依存している場合は、[問題](https://github.com/dotnet/runtime/issues/new)を報告して、シナリオのサポートが追加されるかどうかを確認することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-108">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="5a25b-109">この記事では、<xref:System.Text.Json.JsonSerializer> API の使用方法について説明しますが、<xref:System.Text.Json.JsonDocument> (ドキュメントオブジェクトモデルまたは DOM を表す)、<xref:System.Text.Json.Utf8JsonReader>、<xref:System.Text.Json.Utf8JsonWriter> の型の使用方法に関するガイダンスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-109">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span> <span data-ttu-id="5a25b-110">記事は、次の順序でセクションにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-110">The article is organized into sections in the following order:</span></span>

* [<span data-ttu-id="5a25b-111">**既定**の jsonserializer の動作が Newtonsoft. Json と比較した場合の相違点</span><span class="sxs-lookup"><span data-stu-id="5a25b-111">Differences in **default** JsonSerializer behavior compared to Newtonsoft.Json</span></span>](#differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson)
* [<span data-ttu-id="5a25b-112">回避策を必要とする JsonSerializer の使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="5a25b-112">Scenarios using JsonSerializer that require workarounds</span></span>](#scenarios-using-jsonserializer-that-require-workarounds)
* [<span data-ttu-id="5a25b-113">現在 JsonSerializer がサポートしていないシナリオ</span><span class="sxs-lookup"><span data-stu-id="5a25b-113">Scenarios that JsonSerializer currently doesn't support</span></span>](#scenarios-that-jsonserializer-currently-doesnt-support)
* [<span data-ttu-id="5a25b-114">JsonDocument および Jsondocument と JToken (Jtoken、Jtoken など) の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-114">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>](#jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray)
* [<span data-ttu-id="5a25b-115">Utf8JsonReader と JsonTextReader の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-115">Utf8JsonReader compared to JsonTextReader</span></span>](#utf8jsonreader-compared-to-jsontextreader)
* [<span data-ttu-id="5a25b-116">Utf8JsonWriter と JsonTextWriter の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-116">Utf8JsonWriter compared to JsonTextWriter</span></span>](#utf8jsonwriter-compared-to-jsontextwriter)

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="5a25b-117">既定の JsonSerializer の動作が Newtonsoft. Json と比較した場合の相違点</span><span class="sxs-lookup"><span data-stu-id="5a25b-117">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="5a25b-118"><xref:System.Text.Json> は既定で厳密であり、決定的な動作を重視して、呼び出し元の代わりに推測や解釈を回避します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-118"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="5a25b-119">ライブラリは、このようにして、パフォーマンスとセキュリティのために意図的に設計されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-119">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="5a25b-120">既定では、`Newtonsoft.Json` は柔軟です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-120">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="5a25b-121">設計におけるこの基本的な違いは、既定の動作の次のような具体的な違いの多くによるものです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-121">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="5a25b-122">大文字と小文字を区別しない逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="5a25b-122">Case-insensitive deserialization</span></span> 

<span data-ttu-id="5a25b-123">逆シリアル化中に、`Newtonsoft.Json` は、既定では大文字と小文字を区別せずにプロパティ名が一致します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-123">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="5a25b-124"><xref:System.Text.Json> の既定値では大文字と小文字が区別され、完全に一致するため、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-124">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="5a25b-125">大文字と小文字を区別しない照合を実行する方法については、「[大文字と小文字](system-text-json-how-to.md#case-insensitive-property-matching)を区別しないプロパティの一致</span><span class="sxs-lookup"><span data-stu-id="5a25b-125">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="5a25b-126">ASP.NET Core を使用して `System.Text.Json` 間接的に使用している場合は、`Newtonsoft.Json`のような動作を取得するために何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-126">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="5a25b-127">ASP.NET Core は、`System.Text.Json`を使用するときに、camel 形式の[プロパティ名](system-text-json-how-to.md#use-camel-case-for-all-json-property-names)と大文字と小文字を区別しない一致の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-127">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="comments"></a><span data-ttu-id="5a25b-128">コメント</span><span class="sxs-lookup"><span data-stu-id="5a25b-128">Comments</span></span>

<span data-ttu-id="5a25b-129">逆シリアル化中、`Newtonsoft.Json` は JSON 内のコメントを既定で無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-129">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="5a25b-130">既定 <xref:System.Text.Json> は、 [RFC 8259](https://tools.ietf.org/html/rfc8259)仕様に含まれていないため、コメントの例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-130">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="5a25b-131">コメントを許可する方法の詳細については、「[コメントと末尾のコンマを許可](system-text-json-how-to.md#allow-comments-and-trailing-commas)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-131">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="5a25b-132">末尾のコンマ</span><span class="sxs-lookup"><span data-stu-id="5a25b-132">Trailing commas</span></span>

<span data-ttu-id="5a25b-133">逆シリアル化中に、`Newtonsoft.Json` は既定で末尾のコンマを無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-133">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="5a25b-134">また、複数の末尾のコンマ (`[{"Color":"Red"},{"Color":"Green"},,]`など) も無視されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-134">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="5a25b-135"><xref:System.Text.Json> 既定では、 [RFC 8259](https://tools.ietf.org/html/rfc8259)仕様では許可されていないため、末尾のコンマの例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-135">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="5a25b-136">`System.Text.Json` 使用する方法の詳細については、「[コメントと末尾のコンマを許可](system-text-json-how-to.md#allow-comments-and-trailing-commas)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-136">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="5a25b-137">複数の末尾にコンマを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-137">There's no way to allow multiple trailing commas.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="5a25b-138">JSON 文字列 (プロパティ名と文字列値)</span><span class="sxs-lookup"><span data-stu-id="5a25b-138">JSON strings (property names and string values)</span></span>

<span data-ttu-id="5a25b-139">逆シリアル化中に、`Newtonsoft.Json` は、二重引用符、単一引用符、引用符なしで囲まれたプロパティ名を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-139">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="5a25b-140">二重引用符または単一引用符で囲まれた文字列値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-140">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="5a25b-141">たとえば、`Newtonsoft.Json` は次の JSON を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-141">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="5a25b-142">`System.Text.Json` は、プロパティ名と文字列値を二重引用符でのみ受け入れます。これは、 [RFC 8259](https://tools.ietf.org/html/rfc8259)仕様ではその形式が必要であり、有効な JSON と見なされる唯一の形式であるためです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-142">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="5a25b-143">単一引用符で囲まれた値は、次のメッセージと共に[Jsonexception](xref:System.Text.Json.JsonException)になります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-143">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="5a25b-144">文字列プロパティの文字列以外の値</span><span class="sxs-lookup"><span data-stu-id="5a25b-144">Non-string values for string properties</span></span>

<span data-ttu-id="5a25b-145">`Newtonsoft.Json` は、文字列型のプロパティへの逆シリアル化のために、数値やリテラル `true` や `false`などの文字列以外の値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-145">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="5a25b-146">次の例では、`Newtonsoft.Json`、次のクラスへの逆シリアル化が正常に行われています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-146">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

<span data-ttu-id="5a25b-147">`System.Text.Json` は、文字列以外の値を文字列プロパティに逆シリアル化しません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-147">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="5a25b-148">文字列フィールドに対して受け取った文字列以外の値を指定すると、 [Jsonexception](xref:System.Text.Json.JsonException)が次のメッセージと共に返されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-148">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

### <a name="converter-registration-precedence"></a><span data-ttu-id="5a25b-149">コンバーターの登録の優先順位</span><span class="sxs-lookup"><span data-stu-id="5a25b-149">Converter registration precedence</span></span>

<span data-ttu-id="5a25b-150">カスタムコンバーターの `Newtonsoft.Json` 登録の優先順位は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-150">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="5a25b-151">プロパティの属性</span><span class="sxs-lookup"><span data-stu-id="5a25b-151">Attribute on property</span></span>
* <span data-ttu-id="5a25b-152">型の属性</span><span class="sxs-lookup"><span data-stu-id="5a25b-152">Attribute on type</span></span>
* <span data-ttu-id="5a25b-153">[コンバーター](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)コレクション</span><span class="sxs-lookup"><span data-stu-id="5a25b-153">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="5a25b-154">この順序は、`Converters` コレクション内のカスタムコンバーターが、型レベルで属性を適用することによって登録されるコンバーターによってオーバーライドされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-154">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="5a25b-155">これらの登録はどちらも、プロパティレベルで属性によってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-155">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="5a25b-156">カスタムコンバーターの <xref:System.Text.Json> 登録の優先順位は次のとおり異なります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-156">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="5a25b-157">プロパティの属性</span><span class="sxs-lookup"><span data-stu-id="5a25b-157">Attribute on property</span></span>
* <span data-ttu-id="5a25b-158"><xref:System.Text.Json.JsonSerializerOptions.Converters> コレクション</span><span class="sxs-lookup"><span data-stu-id="5a25b-158"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="5a25b-159">型の属性</span><span class="sxs-lookup"><span data-stu-id="5a25b-159">Attribute on type</span></span>

<span data-ttu-id="5a25b-160">ここでの違いは、`Converters` コレクションのカスタムコンバーターが型レベルの属性をオーバーライドすることです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-160">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="5a25b-161">この優先順位の背後にある意図は、実行時の変更によってデザイン時の選択肢がオーバーライドされることです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-161">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="5a25b-162">優先順位を変更する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-162">There's no way to change the precedence.</span></span>

<span data-ttu-id="5a25b-163">カスタムコンバーターの登録の詳細については、「[カスタムコンバーターの登録](system-text-json-converters-how-to.md#register-a-custom-converter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-163">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="character-escaping"></a><span data-ttu-id="5a25b-164">文字のエスケープ</span><span class="sxs-lookup"><span data-stu-id="5a25b-164">Character escaping</span></span>

<span data-ttu-id="5a25b-165">シリアル化時には、文字をエスケープせずに文字を使用することを、`Newtonsoft.Json` が比較的制限されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-165">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="5a25b-166">つまり、`xxxx` が文字のコードポイントである `\uxxxx` には置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-166">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="5a25b-167">エスケープされた場所では、文字の前に `\` を出力します (たとえば、`"` が `\"`になります)。</span><span class="sxs-lookup"><span data-stu-id="5a25b-167">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="5a25b-168"><xref:System.Text.Json> は、クロスサイトスクリプティング (XSS) 攻撃または情報漏えい攻撃に対する多層防御を提供するために、既定でより多くの文字をエスケープし、6文字のシーケンスを使用してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="5a25b-168"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="5a25b-169">`System.Text.Json` は、既定では ASCII 以外の文字をすべてエスケープするため、`Newtonsoft.Json`で `StringEscapeHandling.EscapeNonAscii` を使用している場合は何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-169">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="5a25b-170">また `System.Text.Json` は、既定で HTML を区別する文字もエスケープします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-170">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="5a25b-171">既定の `System.Text.Json` 動作をオーバーライドする方法については、「[文字エンコードをカスタマイズ](system-text-json-how-to.md#customize-character-encoding)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-171">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="5a25b-172">オブジェクトプロパティの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="5a25b-172">Deserialization of object properties</span></span>

<span data-ttu-id="5a25b-173">POCOs または `Dictionary<string, object>`型のディクショナリで `object` プロパティに逆シリアル化 `Newtonsoft.Json` 場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-173">When `Newtonsoft.Json` deserializes to `object` properties in POCOs or in dictionaries of type `Dictionary<string, object>`, it:</span></span>

* <span data-ttu-id="5a25b-174">JSON ペイロード (`null`以外) のプリミティブ値の型を推測し、格納されている `string`、`long`、`double`、`boolean`、または `DateTime` をボックス化されたオブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-174">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="5a25b-175">*プリミティブ値*は、json 数値、文字列、`true`、`false`、`null`などの1つの json 値です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-175">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="5a25b-176">JSON ペイロード内の複合値の `JObject` または `JArray` を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-176">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="5a25b-177">*複合値*は、中かっこ (`{}`) 内の JSON キーと値のペアのコレクション、または角かっこ (`[]`) 内の値のリストです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-177">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="5a25b-178">中かっこ内または角かっこ内のプロパティと値には、追加のプロパティまたは値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-178">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="5a25b-179">ペイロードに `null` JSON リテラルが含まれている場合は、null 参照を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-179">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="5a25b-180"><xref:System.Text.Json> は、`System.Object` プロパティまたはディクショナリ値内にプリミティブ値と複合値の両方のボックス化された `JsonElement` を格納します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-180"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values within the `System.Object` property or dictionary value.</span></span> <span data-ttu-id="5a25b-181">ただし、`Newtonsoft.Json` と同じ `null` を処理し、ペイロードに `null` JSON リテラルが含まれている場合は null 参照を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-181">However, it treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="5a25b-182">`object` プロパティの型の推定を実装するには、「[カスタムコンバーターの記述方法](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)」の例のようなコンバーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-182">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="5a25b-183">最大の深さ</span><span class="sxs-lookup"><span data-stu-id="5a25b-183">Maximum depth</span></span>

<span data-ttu-id="5a25b-184">`Newtonsoft.Json` には、既定では最大の深さが制限されていません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-184">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="5a25b-185"><xref:System.Text.Json> の既定の制限は64であり、<xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>を設定することによって構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-185">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="omit-null-value-properties"></a><span data-ttu-id="5a25b-186">Null 値のプロパティを省略する</span><span class="sxs-lookup"><span data-stu-id="5a25b-186">Omit null-value properties</span></span>

<span data-ttu-id="5a25b-187">`Newtonsoft.Json` には、null 値プロパティをシリアル化から除外するグローバル設定があります。 [Nullvaluehandling. Ignore](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm).</span><span class="sxs-lookup"><span data-stu-id="5a25b-187">`Newtonsoft.Json` has a global setting that causes null-value properties to be excluded from serialization: [NullValueHandling.Ignore](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm).</span></span> <span data-ttu-id="5a25b-188"><xref:System.Text.Json> の対応するオプションは <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-188">The corresponding option in <xref:System.Text.Json> is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>.</span></span>

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="5a25b-189">回避策を必要とする JsonSerializer の使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="5a25b-189">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="5a25b-190">次のシナリオは、組み込み機能ではサポートされていませんが、回避策用にサンプルコードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-190">The following scenarios aren't supported by built-in functionality, but sample code is provided for workarounds.</span></span> <span data-ttu-id="5a25b-191">ほとんどの回避策では、[カスタムコンバーター](system-text-json-converters-how-to.md)を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-191">Most of the workarounds require that you implement [custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="5a25b-192">日付の形式を指定する</span><span class="sxs-lookup"><span data-stu-id="5a25b-192">Specify date format</span></span>

<span data-ttu-id="5a25b-193">`Newtonsoft.Json` には、`DateTime` と `DateTimeOffset` 型のプロパティをシリアル化および逆シリアル化する方法を制御するためのいくつかの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-193">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="5a25b-194">`DateTimeZoneHandling` 設定は、すべての `DateTime` 値を UTC 日付としてシリアル化するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-194">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="5a25b-195">`DateFormatString` 設定と `DateTime` コンバーターを使用して、日付文字列の形式をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-195">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="5a25b-196"><xref:System.Text.Json>では、サポートが組み込まれている唯一の形式は ISO 8601-1:2019 です。これは広く採用されており、明確で、ラウンドトリップが正確に行われるためです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-196">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="5a25b-197">他の形式を使用するには、カスタムコンバーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-197">To use any other format, create a custom converter.</span></span> <span data-ttu-id="5a25b-198">詳細については、「system.string[での DateTime と DateTimeOffset のサポート](../datetime/system-text-json-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-198">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="5a25b-199">引用符で囲まれた数値</span><span class="sxs-lookup"><span data-stu-id="5a25b-199">Quoted numbers</span></span>

<span data-ttu-id="5a25b-200">`Newtonsoft.Json` は、(引用符で囲まれた) JSON 文字列によって表される数値をシリアル化または逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-200">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="5a25b-201">たとえば、`{"DegreesCelsius":23}`ではなく、`{"DegreesCelsius":"23"}` を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-201">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="5a25b-202"><xref:System.Text.Json>でこの動作を有効にするには、次の例のようなカスタムコンバーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-202">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="5a25b-203">コンバーターは、`long`として定義されたプロパティを処理します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-203">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="5a25b-204">JSON 文字列としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-204">It serializes them as JSON strings.</span></span> 
* <span data-ttu-id="5a25b-205">このメソッドは、逆シリアル化中に、JSON の数値と数値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-205">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

<span data-ttu-id="5a25b-206">個々の `long` プロパティの[属性を使用](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)するか、<xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションに[コンバーターを追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)して、このカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-206">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="5a25b-207">文字列以外のキーを含むディクショナリ</span><span class="sxs-lookup"><span data-stu-id="5a25b-207">Dictionary with non-string key</span></span>

<span data-ttu-id="5a25b-208">`Newtonsoft.Json` は `Dictionary<TKey, TValue>`型のコレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-208">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="5a25b-209"><xref:System.Text.Json> でのディクショナリコレクションの組み込みサポートは、`Dictionary<string, TValue>`に制限されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-209">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="5a25b-210">つまり、キーは文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-210">That is, the key must be a string.</span></span>

<span data-ttu-id="5a25b-211">キーとして整数またはその他の型の辞書をサポートするには、「[カスタムコンバーターの記述方法](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)」の例のようなコンバーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-211">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="5a25b-212">ポリモーフィックシリアル化</span><span class="sxs-lookup"><span data-stu-id="5a25b-212">Polymorphic serialization</span></span>

<span data-ttu-id="5a25b-213">`Newtonsoft.Json` は、自動的にポリモーフィックシリアル化を行います。</span><span class="sxs-lookup"><span data-stu-id="5a25b-213">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="5a25b-214"><xref:System.Text.Json>の制限されたポリモーフィックシリアル化機能については、「[派生クラスのプロパティのシリアル化](system-text-json-how-to.md#serialize-properties-of-derived-classes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-214">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="5a25b-215">ここで説明する回避策は、`object`型として派生クラスを含む可能性のあるプロパティを定義することです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-215">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="5a25b-216">これが不可能な場合は、「[カスタムコンバーターを記述する方法](system-text-json-converters-how-to.md#support-polymorphic-deserialization)」の例のように、継承の種類の階層全体に対して `Write` メソッドを使用してコンバーターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-216">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="5a25b-217">ポリモーフィック逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="5a25b-217">Polymorphic deserialization</span></span>

<span data-ttu-id="5a25b-218">`Newtonsoft.Json` には、シリアル化中に JSON に型名のメタデータを追加する `TypeNameHandling` 設定があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-218">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="5a25b-219">このメタデータは、ポリモーフィックな逆シリアル化を行うために逆シリアル化するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-219">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="5a25b-220"><xref:System.Text.Json> は、ポリモーフィックな逆シリアル化ではなく、限られた範囲の[ポリモーフィックなシリアル化](system-text-json-how-to.md#serialize-properties-of-derived-classes)を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-220"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="5a25b-221">ポリモーフィックな逆シリアル化をサポートするには、「[カスタムコンバーターの記述方法](system-text-json-converters-how-to.md#support-polymorphic-deserialization)」の例のようなコンバーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-221">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="required-properties"></a><span data-ttu-id="5a25b-222">必須のプロパティ</span><span class="sxs-lookup"><span data-stu-id="5a25b-222">Required properties</span></span>

<span data-ttu-id="5a25b-223">逆シリアル化中に、対象の型のいずれかのプロパティの JSON で値が受信されない場合、<xref:System.Text.Json> は例外をスローしません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-223">During deserialization, <xref:System.Text.Json> doesn't throw an exception if no value is received in the JSON for one of the properties of the target type.</span></span> <span data-ttu-id="5a25b-224">たとえば、`WeatherForecast` クラスがある場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-224">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="5a25b-225">次の JSON は、エラーなしで逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-225">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="5a25b-226">JSON に `Date` プロパティがない場合に逆シリアル化が失敗するようにするには、カスタムコンバーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-226">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="5a25b-227">次のサンプルコンバーターコードは、逆シリアル化の完了後に `Date` プロパティが設定されていない場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-227">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="5a25b-228">[POCO クラスの属性を使用](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)するか、<xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションにコンバーターを[追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)して、このカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-228">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="5a25b-229">このパターンに従う場合は、<xref:System.Text.Json.JsonSerializer.Serialize%2A> または <xref:System.Text.Json.JsonSerializer.Deserialize%2A>を再帰的に呼び出すときに options オブジェクトを渡しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-229">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="5a25b-230">Options オブジェクトには、<xref:System.Text.Json.JsonSerializerOptions.Converters%2A> コレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-230">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="5a25b-231">`Serialize` または `Deserialize`に渡すと、カスタムコンバーターはそれ自体を呼び出し、無限ループを行い、stack overflow 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-231">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="5a25b-232">既定のオプションを使用できない場合は、必要な設定を使用してオプションの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-232">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="5a25b-233">新しいインスタンスが個別にキャッシュされるため、この方法は遅くなります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-233">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="5a25b-234">上記のコンバーターコードは、簡略化された例です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-234">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="5a25b-235">属性 ( [[Jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)やカスタムエンコーダーなど) を処理する必要がある場合は、追加のロジックが必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-235">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="5a25b-236">また、この例のコードでは、コンストラクターで既定値が設定されているプロパティを処理しません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-236">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="5a25b-237">このアプローチでは、次のシナリオは区別されません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-237">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="5a25b-238">JSON にプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-238">A property is missing from the JSON.</span></span>
* <span data-ttu-id="5a25b-239">Null 非許容型のプロパティは JSON に存在しますが、値は、`int`の0など、型の既定値です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-239">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="5a25b-240">Null 許容型のプロパティが JSON に存在しますが、値は null です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-240">A property for a nullable type is present in the JSON, but the value is null.</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="5a25b-241">Null 非許容型に null を逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="5a25b-241">Deserialize null to non-nullable type</span></span> 

<span data-ttu-id="5a25b-242">`Newtonsoft.Json` は、次のシナリオでは例外をスローしません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-242">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="5a25b-243">`NullValueHandling` は `Ignore`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-243">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="5a25b-244">逆シリアル化中に、JSON に null 非許容型の null 値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-244">During deserialization, the JSON contains a null value for a non-nullable type.</span></span>

<span data-ttu-id="5a25b-245">同じシナリオでは、<xref:System.Text.Json> によって例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-245">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="5a25b-246">(対応する null 処理設定は <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>です)。</span><span class="sxs-lookup"><span data-stu-id="5a25b-246">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="5a25b-247">対象の型を所有している場合は、問題のプロパティを null 許容にすることをお勧めします (たとえば、`int` を `int?`に変更します)。</span><span class="sxs-lookup"><span data-stu-id="5a25b-247">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="5a25b-248">もう1つの回避策は、型のコンバーターを作成することです。たとえば、次の例では `DateTimeOffset` 型の null 値を処理します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-248">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="5a25b-249">このカスタムコンバーターを登録するには[、プロパティの属性を使用](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)するか、<xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションに[コンバーターを追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-249">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="5a25b-250">**注:** 上記のコンバーターは、既定値を指定する POCOs の `Newtonsoft.Json` とは**異なる方法で null 値を処理**します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-250">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="5a25b-251">たとえば、次のコードがターゲットオブジェクトを表しているとします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-251">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="5a25b-252">また、前のコンバーターを使用して、次の JSON が逆シリアル化されたとします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-252">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="5a25b-253">逆シリアル化の後、`Date` プロパティに 1/1/0001 (`default(DateTimeOffset)`) が設定されます。つまり、コンストラクターで設定された値が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-253">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="5a25b-254">同じ POCO と JSON を指定すると、`Newtonsoft.Json` 逆シリアル化によって `Date` プロパティに1/1/2001 が残されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-254">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="5a25b-255">変更できないクラスと構造体への逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="5a25b-255">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="5a25b-256">`Newtonsoft.Json` は、パラメーターを持つコンストラクターを使用できるため、変更できないクラスおよび構造体に逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-256">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="5a25b-257"><xref:System.Text.Json> では、パラメーターなしのパブリックコンストラクターのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-257"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="5a25b-258">回避策として、カスタムコンバーターでパラメーターを使用してコンストラクターを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-258">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="5a25b-259">次に、複数のコンストラクターパラメーターを持つ変更できない構造体を示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-259">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="5a25b-260">この構造体をシリアル化および逆シリアル化するコンバーターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-260">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="5a25b-261"><xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションにコンバーターを[追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)して、このカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-261">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="5a25b-262">オープンな汎用プロパティを処理する同様のコンバーターの例については、[キーと値のペアの組み込みのコンバーター](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-262">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="5a25b-263">使用するコンストラクターの指定</span><span class="sxs-lookup"><span data-stu-id="5a25b-263">Specify constructor to use</span></span>

<span data-ttu-id="5a25b-264">`Newtonsoft.Json` `[JsonConstructor]` 属性では、POCO に逆シリアル化するときに呼び出すコンストラクターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-264">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="5a25b-265"><xref:System.Text.Json> では、パラメーターなしのコンストラクターのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-265"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="5a25b-266">回避策として、カスタムコンバーターで必要なコンストラクターを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-266">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="5a25b-267">変更できない[クラスと構造体への逆シリアル](#deserialize-to-immutable-classes-and-structs)化の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-267">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="5a25b-268">条件付きでプロパティを無視する</span><span class="sxs-lookup"><span data-stu-id="5a25b-268">Conditionally ignore a property</span></span>

<span data-ttu-id="5a25b-269">`Newtonsoft.Json` には、シリアル化または逆シリアル化のプロパティを条件付きで無視するいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-269">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="5a25b-270">`DefaultContractResolver` を使用すると、任意の条件に基づいて追加または除外するプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-270">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span> 
* <span data-ttu-id="5a25b-271">`JsonSerializerSettings` の `NullValueHandling` と `DefaultValueHandling` の設定を使用すると、すべての null 値または既定値のプロパティを無視するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-271">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="5a25b-272">`[JsonProperty]` 属性の `NullValueHandling` と `DefaultValueHandling` の設定を使用すると、null または既定値に設定されている場合に無視する必要がある個々のプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-272">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="5a25b-273"><xref:System.Text.Json> には、シリアル化中にプロパティを省略する次の方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-273"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="5a25b-274">プロパティの[[Jsonignore]](system-text-json-how-to.md#exclude-individual-properties)属性を指定すると、シリアル化中にプロパティが JSON から除外されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-274">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="5a25b-275">[Ignorenullvalues](system-text-json-how-to.md#exclude-all-null-value-properties)グローバルオプションを使用すると、すべての null 値プロパティを除外できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-275">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="5a25b-276">[Ignorereadonlyproperties](system-text-json-how-to.md#exclude-all-read-only-properties)グローバルオプションを使用すると、すべての読み取り専用プロパティを除外できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-276">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="5a25b-277">これらのオプションでは、次のことはでき**ません**。</span><span class="sxs-lookup"><span data-stu-id="5a25b-277">These options **don't** let you:</span></span>

* <span data-ttu-id="5a25b-278">型の既定値を持つすべてのプロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-278">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="5a25b-279">型の既定値を持つ選択されたプロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-279">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="5a25b-280">選択したプロパティの値が null の場合は無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-280">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="5a25b-281">実行時に評価された任意の条件に基づいて、選択したプロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-281">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span> 

<span data-ttu-id="5a25b-282">この機能については、カスタムコンバーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-282">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="5a25b-283">このアプローチを示すサンプル POCO とカスタムコンバーターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-283">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="5a25b-284">コンバーターは、値が null、空の文字列、または "N/A" の場合、`Summary` プロパティをシリアル化から省略します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-284">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span> 

<span data-ttu-id="5a25b-285">[クラスの属性を使用](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)するか、<xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションにコンバーターを[追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)して、このカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-285">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="5a25b-286">この方法では、次の場合に追加のロジックが必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-286">This approach requires additional logic if:</span></span>

* <span data-ttu-id="5a25b-287">POCO には、複合プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-287">The POCO includes complex properties.</span></span>
* <span data-ttu-id="5a25b-288">`[JsonIgnore]` などの属性や、カスタムエンコーダーなどのオプションを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-288">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="callbacks"></a><span data-ttu-id="5a25b-289">コールバック</span><span class="sxs-lookup"><span data-stu-id="5a25b-289">Callbacks</span></span>

<span data-ttu-id="5a25b-290">`Newtonsoft.Json` では、シリアル化または逆シリアル化プロセスの複数のポイントでカスタムコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-290">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="5a25b-291">OnDeserializing シリアル化 (オブジェクトの逆シリアル化の開始時)</span><span class="sxs-lookup"><span data-stu-id="5a25b-291">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="5a25b-292">OnDeserialized シリアル化 (オブジェクトの逆シリアル化が完了したとき)</span><span class="sxs-lookup"><span data-stu-id="5a25b-292">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="5a25b-293">OnSerializing (オブジェクトのシリアル化の開始時)</span><span class="sxs-lookup"><span data-stu-id="5a25b-293">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="5a25b-294">OnSerialized 化 (オブジェクトのシリアル化が完了したとき)</span><span class="sxs-lookup"><span data-stu-id="5a25b-294">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="5a25b-295"><xref:System.Text.Json>では、カスタムコンバーターを記述してコールバックをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-295">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="5a25b-296">次の例は、POCO のカスタムコンバーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-296">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="5a25b-297">コンバーターには、`Newtonsoft.Json` コールバックに対応する各ポイントにメッセージを表示するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-297">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="5a25b-298">[クラスの属性を使用](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)するか、<xref:System.Text.Json.JsonSerializerOptions.Converters> コレクションにコンバーターを[追加](system-text-json-converters-how-to.md#registration-sample---converters-collection)して、このカスタムコンバーターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-298">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="5a25b-299">前のサンプルに続くカスタムコンバーターを使用する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-299">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="5a25b-300">`OnDeserializing` コードには、新しい POCO インスタンスへのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-300">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="5a25b-301">逆シリアル化の開始時に新しい POCO インスタンスを操作するには、そのコードを POCO コンストラクターに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-301">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="5a25b-302">`Serialize` または `Deserialize`を再帰的に呼び出すときは、options オブジェクトを渡しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-302">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="5a25b-303">Options オブジェクトには、`Converters` コレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-303">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="5a25b-304">`Serialize` または `Deserialize`に渡すと、コンバーターが使用され、無限ループが発生してスタックオーバーフロー例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-304">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="5a25b-305">現在 JsonSerializer がサポートしていないシナリオ</span><span class="sxs-lookup"><span data-stu-id="5a25b-305">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="5a25b-306">次のシナリオでは回避策が考えられますが、その中には実装が比較的困難なものもあります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-306">Workarounds are possible for the following scenarios, but some of them would be relatively difficult to implement.</span></span> <span data-ttu-id="5a25b-307">この記事では、これらのシナリオの回避策を示すコードサンプルは提供しません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-307">This article doesn't provide code samples for workarounds for these scenarios.</span></span>

<span data-ttu-id="5a25b-308">これは、`System.Text.Json`に同等ではない `Newtonsoft.Json` の機能を網羅した一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-308">This is not an exhaustive list of `Newtonsoft.Json` features that have no equivalents in `System.Text.Json`.</span></span> <span data-ttu-id="5a25b-309">この一覧には、 [GitHub の問題](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)または[stackoverflow](https://stackoverflow.com/questions/tagged/system.text.json)の投稿で要求された多くのシナリオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-309">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span>

<span data-ttu-id="5a25b-310">これらのシナリオのいずれかに対応する回避策を実装し、コードを共有できる場合は、ページの下部にある **[このページ]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-310">If you implement a workaround for one of these scenarios and can share the code, select the "**This page**" button at the bottom of the page.</span></span> <span data-ttu-id="5a25b-311">GitHub の問題が作成され、ページの下部に表示されている問題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-311">That creates a GitHub issue and adds it to the issues that are listed at the bottom of the page.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="5a25b-312">組み込みサポートのない型</span><span class="sxs-lookup"><span data-stu-id="5a25b-312">Types without built-in support</span></span>

<span data-ttu-id="5a25b-313"><xref:System.Text.Json> には、次の種類の組み込みサポートが用意されていません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-313"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="5a25b-314"><xref:System.Data.DataTable> と関連する型</span><span class="sxs-lookup"><span data-stu-id="5a25b-314"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="5a25b-315">F#[判別共用体](../../fsharp/language-reference/discriminated-unions.md)、[レコードの種類](../../fsharp/language-reference/records.md)、[匿名レコードの種類](../../fsharp/language-reference/anonymous-records.md)などの型。</span><span class="sxs-lookup"><span data-stu-id="5a25b-315">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <span data-ttu-id="5a25b-316"><xref:System.Collections.Specialized> 名前空間のコレクション型</span><span class="sxs-lookup"><span data-stu-id="5a25b-316">Collection types in the <xref:System.Collections.Specialized> namespace</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="5a25b-317"><xref:System.ValueTuple> とそれに関連付けられているジェネリック型</span><span class="sxs-lookup"><span data-stu-id="5a25b-317"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="5a25b-318">組み込みのサポートがない型に対しては、カスタムコンバーターを実装できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-318">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="5a25b-319">パブリックフィールドと非パブリックフィールド</span><span class="sxs-lookup"><span data-stu-id="5a25b-319">Public and non-public fields</span></span>

<span data-ttu-id="5a25b-320">`Newtonsoft.Json` は、フィールドおよびプロパティをシリアル化および逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-320">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="5a25b-321"><xref:System.Text.Json> は、パブリックプロパティに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-321"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="5a25b-322">カスタムコンバーターは、この機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-322">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="5a25b-323">内部およびプライベートのプロパティ setter と getter</span><span class="sxs-lookup"><span data-stu-id="5a25b-323">Internal and private property setters and getters</span></span>

<span data-ttu-id="5a25b-324">`Newtonsoft.Json` は、`JsonProperty` 属性を使用して、プライベートと内部のプロパティセッターおよび getter を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-324">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="5a25b-325"><xref:System.Text.Json> では、パブリック setter のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-325"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="5a25b-326">カスタムコンバーターは、この機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-326">Custom converters can provide this functionality.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="5a25b-327">オブジェクト参照の保持とループの処理</span><span class="sxs-lookup"><span data-stu-id="5a25b-327">Preserve object references and handle loops</span></span>

<span data-ttu-id="5a25b-328">既定では、`Newtonsoft.Json` は値によってシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-328">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="5a25b-329">たとえば、オブジェクトに同じ `Person` オブジェクトへの参照を含む2つのプロパティが含まれている場合、その `Person` オブジェクトのプロパティの値は JSON で重複します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-329">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="5a25b-330">`Newtonsoft.Json` には、参照によってシリアル化できる `JsonSerializerSettings` に `PreserveReferencesHandling` の設定があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-330">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="5a25b-331">識別子メタデータは、最初の `Person` オブジェクト用に作成された JSON に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-331">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="5a25b-332">2番目の `Person` オブジェクト用に作成された JSON には、プロパティ値ではなく、その識別子への参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-332">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="5a25b-333">`Newtonsoft.Json` には、例外をスローするのではなく、循環参照を無視できるようにする `ReferenceLoopHandling` 設定もあります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-333">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="5a25b-334"><xref:System.Text.Json> は、値によるシリアル化のみをサポートし、循環参照の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-334"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="5a25b-335">System.object のシリアル化属性</span><span class="sxs-lookup"><span data-stu-id="5a25b-335">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="5a25b-336"><xref:System.Text.Json> は、`DataMemberAttribute` や `IgnoreDataMemberAttribute`など、`System.Runtime.Serialization` 名前空間の属性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-336"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="5a25b-337">8進数の数値</span><span class="sxs-lookup"><span data-stu-id="5a25b-337">Octal numbers</span></span>

<span data-ttu-id="5a25b-338">`Newtonsoft.Json` は、先頭に0を持つ数値を8進数として扱います。</span><span class="sxs-lookup"><span data-stu-id="5a25b-338">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="5a25b-339">[RFC 8259](https://tools.ietf.org/html/rfc8259)仕様では許可されていないため、<xref:System.Text.Json> で先頭に0を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-339"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="5a25b-340">既存のオブジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="5a25b-340">Populate existing objects</span></span>

<span data-ttu-id="5a25b-341">`Newtonsoft.Json` の `JsonConvert.PopulateObject` メソッドは、新しいインスタンスを作成するのではなく、クラスの既存のインスタンスに JSON ドキュメントを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-341">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="5a25b-342"><xref:System.Text.Json> は常に、既定のパブリックパラメーターなしのコンストラクターを使用して、ターゲット型の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-342"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="5a25b-343">カスタムコンバーターは、既存のインスタンスに逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-343">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="5a25b-344">プロパティの置換ではなく再利用</span><span class="sxs-lookup"><span data-stu-id="5a25b-344">Reuse rather than replace properties</span></span>

<span data-ttu-id="5a25b-345">`Newtonsoft.Json` `ObjectCreationHandling` 設定を使用すると、逆シリアル化中に、プロパティ内のオブジェクトを置き換えるのではなく再利用するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-345">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="5a25b-346"><xref:System.Text.Json> は常にプロパティ内のオブジェクトを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-346"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="5a25b-347">カスタムコンバーターは、この機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-347">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="5a25b-348">Setter を使用せずにコレクションに追加する</span><span class="sxs-lookup"><span data-stu-id="5a25b-348">Add to collections without setters</span></span>

<span data-ttu-id="5a25b-349">逆シリアル化時には、プロパティに setter がない場合でも、`Newtonsoft.Json` によってオブジェクトがコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-349">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="5a25b-350"><xref:System.Text.Json> は、setter を持たないプロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-350"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="5a25b-351">カスタムコンバーターは、この機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-351">Custom converters can provide this functionality.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="5a25b-352">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="5a25b-352">MissingMemberHandling</span></span>

<span data-ttu-id="5a25b-353">JSON に対象の型に存在しないプロパティが含まれている場合は、逆シリアル化中に例外をスローするように `Newtonsoft.Json` を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-353">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="5a25b-354"><xref:System.Text.Json> では、 [[Jsonextensiondata] 属性](system-text-json-how-to.md#handle-overflow-json)を使用する場合を除き、JSON の追加のプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-354"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="5a25b-355">見つからないメンバー機能に対する回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-355">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="5a25b-356">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="5a25b-356">TraceWriter</span></span>

<span data-ttu-id="5a25b-357">`Newtonsoft.Json` を使用すると、シリアル化または逆シリアル化によって生成されるログを表示するために `TraceWriter` を使用してデバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-357">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="5a25b-358"><xref:System.Text.Json> はログ記録を行いません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-358"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="5a25b-359">JsonDocument および Jsondocument と JToken (Jtoken、Jtoken など) の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-359">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="5a25b-360"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> は、既存の JSON ペイロードから**読み取り**専用のドキュメントオブジェクトモデル (DOM) を解析し、構築する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-360"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="5a25b-361">DOM は、JSON ペイロード内のデータへのランダムアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-361">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="5a25b-362">ペイロードを構成する JSON 要素には、<xref:System.Text.Json.JsonElement> の種類を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-362">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="5a25b-363">`JsonElement` 型は、JSON テキストを共通の .NET 型に変換するための Api を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-363">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="5a25b-364">`JsonDocument` は <xref:System.Text.Json.JsonDocument.RootElement> プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-364">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="5a25b-365">JsonDocument が IDisposable です</span><span class="sxs-lookup"><span data-stu-id="5a25b-365">JsonDocument is IDisposable</span></span>

<span data-ttu-id="5a25b-366">`JsonDocument` は、プールされたバッファーにデータのインメモリビューを構築します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-366">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="5a25b-367">したがって、`JObject` または `Newtonsoft.Json`からの `JArray` とは異なり、`JsonDocument` 型は `IDisposable` を実装し、using ブロック内で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-367">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span> 

<span data-ttu-id="5a25b-368">有効期間の所有権を転送し、責任を呼び出し元に破棄する場合にのみ、API から `JsonDocument` を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-368">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="5a25b-369">ほとんどのシナリオでは、これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-369">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="5a25b-370">呼び出し元が JSON ドキュメント全体を処理する必要がある場合は、<xref:System.Text.Json.JsonDocument.RootElement%2A>の <xref:System.Text.Json.JsonElement.Clone%2A> を返します。これは <xref:System.Text.Json.JsonElement>です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-370">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="5a25b-371">呼び出し元が JSON ドキュメント内の特定の要素を操作する必要がある場合は、その <xref:System.Text.Json.JsonElement>の <xref:System.Text.Json.JsonElement.Clone%2A> を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-371">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="5a25b-372">`Clone`を作成せずに `RootElement` またはサブ要素を直接返した場合、呼び出し元は、それを所有する `JsonDocument` が破棄された後に、返された `JsonElement` にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-372">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="5a25b-373">次に、`Clone`の作成を要求する例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-373">Here's an example that requires you to make a `Clone`:</span></span>

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());
   
    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

<span data-ttu-id="5a25b-374">前のコードでは、`fileName` プロパティを含む `JsonElement` が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-374">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="5a25b-375">JSON ファイルが開き、`JsonDocument`が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-375">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="5a25b-376">メソッドは、呼び出し元がドキュメント全体を処理することを前提としているため、`RootElement`の `Clone` が返されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-376">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span> 

<span data-ttu-id="5a25b-377">`JsonElement` を受け取り、サブ要素を返す場合は、サブ要素の `Clone` を返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-377">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="5a25b-378">呼び出し元は、渡された `JsonElement` が属している `JsonDocument` を維持する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="5a25b-378">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="5a25b-379">例:</span><span class="sxs-lookup"><span data-stu-id="5a25b-379">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="5a25b-380">JsonDocument は読み取り専用です</span><span class="sxs-lookup"><span data-stu-id="5a25b-380">JsonDocument is read-only</span></span>

<span data-ttu-id="5a25b-381"><xref:System.Text.Json> DOM は、JSON 要素の追加、削除、または変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-381">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="5a25b-382">このようにパフォーマンスを向上させ、共通の JSON ペイロードサイズ (つまり < 1 MB) を解析するための割り当てを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-382">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="5a25b-383">現在のシナリオで変更可能な DOM を使用している場合は、次のいずれかの回避策を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-383">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="5a25b-384">`JsonDocument` を最初から作成する (つまり、既存の JSON ペイロードを `Parse` メソッドに渡すことなく) には、`Utf8JsonWriter` を使用して JSON テキストを書き込み、それからの出力を解析して新しい `JsonDocument`を作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-384">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="5a25b-385">既存の `JsonDocument`を変更するには、JSON テキストの書き込み、書き込み中の変更、および新しい `JsonDocument`を作成するための出力の解析に使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-385">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="5a25b-386">`JObject.Merge` または `JContainer.Merge` Api と同等の既存の JSON ドキュメントを `Newtonsoft.Json`からマージする方法については、 [GitHub の問題](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-386">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="5a25b-387">JsonElement は union 構造体です</span><span class="sxs-lookup"><span data-stu-id="5a25b-387">JsonElement is a union struct</span></span>

<span data-ttu-id="5a25b-388">`JsonDocument` は、`RootElement` を <xref:System.Text.Json.JsonElement>型のプロパティとして公開します。これは、任意の JSON 要素を含む共用体の構造体型です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-388">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="5a25b-389">`Newtonsoft.Json` は、`JObject`、`JArray`、`JToken`などの専用の階層型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-389">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="5a25b-390">`JsonElement` は検索と列挙を行うことができ、`JsonElement` を使用して JSON 要素を .NET 型に具体化できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-390">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="5a25b-391">サブ要素の JsonDocument と Jsondocument を検索する方法</span><span class="sxs-lookup"><span data-stu-id="5a25b-391">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="5a25b-392">`JObject` または `Newtonsoft.Json` の `JArray` を使用した JSON トークンの検索は、一部の辞書で参照されているため、比較的高速になる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-392">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="5a25b-393">比較すると、`JsonElement` の検索にはプロパティのシーケンシャル検索が必要になるため、比較的低速になります (たとえば、`TryGetProperty`を使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="5a25b-393">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="5a25b-394"><xref:System.Text.Json> は、検索時間ではなく、初期の解析時間を最小限に抑えるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-394"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="5a25b-395">そのため、`JsonDocument` オブジェクトを検索するときのパフォーマンスを最適化するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-395">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="5a25b-396">独自のインデックス作成やループを実行するのではなく、組み込みの列挙子 (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> と <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-396">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="5a25b-397">`RootElement`を使用して、すべてのプロパティを通して `JsonDocument` 全体で順次検索を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-397">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="5a25b-398">代わりに、JSON データの既知の構造に基づいて入れ子になった JSON オブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-398">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="5a25b-399">たとえば、`Student` オブジェクトで `Grade` のプロパティを探している場合は、`JsonElement` のプロパティを検索するすべての `Grade` オブジェクトを検索するのではなく、`Student` オブジェクトをループし、それぞれの `Grade` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-399">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="5a25b-400">後者を実行すると、同じデータに対して不要なパスが返されます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-400">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="5a25b-401">コード例については、「[データへのアクセスに JsonDocument を使用](system-text-json-how-to.md#use-jsondocument-for-access-to-data)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-401">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="5a25b-402">Utf8JsonReader と JsonTextReader の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-402">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="5a25b-403"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> は、UTF-8 でエンコードされた JSON テキストの高パフォーマンス、低割り当て、前方参照専用のリーダーであり、 [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)または[ReadOnlySequence\<バイト >](xref:System.Buffers.ReadOnlySequence%601)から読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-403"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="5a25b-404">`Utf8JsonReader` は、カスタムパーサーとデシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-404">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="5a25b-405">以下のセクションでは、`Utf8JsonReader`を使用するための推奨されるプログラミングパターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-405">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="5a25b-406">Utf8JsonReader は ref 構造体です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-406">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="5a25b-407">`Utf8JsonReader` 型は*ref 構造体*であるため、いくつかの[制限](../../csharp/language-reference/keywords/ref.md#ref-struct-types)があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-407">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/keywords/ref.md#ref-struct-types).</span></span> <span data-ttu-id="5a25b-408">たとえば、ref 構造体以外のクラスまたは構造体のフィールドとして格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-408">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="5a25b-409">高パフォーマンスを実現するには、この型が `ref struct` である必要があります。これは、それ自体が ref 構造体である入力[ReadOnlySpan\<バイト >](xref:System.ReadOnlySpan%601)をキャッシュする必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-409">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="5a25b-410">また、この型は状態を保持しているため変更可能です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-410">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="5a25b-411">したがって、値ではなく、 **ref で渡す必要**があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-411">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="5a25b-412">値渡しで渡すと、構造体のコピーが生成され、状態の変更が呼び出し元から参照できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-412">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="5a25b-413">これは、`Newtonsoft.Json` `JsonTextReader` がクラスであるため、`Newtonsoft.Json` とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-413">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="5a25b-414">Ref 構造体の使用方法の詳細については、「[安全C#で効率的なコードを記述](../../csharp/write-safe-efficient-code.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-414">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="5a25b-415">UTF-8 テキストの読み取り</span><span class="sxs-lookup"><span data-stu-id="5a25b-415">Read UTF-8 text</span></span>

<span data-ttu-id="5a25b-416">`Utf8JsonReader`の使用中に最大限のパフォーマンスを実現するには、utf-16 文字列としてではなく、既に UTF-8 テキストとしてエンコードされている JSON ペイロードを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-416">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="5a25b-417">コード例については、「 [Utf8JsonReader を使用してデータをフィルター処理](system-text-json-how-to.md#filter-data-using-utf8jsonreader)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-417">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="5a25b-418">ストリームまたは PipeReader で読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-418">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="5a25b-419">`Utf8JsonReader` は、UTF-8 でエンコードされた[ReadOnlySpan\<バイト >](xref:System.ReadOnlySpan%601)または[ReadOnlySequence\<バイト >](xref:System.Buffers.ReadOnlySequence%601) (<xref:System.IO.Pipelines.PipeReader>からの読み取りの結果) からの読み取りをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-419">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="5a25b-420">同期読み取りの場合は、ストリームの末尾がバイト配列になるまで JSON ペイロードを読み取り、それをリーダーに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-420">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="5a25b-421">(UTF-16 としてエンコードされた) 文字列から読み取るには、<xref:System.Text.Encoding.UTF8>を呼び出します。<xref:System.Text.Encoding.GetBytes%2A></span><span class="sxs-lookup"><span data-stu-id="5a25b-421">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="5a25b-422">まず、文字列を UTF-8 でエンコードされたバイト配列にトランスコードします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-422">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="5a25b-423">その後、それを `Utf8JsonReader`に渡します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-423">Then pass that to the `Utf8JsonReader`.</span></span> 

<span data-ttu-id="5a25b-424">`Utf8JsonReader` は入力を JSON テキストと見なしているため、UTF-8 バイトオーダーマーク (BOM) は無効な JSON と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-424">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="5a25b-425">呼び出し元は、データをリーダーに渡す前にフィルター処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-425">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="5a25b-426">コード例については、「 [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-426">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="5a25b-427">マルチセグメント ReadOnlySequence を使用した読み取り</span><span class="sxs-lookup"><span data-stu-id="5a25b-427">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="5a25b-428">JSON 入力が[ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)の場合、読み取りループを進めるときに、リーダーの `ValueSpan` プロパティから各 json 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-428">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="5a25b-429">ただし、入力が[ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601) (<xref:System.IO.Pipelines.PipeReader>からの読み取りの結果) である場合、一部の JSON 要素によって、`ReadOnlySequence<byte>` オブジェクトの複数のセグメントがまたがるされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-429">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="5a25b-430">これらの要素には、連続したメモリブロック内の <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> からアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-430">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="5a25b-431">代わりに、入力として複数セグメントの `ReadOnlySequence<byte>` がある場合は、リーダーの <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> プロパティをポーリングして、現在の JSON 要素にアクセスする方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-431">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="5a25b-432">推奨されるパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-432">Here's a recommended pattern:</span></span>

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="5a25b-433">プロパティ名の参照に ValueTextEquals を使用する</span><span class="sxs-lookup"><span data-stu-id="5a25b-433">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="5a25b-434">プロパティ名の参照に <xref:System.MemoryExtensions.SequenceEqual%2A> を呼び出すことによってバイト単位の比較を実行する場合は、<xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-434">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="5a25b-435">このメソッドは JSON でエスケープされた文字を unescapes するため、代わりに <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-435">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="5a25b-436">"Name" という名前のプロパティを検索する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-436">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="5a25b-437">Null 値が許容される値型に null 値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-437">Read null values into nullable value types</span></span>

<span data-ttu-id="5a25b-438">`Newtonsoft.Json` には、`TokenType` を返すことによって `Null` `bool?`を処理する `ReadAsBoolean`など、<xref:System.Nullable%601>を返す Api が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-438">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="5a25b-439">組み込みの `System.Text.Json` Api は、null 非許容の値型のみを返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-439">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="5a25b-440">たとえば、<xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> は `bool`を返します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-440">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="5a25b-441">JSON で `Null` が見つかった場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-441">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="5a25b-442">次の例では、null を処理する2つの方法を示しています。 null 許容値型を返し、既定値を返すことによって1つです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-442">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a><span data-ttu-id="5a25b-443">マルチターゲット</span><span class="sxs-lookup"><span data-stu-id="5a25b-443">Multi-targeting</span></span>

<span data-ttu-id="5a25b-444">特定のターゲットフレームワークに対して `Newtonsoft.Json` を引き続き使用する必要がある場合は、複数のターゲットを持つことができ、2つの実装があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-444">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="5a25b-445">ただし、これは簡単ではなく、一部の `#ifdefs` とソースの複製が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-445">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="5a25b-446">できるだけ多くのコードを共有する方法の1つとして、`Utf8JsonReader` と `Newtonsoft.Json` `JsonTextReader`の `ref struct` ラッパーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-446">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="5a25b-447">このラッパーは、動作の違いを特定しながら、公開された領域を統合します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-447">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="5a25b-448">これにより、変更を主に型の構造に分離し、新しい型を参照渡しで渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-448">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="5a25b-449">このパターン[は、次](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-449">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="5a25b-450">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="5a25b-450">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="5a25b-451">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="5a25b-451">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="5a25b-452">Utf8JsonWriter と JsonTextWriter の比較</span><span class="sxs-lookup"><span data-stu-id="5a25b-452">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="5a25b-453"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> は、`String`、`Int32`、`DateTime`などの一般的な .NET 型から、UTF-8 でエンコードされた JSON テキストを書き込むための高パフォーマンスの方法です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-453"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="5a25b-454">ライターは、カスタムシリアライザーを構築するために使用できる低レベルの型です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-454">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="5a25b-455">以下のセクションでは、`Utf8JsonWriter`を使用するための推奨されるプログラミングパターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-455">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="5a25b-456">UTF-8 テキストを使用した書き込み</span><span class="sxs-lookup"><span data-stu-id="5a25b-456">Write with UTF-8 text</span></span>

<span data-ttu-id="5a25b-457">`Utf8JsonWriter`の使用中に最大限のパフォーマンスを実現するには、utf-16 文字列としてではなく、既に UTF-8 テキストとしてエンコードされている JSON ペイロードを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-457">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="5a25b-458"><xref:System.Text.Json.JsonEncodedText> を使用して、既知の文字列プロパティの名前と値をスタティックとしてキャッシュおよび事前エンコードし、UTF-16 文字列リテラルを使用するのではなく、ライターに渡します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-458">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="5a25b-459">これは、キャッシュし、UTF-8 バイト配列を使用するよりも高速です。</span><span class="sxs-lookup"><span data-stu-id="5a25b-459">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="5a25b-460">この方法は、カスタムエスケープを行う必要がある場合にも機能します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-460">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="5a25b-461">`System.Text.Json` では、文字列の書き込み中にエスケープを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-461">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="5a25b-462">ただし、独自のカスタム <xref:System.Text.Encodings.Web.JavaScriptEncoder> をライターにオプションとして渡すことも、`JavascriptEncoder` を使用してエスケープを行う独自の `JsonEncodedText` を作成してから、文字列の代わりに `JsonEncodedText` を書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-462">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="5a25b-463">詳細については、「[文字エンコードをカスタマイズ](system-text-json-how-to.md#customize-character-encoding)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-463">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="5a25b-464">生の値の書き込み</span><span class="sxs-lookup"><span data-stu-id="5a25b-464">Write raw values</span></span>

<span data-ttu-id="5a25b-465">`Newtonsoft.Json` `WriteRawValue` メソッドは、値が必要な場合に生の JSON を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-465">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="5a25b-466"><xref:System.Text.Json> には同等の機能はありませんが、有効な JSON だけが書き込まれるようにするための回避策を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-466"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="5a25b-467">文字エスケープのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5a25b-467">Customize character escaping</span></span>

<span data-ttu-id="5a25b-468">`JsonTextWriter` の[StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)設定には、ASCII 以外の文字**または**HTML 文字をすべてエスケープするオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-468">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="5a25b-469">既定では、`Utf8JsonWriter` は、ASCII 以外の文字**と**HTML 文字をすべてエスケープします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-469">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="5a25b-470">このエスケープは、多層防御のセキュリティ上の理由で行われます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-470">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="5a25b-471">別のエスケープポリシーを指定するには、<xref:System.Text.Encodings.Web.JavaScriptEncoder> を作成し、<xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>を設定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-471">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a25b-472">詳細については、「[文字エンコードをカスタマイズ](system-text-json-how-to.md#customize-character-encoding)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25b-472">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="5a25b-473">JSON 形式のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5a25b-473">Customize JSON format</span></span>

<span data-ttu-id="5a25b-474">`JsonTextWriter` には、次の設定が含まれており、`Utf8JsonWriter` に相当するものはありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-474">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="5a25b-475">[インデント](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm)-インデントする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-475">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="5a25b-476">`Utf8JsonWriter` 常に2文字のインデントが行われます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-476">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="5a25b-477">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) -インデントに使用する文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-477">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="5a25b-478">`Utf8JsonWriter` は常に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-478">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="5a25b-479">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) -文字列値を囲むために使用する文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-479">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="5a25b-480">`Utf8JsonWriter` は常に二重引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-480">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="5a25b-481">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) -プロパティ名を引用符で囲むかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-481">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="5a25b-482">`Utf8JsonWriter` は常に引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-482">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="5a25b-483">これらの方法で `Utf8JsonWriter` によって生成される JSON をカスタマイズできる回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-483">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="5a25b-484">Null 値の書き込み</span><span class="sxs-lookup"><span data-stu-id="5a25b-484">Write null values</span></span>

<span data-ttu-id="5a25b-485">`Utf8JsonWriter`を使用して null 値を書き込むには、次のように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-485">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="5a25b-486">値として null を持つキーと値のペアを書き込む <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-486"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="5a25b-487"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>、JSON 配列の要素として null を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-487"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="5a25b-488">文字列プロパティの場合、文字列が null の場合、<xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> と <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> は `WriteNull` と `WriteNullValue`に相当します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-488">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="5a25b-489">Timespan、Uri、または char 値の書き込み</span><span class="sxs-lookup"><span data-stu-id="5a25b-489">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="5a25b-490">`JsonTextWriter` には、 [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)、 [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)、および[char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm)値の `WriteValue` メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a25b-490">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="5a25b-491">`Utf8JsonWriter` には、同等のメソッドがありません。</span><span class="sxs-lookup"><span data-stu-id="5a25b-491">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="5a25b-492">代わりに、これらの値を文字列として書式設定し (たとえば `ToString()`を呼び出し)、<xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-492">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="5a25b-493">マルチターゲット</span><span class="sxs-lookup"><span data-stu-id="5a25b-493">Multi-targeting</span></span>

<span data-ttu-id="5a25b-494">特定のターゲットフレームワークに対して `Newtonsoft.Json` を引き続き使用する必要がある場合は、複数のターゲットを持つことができ、2つの実装があります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-494">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="5a25b-495">ただし、これは簡単ではなく、一部の `#ifdefs` とソースの複製が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a25b-495">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="5a25b-496">できるだけ多くのコードを共有する方法の1つは、`Utf8JsonWriter` のラッパーを作成し、`JsonTextWriter`を `Newtonsoft` することです。</span><span class="sxs-lookup"><span data-stu-id="5a25b-496">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="5a25b-497">このラッパーは、動作の違いを特定しながら、公開された領域を統合します。</span><span class="sxs-lookup"><span data-stu-id="5a25b-497">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="5a25b-498">これにより、主に型の構造に変更を分離できます。</span><span class="sxs-lookup"><span data-stu-id="5a25b-498">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="5a25b-499">次[のよう](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)にします。</span><span class="sxs-lookup"><span data-stu-id="5a25b-499">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="5a25b-500">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="5a25b-500">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="5a25b-501">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="5a25b-501">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="5a25b-502">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="5a25b-502">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [<span data-ttu-id="5a25b-503">System.string の概要</span><span class="sxs-lookup"><span data-stu-id="5a25b-503">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="5a25b-504">方法: system.string を使用する</span><span class="sxs-lookup"><span data-stu-id="5a25b-504">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="5a25b-505">カスタムコンバーターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="5a25b-505">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="5a25b-506">System.string での DateTime と DateTimeOffset のサポート</span><span class="sxs-lookup"><span data-stu-id="5a25b-506">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="5a25b-507">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="5a25b-507">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="5a25b-508">Text. Json. Serialization API リファレンス</span><span class="sxs-lookup"><span data-stu-id="5a25b-508">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
