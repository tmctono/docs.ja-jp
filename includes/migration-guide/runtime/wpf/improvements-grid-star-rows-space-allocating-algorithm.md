---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237617"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="75496-101">グリッド スター行領域の割り当てアルゴリズムの改善</span><span class="sxs-lookup"><span data-stu-id="75496-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="75496-102">説明</span><span class="sxs-lookup"><span data-stu-id="75496-102">Details</span></span>|<span data-ttu-id="75496-103">.NET Framework 4.7 で導入された <xref:System.Windows.Controls.Grid> で[サイズを割り当てるためのアルゴリズム](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) のバグを修正しました。</span><span class="sxs-lookup"><span data-stu-id="75496-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="75496-104">空の行を含む <code>Height=&quot;Auto&quot;</code> のグリッドなど、場合によっては、行が正しくない位置に配置され、すべてグリッドの外側に示されることがありました。</span><span class="sxs-lookup"><span data-stu-id="75496-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="75496-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="75496-105">Suggestion</span></span>|<span data-ttu-id="75496-106">アプリケーションでこれらの変更を利用するには、.NET Framework 4.8 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75496-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="75496-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="75496-107">Scope</span></span>|<span data-ttu-id="75496-108">Major</span><span class="sxs-lookup"><span data-stu-id="75496-108">Major</span></span>|
|<span data-ttu-id="75496-109">Version</span><span class="sxs-lookup"><span data-stu-id="75496-109">Version</span></span>|<span data-ttu-id="75496-110">4.8</span><span class="sxs-lookup"><span data-stu-id="75496-110">4.8</span></span>|
|<span data-ttu-id="75496-111">型</span><span class="sxs-lookup"><span data-stu-id="75496-111">Type</span></span>|<span data-ttu-id="75496-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="75496-112">Runtime</span></span>|
