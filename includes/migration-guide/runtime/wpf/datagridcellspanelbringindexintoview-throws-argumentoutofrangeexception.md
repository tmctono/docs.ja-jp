---
ms.openlocfilehash: 1a1fc91ea2bb81e0f94b64323085ccf99072a1f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802496"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="8c64c-101">DataGridCellsPanel.BringIndexIntoView で ArgumentOutOfRangeException がスローされる</span><span class="sxs-lookup"><span data-stu-id="8c64c-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8c64c-102">説明</span><span class="sxs-lookup"><span data-stu-id="8c64c-102">Details</span></span>|<span data-ttu-id="8c64c-103">列の仮想化は有効になっているが、列の幅がまだ決定されていない場合、<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> は非同期で動作します。</span><span class="sxs-lookup"><span data-stu-id="8c64c-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="8c64c-104">非同期動作が発生する前に列が削除されると、<xref:System.ArgumentOutOfRangeException?displayProperty=name> が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c64c-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=name> can occur.</span></span>|
|<span data-ttu-id="8c64c-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8c64c-105">Suggestion</span></span>|<span data-ttu-id="8c64c-106">以下のいずれかを実行してください。</span><span class="sxs-lookup"><span data-stu-id="8c64c-106">Any one of the following:</span></span><ol><li><span data-ttu-id="8c64c-107">.NET Framework 4.7 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8c64c-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="8c64c-108">.NET Framework 4.6.2 の最新のサービス パッチをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c64c-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="8c64c-109"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> に対する非同期応答が完了するまでは列を削除しないようにする。</span><span class="sxs-lookup"><span data-stu-id="8c64c-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>|
|<span data-ttu-id="8c64c-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="8c64c-110">Scope</span></span>|<span data-ttu-id="8c64c-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="8c64c-111">Edge</span></span>|
|<span data-ttu-id="8c64c-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="8c64c-112">Version</span></span>|<span data-ttu-id="8c64c-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="8c64c-113">4.6.2</span></span>|
|<span data-ttu-id="8c64c-114">[種類]</span><span class="sxs-lookup"><span data-stu-id="8c64c-114">Type</span></span>|<span data-ttu-id="8c64c-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8c64c-115">Runtime</span></span>|
|<span data-ttu-id="8c64c-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8c64c-116">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
