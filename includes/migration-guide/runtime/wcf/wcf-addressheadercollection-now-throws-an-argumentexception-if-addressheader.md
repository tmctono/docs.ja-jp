---
ms.openlocfilehash: d29be721b50d1c93723b325774a06e86f77dbebf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621224"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="f241f-101">addressHeader 要素が null の場合、WCF AddressHeaderCollection で ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="f241f-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="f241f-102">説明</span><span class="sxs-lookup"><span data-stu-id="f241f-102">Details</span></span>

<span data-ttu-id="f241f-103">.NET Framework 4.7.1 以降では、要素のいずれかが <code>null</code> の場合、<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> コンストラクターで <xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f241f-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="f241f-104">.NET Framework 4.7 以前のバージョンでは、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="f241f-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f241f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f241f-105">Suggestion</span></span>

<span data-ttu-id="f241f-106">.NET Framework 4.7.1 以降のバージョンでこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f241f-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f241f-107">名前</span><span class="sxs-lookup"><span data-stu-id="f241f-107">Name</span></span>    | <span data-ttu-id="f241f-108">値</span><span class="sxs-lookup"><span data-stu-id="f241f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f241f-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="f241f-109">Scope</span></span>   |<span data-ttu-id="f241f-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="f241f-110">Minor</span></span>|
|<span data-ttu-id="f241f-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="f241f-111">Version</span></span>|<span data-ttu-id="f241f-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f241f-112">4.7.1</span></span>|
|<span data-ttu-id="f241f-113">種類</span><span class="sxs-lookup"><span data-stu-id="f241f-113">Type</span></span>|<span data-ttu-id="f241f-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f241f-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f241f-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f241f-115">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
