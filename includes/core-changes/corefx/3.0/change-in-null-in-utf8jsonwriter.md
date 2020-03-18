---
ms.openlocfilehash: 7c39fe7ffd59fa7a5564bb45f32a6a2fbe0ddb33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568196"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="c9668-101">Utf8JsonWriter での `(string)null` のセマンティクスの変更</span><span class="sxs-lookup"><span data-stu-id="c9668-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="c9668-102">.NET Core 3.0 プレビュー 7 では、null 文字列は <xref:System.Text.Json.Utf8JsonWriter> 内で空の文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="c9668-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="c9668-103">.NET Core 3.0 Preview 8 以降、null 文字列は、プロパティ名として使用される場合は例外をスローし、値として使用される場合は JSON null トークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="c9668-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c9668-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c9668-104">Change description</span></span>

<span data-ttu-id="c9668-105">.NET Core 3.0 Preview 7 では、プロパティ名を作成する場合も値を作成する場合も、`null` 文字列は `""` として扱われていました。</span><span class="sxs-lookup"><span data-stu-id="c9668-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="c9668-106">.NET Core 3.0 Preview 8 以降、`null` プロパティ名によって `ArgumentNullException` がスローされ、`null` 値は <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> または <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType> の呼び出しとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="c9668-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="c9668-107">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c9668-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="c9668-108">.NET Core 3.0 Preview 7 で実行する場合、作成者は次の出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9668-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="c9668-109">.NET Core 3.0 Preview 8 以降、`writer.WriteString(propertyName1, propertyValue1)` の呼び出しによって <xref:System.ArgumentNullException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c9668-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="c9668-110">`propertyName1 = null` を `propertyName1 = string.Empty` に置き換えると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9668-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="c9668-111">この変更により、`null` 値に対する呼び出し元の期待との一致性が向上します。</span><span class="sxs-lookup"><span data-stu-id="c9668-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c9668-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c9668-112">Version introduced</span></span>

<span data-ttu-id="c9668-113">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="c9668-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c9668-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c9668-114">Recommended action</span></span>

<span data-ttu-id="c9668-115"><xref:System.Text.Json.Utf8JsonWriter> クラスを使用してプロパティ名および値を作成する場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9668-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="c9668-116">`null` 以外の文字列がプロパティ名として使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c9668-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="c9668-117">以前の動作が望ましい場合は、null 合体呼び出し (たとえば、`writer.WriteString(propertyName1 ?? "", propertyValue1)`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9668-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="c9668-118">`null` 文字列値の `null` リテラルを作成することが望ましくない場合は、null 合体呼び出し (たとえば、`writer.WriteString(propertyName2, propertyValue2 ?? "")`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9668-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="c9668-119">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c9668-119">Category</span></span>

<span data-ttu-id="c9668-120">CoreFx</span><span class="sxs-lookup"><span data-stu-id="c9668-120">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c9668-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c9668-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
