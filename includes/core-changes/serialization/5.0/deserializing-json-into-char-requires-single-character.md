---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844508"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="d74ff-101">JsonSerializer.Deserialize によって 1 文字の文字列が求められる</span><span class="sxs-lookup"><span data-stu-id="d74ff-101">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="d74ff-102">型パラメーターが <xref:System.Char> の場合、正常に逆シリアル化を行うには、<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> の文字列引数に 1 文字を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d74ff-102">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d74ff-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="d74ff-103">Change description</span></span>

<span data-ttu-id="d74ff-104">以前の .NET バージョンでは、複数文字の文字列を <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> に渡し、型パラメーターが <xref:System.Char> の場合、逆シリアル化は正常に行われ、最初の文字のみが逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="d74ff-104">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="d74ff-105">.NET 5.0 以降では、型パラメーターが <xref:System.Char> の場合、1 文字の文字列以外のものを渡すと、<xref:System.Text.Json.JsonException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d74ff-105">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a><span data-ttu-id="d74ff-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d74ff-106">Version introduced</span></span>

<span data-ttu-id="d74ff-107">5.0</span><span class="sxs-lookup"><span data-stu-id="d74ff-107">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d74ff-108">変更理由</span><span class="sxs-lookup"><span data-stu-id="d74ff-108">Reason for change</span></span>

<span data-ttu-id="d74ff-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> を使用すると、1 つの JSON 値を表すテキストが、ジェネリック型パラメーターで指定された型のインスタンスに解析されます。</span><span class="sxs-lookup"><span data-stu-id="d74ff-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="d74ff-110">解析が正常に行われるのは、指定されたペイロードが指定されたジェネリック型パラメーターに対して有効な場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d74ff-110">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="d74ff-111"><xref:System.Char> 値の型の場合、有効なペイロードは 1 文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d74ff-111">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d74ff-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="d74ff-112">Recommended action</span></span>

<span data-ttu-id="d74ff-113"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> を使用して文字列を <xref:System.Char> 型に解析する場合は、文字列が 1 文字で構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d74ff-113">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

#### <a name="category"></a><span data-ttu-id="d74ff-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d74ff-114">Category</span></span>

<span data-ttu-id="d74ff-115">シリアル化</span><span class="sxs-lookup"><span data-stu-id="d74ff-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d74ff-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d74ff-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
