---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119084"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="41266-101">`JsonException` から `NotSupportedException` に変更された Json シリアライザーの例外の型</span><span class="sxs-lookup"><span data-stu-id="41266-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="41266-102">.NET Core 3.0 Preview 6 から 8 では、サポート対象外の派生コレクション型が検出されると、<xref:System.Text.Json.JsonException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="41266-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="41266-103">.NET Core 3.0 Preview 9 以降では、シリアライザーによって <xref:System.NotSupportedException> が代わりにスローされます。</span><span class="sxs-lookup"><span data-stu-id="41266-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="41266-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="41266-104">Change description</span></span>

<span data-ttu-id="41266-105">.NET Core 3.0 Preview 6 から Preview 8 では、サポート対象外の派生コレクション型が検出されると、<xref:System.Text.Json.JsonException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="41266-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="41266-106">"*サポート対象外の派生コレクション型*" とは、次のいずれかの型に割り当てることができない任意のコレクション型です。</span><span class="sxs-lookup"><span data-stu-id="41266-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

 - <xref:System.Collections.IList>
 - <xref:System.Collections.Generic.ICollection%601>
 - <xref:System.Collections.Generic.Stack%601>
 - <xref:System.Collections.Generic.Queue%601>`
 - <xref:System.Collections.IDictionary>
 - [<span data-ttu-id="41266-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="41266-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="41266-108">.NET Core 3.0 Preview 9 以降では、シリアライザーでサポート対象外のコレクション型が検出されると、<xref:System.NotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="41266-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="41266-109">新しい例外の型の方が、逆シリアル化操作が失敗する理由がよくわかります。</span><span class="sxs-lookup"><span data-stu-id="41266-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41266-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="41266-110">Version introduced</span></span>

<span data-ttu-id="41266-111">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="41266-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41266-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="41266-112">Recommended action</span></span>

<span data-ttu-id="41266-113">逆シリアル化時に <xref:System.Text.Json.JsonException> をキャッチする場合は、<xref:System.NotSupportedException> もキャッチすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="41266-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="41266-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="41266-114">Category</span></span>

<span data-ttu-id="41266-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="41266-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41266-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="41266-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
