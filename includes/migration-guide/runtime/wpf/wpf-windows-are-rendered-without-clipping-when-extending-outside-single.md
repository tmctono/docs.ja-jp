---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858649"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="4d088-101">1 つのモニターの外部に拡張すると、クリッピングなしで WPF ウィンドウがレンダリングされる</span><span class="sxs-lookup"><span data-stu-id="4d088-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4d088-102">説明</span><span class="sxs-lookup"><span data-stu-id="4d088-102">Details</span></span>|<span data-ttu-id="4d088-103">Windows 8 以上で実行している .NET Framework 4.6 では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="4d088-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="4d088-104">これは、1 つのディスプレイを超える WPF ウィンドウをクリッピングする、以前のバージョンの .NET Framework とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4d088-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="4d088-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4d088-105">Suggestion</span></span>|<span data-ttu-id="4d088-106">この動作 (クリッピングするかどうか) は、アプリケーションの構成ファイルの <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> で <code>&lt;appSettings&gt;</code> 要素を使用するか、アプリの起動時に <code>EnableMultiMonitorDisplayClipping</code> プロパティを設定することで明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="4d088-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="4d088-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4d088-107">Scope</span></span>|<span data-ttu-id="4d088-108">Minor</span><span class="sxs-lookup"><span data-stu-id="4d088-108">Minor</span></span>|
|<span data-ttu-id="4d088-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="4d088-109">Version</span></span>|<span data-ttu-id="4d088-110">4.6</span><span class="sxs-lookup"><span data-stu-id="4d088-110">4.6</span></span>|
|<span data-ttu-id="4d088-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="4d088-111">Type</span></span>|<span data-ttu-id="4d088-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4d088-112">Runtime</span></span>|
