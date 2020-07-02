---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621356"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="2760e-101">1 つのモニターの外部に拡張すると、クリッピングなしで WPF ウィンドウがレンダリングされる</span><span class="sxs-lookup"><span data-stu-id="2760e-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="2760e-102">説明</span><span class="sxs-lookup"><span data-stu-id="2760e-102">Details</span></span>

<span data-ttu-id="2760e-103">Windows 8 以上で実行している .NET Framework 4.6 では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="2760e-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="2760e-104">これは、1 つのディスプレイを超える WPF ウィンドウをクリッピングする、以前のバージョンの .NET Framework とは異なります。</span><span class="sxs-lookup"><span data-stu-id="2760e-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2760e-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2760e-105">Suggestion</span></span>

<span data-ttu-id="2760e-106">この動作 (クリッピングするかどうか) は、アプリケーションの構成ファイルの <code>&lt;appSettings&gt;</code> で <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> 要素を使用するか、アプリの起動時に <code>EnableMultiMonitorDisplayClipping</code> プロパティを設定することで明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="2760e-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="2760e-107">名前</span><span class="sxs-lookup"><span data-stu-id="2760e-107">Name</span></span>    | <span data-ttu-id="2760e-108">値</span><span class="sxs-lookup"><span data-stu-id="2760e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2760e-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="2760e-109">Scope</span></span>   |<span data-ttu-id="2760e-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="2760e-110">Minor</span></span>|
|<span data-ttu-id="2760e-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="2760e-111">Version</span></span>|<span data-ttu-id="2760e-112">4.6</span><span class="sxs-lookup"><span data-stu-id="2760e-112">4.6</span></span>|
|<span data-ttu-id="2760e-113">種類</span><span class="sxs-lookup"><span data-stu-id="2760e-113">Type</span></span>|<span data-ttu-id="2760e-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2760e-114">Runtime</span></span>|
