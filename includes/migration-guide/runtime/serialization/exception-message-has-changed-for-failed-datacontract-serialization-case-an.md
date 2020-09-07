---
ms.openlocfilehash: 8d0404c728231f596500653d556e3be6fcc20c2c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496728"
---
### <a name="exception-message-has-changed-for-failed-datacontract-serialization-in-case-of-an-unknown-type"></a>不明な型の場合に失敗した DataContract シリアル化の例外メッセージが変更された

#### <a name="details"></a>説明

.NET Framework 4.6 以降では、"既知の型" がないために <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> または <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> のシリアル化または逆シリアル化が失敗した場合に提供される例外メッセージが明確化されました。

#### <a name="suggestion"></a>提案される解決策

アプリは、特定の例外メッセージに依存しないようにする必要があります。 アプリがこのメッセージに依存している場合は、新しいメッセージを使うように更新するか、(可能であれば) 例外の種類のみに依存するように変更します。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Runtime.Serialization.Json.DataContractJsonSerializerSettings)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Runtime.Serialization.DataContractSerializerSettings)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)>
- <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Runtime.Serialization.Json.DataContractJsonSerializerSettings)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.String)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)`
- `M:System.Runtime.Serialization.Json.DataContractJsonSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Runtime.Serialization.DataContractSerializerSettings)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.String,System.String)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)`
- `M:System.Runtime.Serialization.DataContractSerializer.#ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)`

-->
