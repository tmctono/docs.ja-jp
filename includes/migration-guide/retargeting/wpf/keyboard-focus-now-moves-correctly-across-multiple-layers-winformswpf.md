---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614947"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="93a11-101">キーボード フォーカスが WinForms/WPF ホストの複数層の間で正しく移動するようになった</span><span class="sxs-lookup"><span data-stu-id="93a11-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="93a11-102">説明</span><span class="sxs-lookup"><span data-stu-id="93a11-102">Details</span></span>

<span data-ttu-id="93a11-103">WinForms コントロールをホストし、さらに WPF コントロールをホストする WPF アプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="93a11-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="93a11-104">WinForms 層の最初または最後のコントロールが WPF `System.Windows.Forms.Integration.ElementHost` である場合、ユーザーはこの層を Tab キーで移動できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="93a11-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="93a11-105">今回の変更でこの問題が修正され、ユーザーは WinForms 層を Tab キーで移動できるようになりました。WinForms 層をエスケープしないフォーカスに依存する自動アプリケーションは、期待どおりに動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93a11-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="93a11-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="93a11-106">Suggestion</span></span>

<span data-ttu-id="93a11-107">.NET 4.7.2 より前のバージョンのフレームワークを対象とするときに、この変更を利用する開発者は、次の一連の AppContext フラグを false に設定することで変更を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="93a11-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="93a11-108">WPF アプリケーションでより新しい改善を得るには、アクセシビリティに関する以前の改善をすべてオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93a11-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="93a11-109">つまり、`Switch.UseLegacyAccessibilityFeatures` および `Switch.UseLegacyAccessibilityFeatures.2` スイッチの両方が設定されている必要があります。 .NET 4.7.2 以降を対象とするときに、前の機能を必要とする開発者は、次の AppContext フラグを true に設定することで変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="93a11-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="93a11-110">名前</span><span class="sxs-lookup"><span data-stu-id="93a11-110">Name</span></span>    | <span data-ttu-id="93a11-111">[値]</span><span class="sxs-lookup"><span data-stu-id="93a11-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="93a11-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="93a11-112">Scope</span></span>   | <span data-ttu-id="93a11-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="93a11-113">Edge</span></span>        |
| <span data-ttu-id="93a11-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="93a11-114">Version</span></span> | <span data-ttu-id="93a11-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="93a11-115">4.7.2</span></span>       |
| <span data-ttu-id="93a11-116">種類</span><span class="sxs-lookup"><span data-stu-id="93a11-116">Type</span></span>    | <span data-ttu-id="93a11-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="93a11-117">Retargeting</span></span> |
