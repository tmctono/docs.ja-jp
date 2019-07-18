---
ms.openlocfilehash: e605e0f2636d83745815ec4ed27bf72692f18d15
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802679"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="d7f69-101">ASP.NET WebForms CheckBox コントロールの InputAttributes および LabelAttributes の処理の修正</span><span class="sxs-lookup"><span data-stu-id="d7f69-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d7f69-102">説明</span><span class="sxs-lookup"><span data-stu-id="d7f69-102">Details</span></span>|<span data-ttu-id="d7f69-103">.NET Framework 4.7.2 以前のバージョンをターゲットとするアプリケーションでは、WebForms <xref:System.Web.UI.WebControls.CheckBox> コントロールにプログラムで追加された <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> および <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> がポストバック後に失われます。</span><span class="sxs-lookup"><span data-stu-id="d7f69-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="d7f69-104">.NET Framework 4.8 以降のバージョンをターゲットとするアプリケーションでは、これらはポストバック後に保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7f69-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>|
|<span data-ttu-id="d7f69-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d7f69-105">Suggestion</span></span>|<span data-ttu-id="d7f69-106">ポストバック時に属性を復元する動作を正しいものにするには、<code>targetFrameworkVersion</code> を 4.8 以降に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7f69-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="d7f69-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d7f69-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="d7f69-108">これより小さい値に設定した場合、または、まったく設定しない場合、適切でない古い動作が維持されます。</span><span class="sxs-lookup"><span data-stu-id="d7f69-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>|
|<span data-ttu-id="d7f69-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d7f69-109">Scope</span></span>|<span data-ttu-id="d7f69-110">不明</span><span class="sxs-lookup"><span data-stu-id="d7f69-110">Unknown</span></span>|
|<span data-ttu-id="d7f69-111">Version</span><span class="sxs-lookup"><span data-stu-id="d7f69-111">Version</span></span>|<span data-ttu-id="d7f69-112">4.8</span><span class="sxs-lookup"><span data-stu-id="d7f69-112">4.8</span></span>|
|<span data-ttu-id="d7f69-113">型</span><span class="sxs-lookup"><span data-stu-id="d7f69-113">Type</span></span>|<span data-ttu-id="d7f69-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d7f69-114">Runtime</span></span>|
|<span data-ttu-id="d7f69-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d7f69-115">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|

