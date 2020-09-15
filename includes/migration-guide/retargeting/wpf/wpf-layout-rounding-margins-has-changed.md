---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615723"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="285e9-101">WPF レイアウトでの余白の丸め方の変更</span><span class="sxs-lookup"><span data-stu-id="285e9-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="285e9-102">説明</span><span class="sxs-lookup"><span data-stu-id="285e9-102">Details</span></span>

<span data-ttu-id="285e9-103">余白、境界線、およびそれらの内部の背景の丸め処理の方法が変更されました。</span><span class="sxs-lookup"><span data-stu-id="285e9-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="285e9-104">この変更の結果、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="285e9-104">As a result of this change:</span></span>

- <span data-ttu-id="285e9-105">要素の幅または高さが最大で 1 ピクセル拡大または縮小することがあります。</span><span class="sxs-lookup"><span data-stu-id="285e9-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="285e9-106">オブジェクトの配置が最大で 1 ピクセル移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="285e9-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="285e9-107">中央揃えの要素が中央から最大で 1 ピクセル垂直まは水平方向にずれることがあります。</span><span class="sxs-lookup"><span data-stu-id="285e9-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="285e9-108">既定では、この新しいレイアウトは .NET Framework の 4.6 を対象とするアプリに対してのみ有効となります。</span><span class="sxs-lookup"><span data-stu-id="285e9-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="285e9-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="285e9-109">Suggestion</span></span>

<span data-ttu-id="285e9-110">この変更では、DPI が高いときにWPF コントロールの一番右または一番下でクリッピングの発生を除去する傾向があるため、app.config ファイルの `<runtime>` セクションに次の行を追加することによって、以前のバージョンの .NET Framework を対象としながら .NET Framework 4.6 上で実行されているアプリがこの新しい動作を選択ことができます。</span><span class="sxs-lookup"><span data-stu-id="285e9-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="285e9-111">.NET Framework 4.6 を対象としながら以前のレイアウト アルゴリズムを使用して WPF コントロールをレンダリングする必要があるアプリの場合、app.config ファイルの `<runtime>` セクションに次の行を追加することによってそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="285e9-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="285e9-112">名前</span><span class="sxs-lookup"><span data-stu-id="285e9-112">Name</span></span>    | <span data-ttu-id="285e9-113">値</span><span class="sxs-lookup"><span data-stu-id="285e9-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="285e9-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="285e9-114">Scope</span></span>   | <span data-ttu-id="285e9-115">マイナー</span><span class="sxs-lookup"><span data-stu-id="285e9-115">Minor</span></span>       |
| <span data-ttu-id="285e9-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="285e9-116">Version</span></span> | <span data-ttu-id="285e9-117">4.6</span><span class="sxs-lookup"><span data-stu-id="285e9-117">4.6</span></span>         |
| <span data-ttu-id="285e9-118">種類</span><span class="sxs-lookup"><span data-stu-id="285e9-118">Type</span></span>    | <span data-ttu-id="285e9-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="285e9-119">Retargeting</span></span> |
