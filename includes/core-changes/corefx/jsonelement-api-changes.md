---
ms.openlocfilehash: 8a92a426ac2c5eee6fba40bfc46281420466d648
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237401"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="dcfa0-101">JsonElement API の変更</span><span class="sxs-lookup"><span data-stu-id="dcfa0-101">JsonElement API changes</span></span>

<span data-ttu-id="dcfa0-102">.NET Core 3.0 Preview 7 以降、一部の <xref:System.Text.Json.JsonElement> API はより検出しやすく、より使いやすく変更されています。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dcfa0-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="dcfa0-103">Change description</span></span>

<span data-ttu-id="dcfa0-104">.NET Core 3.0 Preview 7 では、<xref:System.Text.Json.JsonElement> API は次のようにより検出しやすく、より使いやすく変更されています。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="dcfa0-105">すべての `WriteProperty` メソッドのオーバーロードが <xref:System.Text.Json.JsonElement> から削除されています。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="dcfa0-106">これは、次などのコードに影響します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-106">This affects code such as the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. <span data-ttu-id="dcfa0-107">`WriteValue` は <xref:System.Text.Json.JsonElement.WriteTo%2A> に名前変更されました。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="dcfa0-108">これは、次などのコードに影響します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="dcfa0-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> で、それのメソッド パラメーターが `null` の場合に、<xref:System.ArgumentNullException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dcfa0-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dcfa0-110">Version introduced</span></span>

<span data-ttu-id="dcfa0-111">3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="dcfa0-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dcfa0-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="dcfa0-112">Recommended action</span></span>

<span data-ttu-id="dcfa0-113">これらの変更の影響をコードが受ける場合、次を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="dcfa0-114"><xref:System.Text.Json.JsonElement> に `WriteProperty` オーバーロードに対する置換 API はありません。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="dcfa0-115">同じ結果を得るには、代わりに <xref:System.Text.Json.JsonElement.WriteTo%2A> メソッドと共に <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> オーバーロードの 1 つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achive the same result.</span></span> <span data-ttu-id="dcfa0-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="dcfa0-117">`WriteValue` メソッドの名前を <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)> に変更します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="dcfa0-118">このメソッドのパラメーターは変更されません。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="dcfa0-119">たとえば、前のコードは次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="dcfa0-120"><xref:System.Text.Json.JsonElement.WriteTo%2A> メソッドへの呼び出しの <xref:System.ArgumentNullException> を処理します。</span><span class="sxs-lookup"><span data-stu-id="dcfa0-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dcfa0-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dcfa0-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
