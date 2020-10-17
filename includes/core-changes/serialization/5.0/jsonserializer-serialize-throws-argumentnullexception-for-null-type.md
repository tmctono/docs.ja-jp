---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955339"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>型パラメーターが null の場合に JsonSerializer.Serialize によって ArgumentNullException がスローされる

<xref:System.Type> パラメーターに `null` が渡されるたびに、<xref:System.Type> パラメーターを持つ <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>、<xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>、<xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> のオーバーロードによって <xref:System.ArgumentNullException> がスローされるようになりました。

#### <a name="change-description"></a>変更内容

.NET Core 3.1 では、`Type inputType` パラメーターに `null` が渡されると、<xref:System.Type> パラメーターを持つ <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>、<xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>、<xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> のオーバーロードによって <xref:System.ArgumentNullException> がスローされますが、`Object value` パラメーターも `null` の場合はされません。 .NET 5.0 以降では、`null` が <xref:System.Type> パラメーターに渡されると、これらのメソッドによって "*常に*" <xref:System.ArgumentNullException> がスローされます。

.NET Core 3.1 での動作:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

.NET 5.0 以降での動作:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="reason-for-change"></a>変更理由

`Type inputType` パラメーターに `null` を渡すことは許容されておらず、常に <xref:System.ArgumentNullException> をスローする必要があります。

#### <a name="recommended-action"></a>推奨される操作

これらのメソッドの `Type inputType` パラメーターに `null` が渡されていないことを確認します。

#### <a name="category"></a>カテゴリ

シリアル化

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
