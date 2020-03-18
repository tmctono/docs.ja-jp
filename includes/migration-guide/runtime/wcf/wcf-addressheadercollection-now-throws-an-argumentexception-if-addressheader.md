---
ms.openlocfilehash: d8c9cec723ec4e57fb4868cc95881be8eb4001b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857249"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="7d6b3-101">addressHeader 要素が null の場合、WCF AddressHeaderCollection で ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="7d6b3-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7d6b3-102">説明</span><span class="sxs-lookup"><span data-stu-id="7d6b3-102">Details</span></span>|<span data-ttu-id="7d6b3-103">.NET Framework 4.7.1 以降では、要素のいずれかが <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> の場合、<xref:System.ArgumentException> コンストラクターで <code>null</code> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="7d6b3-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="7d6b3-104">.NET Framework 4.7 以前のバージョンでは、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="7d6b3-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>|
|<span data-ttu-id="7d6b3-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7d6b3-105">Suggestion</span></span>|<span data-ttu-id="7d6b3-106">.NET Framework 4.7.1 以降のバージョンでこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7d6b3-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="7d6b3-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="7d6b3-107">Scope</span></span>|<span data-ttu-id="7d6b3-108">Minor</span><span class="sxs-lookup"><span data-stu-id="7d6b3-108">Minor</span></span>|
|<span data-ttu-id="7d6b3-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="7d6b3-109">Version</span></span>|<span data-ttu-id="7d6b3-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7d6b3-110">4.7.1</span></span>|
|<span data-ttu-id="7d6b3-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="7d6b3-111">Type</span></span>|<span data-ttu-id="7d6b3-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7d6b3-112">Runtime</span></span>|
|<span data-ttu-id="7d6b3-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7d6b3-113">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|
