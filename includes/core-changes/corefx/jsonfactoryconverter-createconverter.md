---
ms.openlocfilehash: f5b0064f9f01923c6353fd8e2b274bd7407ccbd8
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237399"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="de0be-101">JsonFactoryConverter.CreateConverter 署名が変更されました</span><span class="sxs-lookup"><span data-stu-id="de0be-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="de0be-102"><xref:System.Text.Json.Serialization.JsonConverterFactory> クラスの合成を容易にするために、<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> メソッドが公開され、<xref:System.Text.Json.JsonSerializerOptions> 型の 2 番目の引数が指定されました。</span><span class="sxs-lookup"><span data-stu-id="de0be-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="de0be-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="de0be-103">Change description</span></span>

<span data-ttu-id="de0be-104">.NET Core バージョン 3.0 Preview 8 より前の `CreateConverter` メソッドの署名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de0be-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span> 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="de0be-105">.NET Core 3.0 Preview 8 以降のバージョンでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="de0be-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="de0be-106">この変更の前は、シールド ファクトリ コンバーターを作成することは、そこから <xref:System.Text.Json.Serialization.JsonConverter%601> を取得する簡単な方法がなかったため困難でした。</span><span class="sxs-lookup"><span data-stu-id="de0be-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="de0be-107">ファクトリ メソッドを公開し、現在の <xref:System.Text.Json.JsonSerializerOptions> も渡すことによって、より柔軟な作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de0be-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="de0be-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="de0be-108">Version introduced</span></span>

<span data-ttu-id="de0be-109">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="de0be-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="de0be-110">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="de0be-110">Recommended action</span></span>

<span data-ttu-id="de0be-111">派生クラスを更新して再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de0be-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="de0be-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="de0be-112">Affected APIs</span></span>

<span data-ttu-id="de0be-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="de0be-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
