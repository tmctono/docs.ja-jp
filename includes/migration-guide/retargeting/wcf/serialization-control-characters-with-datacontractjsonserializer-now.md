---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614793"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="e13a7-101">DataContractJsonSerializer による制御文字のシリアル化が ECMAScript V6 および V8 対応に</span><span class="sxs-lookup"><span data-stu-id="e13a7-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="e13a7-102">説明</span><span class="sxs-lookup"><span data-stu-id="e13a7-102">Details</span></span>

<span data-ttu-id="e13a7-103">.NET framework 4.6.2 以前のバージョンでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> で、ECMAScript V6 および V8 標準と互換性がある方法で \b、\f、\t などの一部の特殊制御文字がシリアル化されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e13a7-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="e13a7-104">.NET Framework 4.7 以降、これらの制御文字のシリアル化は ECMAScript V6 および V8 と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="e13a7-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e13a7-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e13a7-105">Suggestion</span></span>

<span data-ttu-id="e13a7-106">.NET Framework 4.7 を対象とするアプリの場合、この機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e13a7-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="e13a7-107">この動作が望ましくない場合は、app.config または web.config ファイルの `<runtime>` セクションに次の行を追加して、この機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e13a7-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="e13a7-108">名前</span><span class="sxs-lookup"><span data-stu-id="e13a7-108">Name</span></span>    | <span data-ttu-id="e13a7-109">値</span><span class="sxs-lookup"><span data-stu-id="e13a7-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e13a7-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="e13a7-110">Scope</span></span>   | <span data-ttu-id="e13a7-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="e13a7-111">Edge</span></span>        |
| <span data-ttu-id="e13a7-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="e13a7-112">Version</span></span> | <span data-ttu-id="e13a7-113">4.7</span><span class="sxs-lookup"><span data-stu-id="e13a7-113">4.7</span></span>         |
| <span data-ttu-id="e13a7-114">種類</span><span class="sxs-lookup"><span data-stu-id="e13a7-114">Type</span></span>    | <span data-ttu-id="e13a7-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="e13a7-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e13a7-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e13a7-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
