---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615648"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="ca599-101">HtmlTextWriter によって `<br/>` 要素が正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="ca599-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="ca599-102">説明</span><span class="sxs-lookup"><span data-stu-id="ca599-102">Details</span></span>

<span data-ttu-id="ca599-103">.NET Framework 4.6 以降では、`<BR />` 要素を指定して <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> と <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> を呼び出すと、`<BR />` が 1 つのみ (2 つではなく) 正しく挿入されます。</span><span class="sxs-lookup"><span data-stu-id="ca599-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ca599-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ca599-104">Suggestion</span></span>

<span data-ttu-id="ca599-105">アプリが余分な `<BR />` タグに依存している場合は、<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> をもう一度呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca599-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="ca599-106">この動作の変更は、.NET Framework 4.6 以降を対象とするアプリにのみ影響するので、以前の動作を得るためには、以前のバージョンの .NET Framework を対象とするという方法もあります。</span><span class="sxs-lookup"><span data-stu-id="ca599-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="ca599-107">名前</span><span class="sxs-lookup"><span data-stu-id="ca599-107">Name</span></span>    | <span data-ttu-id="ca599-108">値</span><span class="sxs-lookup"><span data-stu-id="ca599-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ca599-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="ca599-109">Scope</span></span>   | <span data-ttu-id="ca599-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="ca599-110">Edge</span></span>        |
| <span data-ttu-id="ca599-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="ca599-111">Version</span></span> | <span data-ttu-id="ca599-112">4.6</span><span class="sxs-lookup"><span data-stu-id="ca599-112">4.6</span></span>         |
| <span data-ttu-id="ca599-113">種類</span><span class="sxs-lookup"><span data-stu-id="ca599-113">Type</span></span>    | <span data-ttu-id="ca599-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ca599-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ca599-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ca599-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
