---
ms.openlocfilehash: 0d38e2177377e7e9ea911071eb65aa13aa1f5900
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496758"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a><span data-ttu-id="ed94d-101">.NET Framework 4.7.2 で "dataAnnotations:dataTypeAttribute:disableRegEx" アプリ設定が既定で有効になっている</span><span class="sxs-lookup"><span data-stu-id="ed94d-101">"dataAnnotations:dataTypeAttribute:disableRegEx" app setting is on by default in .NET Framework 4.7.2</span></span>

#### <a name="details"></a><span data-ttu-id="ed94d-102">説明</span><span class="sxs-lookup"><span data-stu-id="ed94d-102">Details</span></span>

<span data-ttu-id="ed94d-103">.NET framework 4.6.1 で、データ型属性 (<xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>、<xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType>、<xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType> など) で正規表現の使用を無効にするアプリ設定 (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>) が導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed94d-103">In .NET Framework 4.6.1, an app setting (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>) was introduced that allows users to disable the use of regular expressions in data type attributes (such as <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType>, and <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="ed94d-104">これにより、特定の正規表現を使用するサービス拒否攻撃の可能性を回避できるなど、セキュリティの脆弱性を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="ed94d-104">This helps to reduce security vulnerability such as avoiding the possibility of a Denial of Service attack using specific regular expressions.</span></span><br/><span data-ttu-id="ed94d-105">.NET Framework 4.6.1 で、正規表現の使用を無効にするこのアプリ設定が、既定で <code>false</code> に設定されました。</span><span class="sxs-lookup"><span data-stu-id="ed94d-105">In .NET Framework 4.6.1, this app setting to disable RegEx usage was set to <code>false</code> by default.</span></span> <span data-ttu-id="ed94d-106">.NET Framework 4.7.2 からは、この構成スイッチが既定で <code>true</code> に設定され、.NET Framework 4.7.2 以降を対象とする Web アプリケーションのセキュリティの脆弱性がさらに軽減されています。</span><span class="sxs-lookup"><span data-stu-id="ed94d-106">Starting with .NET Framework 4.7.2, this config switch is set to <code>true</code> by default to further reduce secure vulnerability for web applications that target .NET Framework 4.7.2 and above.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ed94d-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ed94d-107">Suggestion</span></span>

<span data-ttu-id="ed94d-108">.NET Framework 4.7.2 へのアップグレード後に Web アプリケーションの正規表現が動作しない場合は、<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> 設定の値を <code>false</code> に更新して以前の動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ed94d-108">If you find that regular expressions in your web application do not work after upgrading to .NET Framework 4.7.2, you can update the value of the <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> setting to <code>false</code> to revert to the previous behavior.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="ed94d-109">名前</span><span class="sxs-lookup"><span data-stu-id="ed94d-109">Name</span></span>    | <span data-ttu-id="ed94d-110">[値]</span><span class="sxs-lookup"><span data-stu-id="ed94d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ed94d-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="ed94d-111">Scope</span></span>   |<span data-ttu-id="ed94d-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="ed94d-112">Minor</span></span>|
|<span data-ttu-id="ed94d-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="ed94d-113">Version</span></span>|<span data-ttu-id="ed94d-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="ed94d-114">4.7.2</span></span>|
|<span data-ttu-id="ed94d-115">種類</span><span class="sxs-lookup"><span data-stu-id="ed94d-115">Type</span></span>|<span data-ttu-id="ed94d-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ed94d-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ed94d-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ed94d-117">Affected APIs</span></span>

<span data-ttu-id="ed94d-118">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="ed94d-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
