---
ms.openlocfilehash: 6d804dd335cb18d5febc2ca5f794af92963bece1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620493"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a><span data-ttu-id="fb92d-101">WPF DataGrid 行ヘッダーを右クリックすると、DataGrid の選択が変更される</span><span class="sxs-lookup"><span data-stu-id="fb92d-101">Right clicking on a WPF DataGrid row header changes the DataGrid selection</span></span>

#### <a name="details"></a><span data-ttu-id="fb92d-102">説明</span><span class="sxs-lookup"><span data-stu-id="fb92d-102">Details</span></span>

<span data-ttu-id="fb92d-103">複数行が選択されている状態で、選択した <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> 行ヘッダーを右クリックすると、その行のみで <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> の選択が変更されます。</span><span class="sxs-lookup"><span data-stu-id="fb92d-103">Right-clicking a selected <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> row header while multiple rows are selected results in the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s selection changing to only that row.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fb92d-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fb92d-104">Suggestion</span></span>

<span data-ttu-id="fb92d-105">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="fb92d-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="fb92d-106">名前</span><span class="sxs-lookup"><span data-stu-id="fb92d-106">Name</span></span>    | <span data-ttu-id="fb92d-107">[値]</span><span class="sxs-lookup"><span data-stu-id="fb92d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fb92d-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="fb92d-108">Scope</span></span>   |<span data-ttu-id="fb92d-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="fb92d-109">Edge</span></span>|
|<span data-ttu-id="fb92d-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="fb92d-110">Version</span></span>|<span data-ttu-id="fb92d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fb92d-111">4.5</span></span>|
|<span data-ttu-id="fb92d-112">種類</span><span class="sxs-lookup"><span data-stu-id="fb92d-112">Type</span></span>|<span data-ttu-id="fb92d-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fb92d-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fb92d-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fb92d-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.%23ctor></li></ul>|
