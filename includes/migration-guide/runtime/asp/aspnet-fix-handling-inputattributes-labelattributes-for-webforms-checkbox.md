---
ms.openlocfilehash: 55a26f1ab27792cbedf3f31b797f37d3f768d51a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496796"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="b193a-101">ASP.NET WebForms CheckBox コントロールの InputAttributes および LabelAttributes の処理の修正</span><span class="sxs-lookup"><span data-stu-id="b193a-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="b193a-102">説明</span><span class="sxs-lookup"><span data-stu-id="b193a-102">Details</span></span>

<span data-ttu-id="b193a-103">.NET Framework 4.7.2 以前のバージョンをターゲットとするアプリケーションでは、WebForms <xref:System.Web.UI.WebControls.CheckBox> コントロールにプログラムで追加された <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> および <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> がポストバック後に失われます。</span><span class="sxs-lookup"><span data-stu-id="b193a-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="b193a-104">.NET Framework 4.8 以降のバージョンをターゲットとするアプリケーションでは、これらはポストバック後に保持されます。</span><span class="sxs-lookup"><span data-stu-id="b193a-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b193a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b193a-105">Suggestion</span></span>

<span data-ttu-id="b193a-106">ポストバック時に属性を復元する動作を正しいものにするには、<code>targetFrameworkVersion</code> を 4.8 以降に設定します。</span><span class="sxs-lookup"><span data-stu-id="b193a-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="b193a-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b193a-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="b193a-108">これより小さい値に設定した場合、または、まったく設定しない場合、適切でない古い動作が維持されます。</span><span class="sxs-lookup"><span data-stu-id="b193a-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="b193a-109">名前</span><span class="sxs-lookup"><span data-stu-id="b193a-109">Name</span></span>    | <span data-ttu-id="b193a-110">[値]</span><span class="sxs-lookup"><span data-stu-id="b193a-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b193a-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="b193a-111">Scope</span></span>   |<span data-ttu-id="b193a-112">不明</span><span class="sxs-lookup"><span data-stu-id="b193a-112">Unknown</span></span>|
|<span data-ttu-id="b193a-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="b193a-113">Version</span></span>|<span data-ttu-id="b193a-114">4.8</span><span class="sxs-lookup"><span data-stu-id="b193a-114">4.8</span></span>|
|<span data-ttu-id="b193a-115">種類</span><span class="sxs-lookup"><span data-stu-id="b193a-115">Type</span></span>|<span data-ttu-id="b193a-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b193a-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b193a-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b193a-117">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.UI.WebControls.CheckBox`

-->
