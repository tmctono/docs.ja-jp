---
ms.openlocfilehash: 3506653bfc749ae3d8002715ca72ca89de7a681b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024867"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="94fac-101">addressHeader 要素が null の場合、WCF AddressHeaderCollection で ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="94fac-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="94fac-102">説明</span><span class="sxs-lookup"><span data-stu-id="94fac-102">Details</span></span>

<span data-ttu-id="94fac-103">.NET Framework 4.7.1 以降では、要素のいずれかが `null` の場合、<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> コンストラクターで <xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="94fac-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="94fac-104">.NET Framework 4.7 以前のバージョンでは、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="94fac-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="94fac-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="94fac-105">Suggestion</span></span>

<span data-ttu-id="94fac-106">.NET Framework 4.7.1 以降のバージョンでこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの `<runtime>` セクションに追加することで、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="94fac-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="94fac-107">Name</span><span class="sxs-lookup"><span data-stu-id="94fac-107">Name</span></span>    | <span data-ttu-id="94fac-108">値</span><span class="sxs-lookup"><span data-stu-id="94fac-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="94fac-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="94fac-109">Scope</span></span>   | <span data-ttu-id="94fac-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="94fac-110">Minor</span></span>   |
| <span data-ttu-id="94fac-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="94fac-111">Version</span></span> | <span data-ttu-id="94fac-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="94fac-112">4.7.1</span></span>   |
| <span data-ttu-id="94fac-113">種類</span><span class="sxs-lookup"><span data-stu-id="94fac-113">Type</span></span>    | <span data-ttu-id="94fac-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="94fac-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="94fac-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="94fac-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
