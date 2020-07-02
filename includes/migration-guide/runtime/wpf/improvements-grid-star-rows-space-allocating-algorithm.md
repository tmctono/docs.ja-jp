---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621993"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="df315-101">グリッド スター行領域の割り当てアルゴリズムの改善</span><span class="sxs-lookup"><span data-stu-id="df315-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="df315-102">説明</span><span class="sxs-lookup"><span data-stu-id="df315-102">Details</span></span>

<span data-ttu-id="df315-103">.NET Framework 4.7 で導入された <xref:System.Windows.Controls.Grid> で[サイズを割り当てるためのアルゴリズム](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) のバグを修正しました。</span><span class="sxs-lookup"><span data-stu-id="df315-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="df315-104">空の行を含む <code>Height=&quot;Auto&quot;</code> のグリッドなど、場合によっては、行が正しくない位置に配置され、すべてグリッドの外側に示されることがありました。</span><span class="sxs-lookup"><span data-stu-id="df315-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df315-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="df315-105">Suggestion</span></span>

<span data-ttu-id="df315-106">アプリケーションでこれらの変更を利用するには、.NET Framework 4.8 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df315-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="df315-107">名前</span><span class="sxs-lookup"><span data-stu-id="df315-107">Name</span></span>    | <span data-ttu-id="df315-108">[値]</span><span class="sxs-lookup"><span data-stu-id="df315-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df315-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="df315-109">Scope</span></span>   |<span data-ttu-id="df315-110">Major</span><span class="sxs-lookup"><span data-stu-id="df315-110">Major</span></span>|
|<span data-ttu-id="df315-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="df315-111">Version</span></span>|<span data-ttu-id="df315-112">4.8</span><span class="sxs-lookup"><span data-stu-id="df315-112">4.8</span></span>|
|<span data-ttu-id="df315-113">種類</span><span class="sxs-lookup"><span data-stu-id="df315-113">Type</span></span>|<span data-ttu-id="df315-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="df315-114">Runtime</span></span>|
