---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496994"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="ffdc0-101">1 つのモニターの外部に拡張すると、クリッピングなしで WPF ウィンドウがレンダリングされる</span><span class="sxs-lookup"><span data-stu-id="ffdc0-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="ffdc0-102">説明</span><span class="sxs-lookup"><span data-stu-id="ffdc0-102">Details</span></span>

<span data-ttu-id="ffdc0-103">Windows 8 以上で実行している .NET Framework 4.6 では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="ffdc0-104">これは、1 つのディスプレイを超える WPF ウィンドウをクリッピングする、以前のバージョンの .NET Framework とは異なります。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ffdc0-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ffdc0-105">Suggestion</span></span>

<span data-ttu-id="ffdc0-106">この動作 (クリッピングするかどうか) は、アプリケーションの構成ファイルの <code>&lt;appSettings&gt;</code> で <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> 要素を使用するか、アプリの起動時に <code>EnableMultiMonitorDisplayClipping</code> プロパティを設定することで明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="ffdc0-107">名前</span><span class="sxs-lookup"><span data-stu-id="ffdc0-107">Name</span></span>    | <span data-ttu-id="ffdc0-108">値</span><span class="sxs-lookup"><span data-stu-id="ffdc0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ffdc0-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="ffdc0-109">Scope</span></span>   |<span data-ttu-id="ffdc0-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="ffdc0-110">Minor</span></span>|
|<span data-ttu-id="ffdc0-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="ffdc0-111">Version</span></span>|<span data-ttu-id="ffdc0-112">4.6</span><span class="sxs-lookup"><span data-stu-id="ffdc0-112">4.6</span></span>|
|<span data-ttu-id="ffdc0-113">種類</span><span class="sxs-lookup"><span data-stu-id="ffdc0-113">Type</span></span>|<span data-ttu-id="ffdc0-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ffdc0-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ffdc0-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ffdc0-115">Affected APIs</span></span>

<span data-ttu-id="ffdc0-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
