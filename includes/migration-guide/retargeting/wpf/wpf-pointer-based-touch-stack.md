---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614892"
---
### <a name="wpf-pointer-based-touch-stack"></a><span data-ttu-id="0e430-101">WPF ポインター ベースのタッチ スタック</span><span class="sxs-lookup"><span data-stu-id="0e430-101">WPF Pointer-Based Touch Stack</span></span>

#### <a name="details"></a><span data-ttu-id="0e430-102">説明</span><span class="sxs-lookup"><span data-stu-id="0e430-102">Details</span></span>

<span data-ttu-id="0e430-103">この変更で、オプションの WM_POINTER ベースの WPF タッチ/スタイラス スタックを有効にする機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="0e430-103">This change adds the ability to enable an optional WM_POINTER based WPF touch/stylus stack.</span></span>  <span data-ttu-id="0e430-104">これを明示的に有効にしていない開発者は、WPF タッチ/スタイラス動作の変更を確認できません。オプションの WM_POINTER ベースのタッチ/スタイラス スタックに関する現在の既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0e430-104">Developers that do not explicitly enable this should see no change in WPF touch/stylus behavior.Current Known Issues With optional WM_POINTER based touch/stylus stack:</span></span>

- <span data-ttu-id="0e430-105">リアルタイム インクがサポートされない。</span><span class="sxs-lookup"><span data-stu-id="0e430-105">No support for real-time inking.</span></span>
- <span data-ttu-id="0e430-106">インクと StylusPlugins がまだ機能している間は、UI スレッドで処理されますが、パフォーマンスの低下につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e430-106">While inking and StylusPlugins will still work, they will be processed on the UI Thread which can lead to poor performance.</span></span>
- <span data-ttu-id="0e430-107">プロモーションの変更により、タッチ/スタイラス イベントからマウス イベントに動作が変更される。</span><span class="sxs-lookup"><span data-stu-id="0e430-107">Behavioral changes due to changes in promotion from touch/stylus events to mouse events</span></span>
- <span data-ttu-id="0e430-108">操作の動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e430-108">Manipulation may behave differently</span></span>
- <span data-ttu-id="0e430-109">ドラッグ/ドロップでは、タッチ入力の適切なフィードバックが表示されません。</span><span class="sxs-lookup"><span data-stu-id="0e430-109">Drag/Drop will not show appropriate feedback for touch input</span></span>
- <span data-ttu-id="0e430-110">これはスタイラス入力には影響しません。</span><span class="sxs-lookup"><span data-stu-id="0e430-110">This does not affect stylus input</span></span>
- <span data-ttu-id="0e430-111">ドラッグ/ドロップは、タッチ/スタイラス イベントで開始できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0e430-111">Drag/Drop can no longer be initiated on touch/stylus events</span></span>
- <span data-ttu-id="0e430-112">そのため、マウス入力が検出されるまで、アプリケーションがハングする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e430-112">This can potentially hang the application until mouse input is detected.</span></span>
- <span data-ttu-id="0e430-113">代わりに、開発者はマウス イベントからドラッグ アンド ドロップを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e430-113">Instead, developers should initiate drag and drop from mouse events.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0e430-114">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0e430-114">Suggestion</span></span>

<span data-ttu-id="0e430-115">このスタックを有効にする開発者は、アプリケーションの App.config ファイルに次の行を追加/マージできます。</span><span class="sxs-lookup"><span data-stu-id="0e430-115">Developers who wish to enable this stack can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="0e430-116">これを削除するか、値を false に設定すると、このオプションのスタックがオフになります。このスタックは Windows 10 Creators Update 以降でのみ使用できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0e430-116">Removing this or setting the value to false will turn this optional stack off.Note that this stack is available only on Windows 10 Creators Update and above.</span></span>

| <span data-ttu-id="0e430-117">名前</span><span class="sxs-lookup"><span data-stu-id="0e430-117">Name</span></span>    | <span data-ttu-id="0e430-118">値</span><span class="sxs-lookup"><span data-stu-id="0e430-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0e430-119">スコープ</span><span class="sxs-lookup"><span data-stu-id="0e430-119">Scope</span></span>   | <span data-ttu-id="0e430-120">エッジ</span><span class="sxs-lookup"><span data-stu-id="0e430-120">Edge</span></span>        |
| <span data-ttu-id="0e430-121">バージョン</span><span class="sxs-lookup"><span data-stu-id="0e430-121">Version</span></span> | <span data-ttu-id="0e430-122">4.7</span><span class="sxs-lookup"><span data-stu-id="0e430-122">4.7</span></span>         |
| <span data-ttu-id="0e430-123">種類</span><span class="sxs-lookup"><span data-stu-id="0e430-123">Type</span></span>    | <span data-ttu-id="0e430-124">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="0e430-124">Retargeting</span></span> |
