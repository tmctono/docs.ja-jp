---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844508"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer.Deserialize によって 1 文字の文字列が求められる

型パラメーターが <xref:System.Char> の場合、正常に逆シリアル化を行うには、<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> の文字列引数に 1 文字を含める必要があります。

#### <a name="change-description"></a>変更内容

以前の .NET バージョンでは、複数文字の文字列を <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> に渡し、型パラメーターが <xref:System.Char> の場合、逆シリアル化は正常に行われ、最初の文字のみが逆シリアル化されます。

.NET 5.0 以降では、型パラメーターが <xref:System.Char> の場合、1 文字の文字列以外のものを渡すと、<xref:System.Text.Json.JsonException> がスローされます。

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="reason-for-change"></a>変更理由

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> を使用すると、1 つの JSON 値を表すテキストが、ジェネリック型パラメーターで指定された型のインスタンスに解析されます。 解析が正常に行われるのは、指定されたペイロードが指定されたジェネリック型パラメーターに対して有効な場合のみです。 <xref:System.Char> 値の型の場合、有効なペイロードは 1 文字の文字列です。

#### <a name="recommended-action"></a>推奨される操作

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> を使用して文字列を <xref:System.Char> 型に解析する場合は、文字列が 1 文字で構成されていることを確認してください。

#### <a name="category"></a>カテゴリ

シリアル化

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
