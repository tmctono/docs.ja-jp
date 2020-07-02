---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614948"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="ae7cc-101">TabControl SelectionChanged イベントおよび SelectedContent プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae7cc-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="ae7cc-102">説明</span><span class="sxs-lookup"><span data-stu-id="ae7cc-102">Details</span></span>

<span data-ttu-id="ae7cc-103">.NET Framework 4.7.1、以降の<xref:System.Windows.Controls.TabControl>の値を更新、<xref:System.Windows.Controls.TabControl.SelectedContent>を発生させる前に、プロパティ、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>イベント、その選択が変更されたときにします。 .NET Framework 4.7 と以前のバージョンでは、イベント後に SelectedContent への更新が発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae7cc-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ae7cc-104">Suggestion</span></span>

<span data-ttu-id="ae7cc-105">.NET Framework 4.7.1 以降を対象とするアプリでこの変更を無効にし、従来の動作を使用することができます。その場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="ae7cc-106">.NET Framework 4.7 以前を対象とするものの、.NET Framework 4.7.1 以降で実行されているアプリでは、新しい動作を有効にすることができます。その場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="ae7cc-107">名前</span><span class="sxs-lookup"><span data-stu-id="ae7cc-107">Name</span></span>    | <span data-ttu-id="ae7cc-108">値</span><span class="sxs-lookup"><span data-stu-id="ae7cc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae7cc-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="ae7cc-109">Scope</span></span>   | <span data-ttu-id="ae7cc-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="ae7cc-110">Minor</span></span>       |
| <span data-ttu-id="ae7cc-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="ae7cc-111">Version</span></span> | <span data-ttu-id="ae7cc-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="ae7cc-112">4.7.1</span></span>       |
| <span data-ttu-id="ae7cc-113">種類</span><span class="sxs-lookup"><span data-stu-id="ae7cc-113">Type</span></span>    | <span data-ttu-id="ae7cc-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ae7cc-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ae7cc-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ae7cc-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
