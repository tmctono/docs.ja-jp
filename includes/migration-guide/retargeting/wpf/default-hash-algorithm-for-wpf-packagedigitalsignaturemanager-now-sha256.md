---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614919"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="8ecae-101">WPF PackageDigitalSignatureManager の既定のハッシュ アルゴリズムが SHA256 になりました</span><span class="sxs-lookup"><span data-stu-id="8ecae-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="8ecae-102">説明</span><span class="sxs-lookup"><span data-stu-id="8ecae-102">Details</span></span>

<span data-ttu-id="8ecae-103">`System.IO.Packaging.PackageDigitalSignatureManager` は、WPF パッケージに関連してデジタル署名の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8ecae-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="8ecae-104">.NET Framework 4.7 以前のバージョンでは、パッケージのパーツへの署名に使用される既定のアルゴリズム (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) は SHA1 でした。</span><span class="sxs-lookup"><span data-stu-id="8ecae-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="8ecae-105">最近明らかになった SHA1 のセキュリティに関する懸念事項により、この既定値は .NET Framework 4.7.1 で開始する SHA256 に変更されています。</span><span class="sxs-lookup"><span data-stu-id="8ecae-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="8ecae-106">この変更は、XPS ドキュメントを含むあらゆるパッケージの署名に影響します。</span><span class="sxs-lookup"><span data-stu-id="8ecae-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ecae-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8ecae-107">Suggestion</span></span>

<span data-ttu-id="8ecae-108">.NET Framework 4.7.1 より前のフレームワーク バージョンを対象とするときにこの変更を利用する開発者または .NET Framework 4.7.1 以上を対象とするときに以前の機能を必要とする開発者は、次の AppContext フラグを適宜設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8ecae-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="8ecae-109">true の値を設定すると、SHA1 が既定のアルゴリズムとして使用され、false の値を設定すると SHA256 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ecae-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8ecae-110">名前</span><span class="sxs-lookup"><span data-stu-id="8ecae-110">Name</span></span>    | <span data-ttu-id="8ecae-111">[値]</span><span class="sxs-lookup"><span data-stu-id="8ecae-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ecae-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="8ecae-112">Scope</span></span>   | <span data-ttu-id="8ecae-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="8ecae-113">Edge</span></span>        |
| <span data-ttu-id="8ecae-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="8ecae-114">Version</span></span> | <span data-ttu-id="8ecae-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="8ecae-115">4.7.1</span></span>       |
| <span data-ttu-id="8ecae-116">種類</span><span class="sxs-lookup"><span data-stu-id="8ecae-116">Type</span></span>    | <span data-ttu-id="8ecae-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="8ecae-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8ecae-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8ecae-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
