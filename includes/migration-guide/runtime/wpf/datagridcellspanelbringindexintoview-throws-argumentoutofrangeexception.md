---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622370"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="5721e-101">DataGridCellsPanel.BringIndexIntoView で ArgumentOutOfRangeException がスローされる</span><span class="sxs-lookup"><span data-stu-id="5721e-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="5721e-102">説明</span><span class="sxs-lookup"><span data-stu-id="5721e-102">Details</span></span>

<span data-ttu-id="5721e-103">列の仮想化は有効になっているが、列の幅がまだ決定されていない場合、<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> は非同期で動作します。</span><span class="sxs-lookup"><span data-stu-id="5721e-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="5721e-104">非同期動作が発生する前に列が削除されると、<xref:System.ArgumentOutOfRangeException?displayProperty=fullName> が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5721e-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5721e-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5721e-105">Suggestion</span></span>

<span data-ttu-id="5721e-106">以下のいずれかを実行してください。</span><span class="sxs-lookup"><span data-stu-id="5721e-106">Any one of the following:</span></span><ol><li><span data-ttu-id="5721e-107">.NET Framework 4.7 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="5721e-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="5721e-108">.NET Framework 4.6.2 の最新のサービス パッチをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5721e-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="5721e-109"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> に対する非同期応答が完了するまでは列を削除しないようにする。</span><span class="sxs-lookup"><span data-stu-id="5721e-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="5721e-110">名前</span><span class="sxs-lookup"><span data-stu-id="5721e-110">Name</span></span>    | <span data-ttu-id="5721e-111">値</span><span class="sxs-lookup"><span data-stu-id="5721e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5721e-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="5721e-112">Scope</span></span>   |<span data-ttu-id="5721e-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="5721e-113">Edge</span></span>|
|<span data-ttu-id="5721e-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="5721e-114">Version</span></span>|<span data-ttu-id="5721e-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5721e-115">4.6.2</span></span>|
|<span data-ttu-id="5721e-116">種類</span><span class="sxs-lookup"><span data-stu-id="5721e-116">Type</span></span>|<span data-ttu-id="5721e-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5721e-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5721e-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5721e-118">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
