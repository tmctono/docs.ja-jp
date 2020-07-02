---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621973"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="17787-101">ASP.NET WebForms CheckBox コントロールの InputAttributes および LabelAttributes の処理の修正</span><span class="sxs-lookup"><span data-stu-id="17787-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="17787-102">説明</span><span class="sxs-lookup"><span data-stu-id="17787-102">Details</span></span>

<span data-ttu-id="17787-103">.NET Framework 4.7.2 以前のバージョンをターゲットとするアプリケーションでは、WebForms <xref:System.Web.UI.WebControls.CheckBox> コントロールにプログラムで追加された <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> および <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> がポストバック後に失われます。</span><span class="sxs-lookup"><span data-stu-id="17787-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="17787-104">.NET Framework 4.8 以降のバージョンをターゲットとするアプリケーションでは、これらはポストバック後に保持されます。</span><span class="sxs-lookup"><span data-stu-id="17787-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="17787-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="17787-105">Suggestion</span></span>

<span data-ttu-id="17787-106">ポストバック時に属性を復元する動作を正しいものにするには、<code>targetFrameworkVersion</code> を 4.8 以降に設定します。</span><span class="sxs-lookup"><span data-stu-id="17787-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="17787-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="17787-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="17787-108">これより小さい値に設定した場合、または、まったく設定しない場合、適切でない古い動作が維持されます。</span><span class="sxs-lookup"><span data-stu-id="17787-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="17787-109">名前</span><span class="sxs-lookup"><span data-stu-id="17787-109">Name</span></span>    | <span data-ttu-id="17787-110">[値]</span><span class="sxs-lookup"><span data-stu-id="17787-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="17787-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="17787-111">Scope</span></span>   |<span data-ttu-id="17787-112">不明</span><span class="sxs-lookup"><span data-stu-id="17787-112">Unknown</span></span>|
|<span data-ttu-id="17787-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="17787-113">Version</span></span>|<span data-ttu-id="17787-114">4.8</span><span class="sxs-lookup"><span data-stu-id="17787-114">4.8</span></span>|
|<span data-ttu-id="17787-115">種類</span><span class="sxs-lookup"><span data-stu-id="17787-115">Type</span></span>|<span data-ttu-id="17787-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="17787-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="17787-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="17787-117">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
