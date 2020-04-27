---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021660"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="c3e9f-101">`JsonException` から `NotSupportedException` に変更された Json シリアライザーの例外の型</span><span class="sxs-lookup"><span data-stu-id="c3e9f-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="c3e9f-102">.NET Core 3.0 Preview 6 から 8 では、サポート対象外の派生コレクション型が検出されると、<xref:System.Text.Json.JsonException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c3e9f-103">.NET Core 3.0 Preview 9 以降では、シリアライザーによって <xref:System.NotSupportedException> が代わりにスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c3e9f-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c3e9f-104">Change description</span></span>

<span data-ttu-id="c3e9f-105">.NET Core 3.0 Preview 6 から Preview 8 では、サポート対象外の派生コレクション型が検出されると、<xref:System.Text.Json.JsonException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c3e9f-106">"*サポート対象外の派生コレクション型*" とは、次のいずれかの型に割り当てることができない任意のコレクション型です。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="c3e9f-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="c3e9f-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="c3e9f-108">.NET Core 3.0 Preview 9 以降では、シリアライザーでサポート対象外のコレクション型が検出されると、<xref:System.NotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="c3e9f-109">新しい例外の型の方が、逆シリアル化操作が失敗する理由がよくわかります。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c3e9f-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c3e9f-110">Version introduced</span></span>

<span data-ttu-id="c3e9f-111">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="c3e9f-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c3e9f-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c3e9f-112">Recommended action</span></span>

<span data-ttu-id="c3e9f-113">逆シリアル化時に <xref:System.Text.Json.JsonException> をキャッチする場合は、<xref:System.NotSupportedException> もキャッチすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3e9f-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="c3e9f-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c3e9f-114">Category</span></span>

<span data-ttu-id="c3e9f-115">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="c3e9f-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c3e9f-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c3e9f-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
