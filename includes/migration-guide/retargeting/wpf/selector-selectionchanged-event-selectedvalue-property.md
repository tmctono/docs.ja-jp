---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614934"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="df3a3-101">セレクター SelectionChanged イベントおよび SelectedValue プロパティ</span><span class="sxs-lookup"><span data-stu-id="df3a3-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="df3a3-102">説明</span><span class="sxs-lookup"><span data-stu-id="df3a3-102">Details</span></span>

<span data-ttu-id="df3a3-103">NET Framework 4.7.1 以降、<xref:System.Windows.Controls.Primitives.Selector> は選択の変更が発生すると必ず、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントが発生する前に <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティの値を更新します。</span><span class="sxs-lookup"><span data-stu-id="df3a3-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="df3a3-104">これにより、SelectedValue プロパティと、イベント発生前に更新されるその他の選択プロパティ (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> および <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>) との整合性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="df3a3-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="df3a3-105">.NET Framework 4.7 以前のバージョンでは、ほとんどの場合、イベントの前に SelectedValue に対する更新が行われました。しかし、選択の変更が <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティの変更に起因している場合、SelectedValue に対する更新はイベントの後に行われていました。</span><span class="sxs-lookup"><span data-stu-id="df3a3-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df3a3-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="df3a3-106">Suggestion</span></span>

<span data-ttu-id="df3a3-107">.NET Framework 4.7.1 以降を対象とするアプリでこの変更を無効にし、従来の動作を使用することができます。その場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="df3a3-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="df3a3-108">.NET Framework 4.7 以前を対象とするものの、.NET Framework 4.7.1 以降で実行されているアプリでは、新しい動作を有効にすることができます。その場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="df3a3-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="df3a3-109">名前</span><span class="sxs-lookup"><span data-stu-id="df3a3-109">Name</span></span>    | <span data-ttu-id="df3a3-110">値</span><span class="sxs-lookup"><span data-stu-id="df3a3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df3a3-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="df3a3-111">Scope</span></span>   | <span data-ttu-id="df3a3-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="df3a3-112">Minor</span></span>       |
| <span data-ttu-id="df3a3-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="df3a3-113">Version</span></span> | <span data-ttu-id="df3a3-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="df3a3-114">4.7.1</span></span>       |
| <span data-ttu-id="df3a3-115">種類</span><span class="sxs-lookup"><span data-stu-id="df3a3-115">Type</span></span>    | <span data-ttu-id="df3a3-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="df3a3-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="df3a3-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="df3a3-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
