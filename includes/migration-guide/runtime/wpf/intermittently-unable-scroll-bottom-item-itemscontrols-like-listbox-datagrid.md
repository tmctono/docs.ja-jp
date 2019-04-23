---
ms.openlocfilehash: 9c2ee4ba66deb7c3b33698963add2b8a7e70069f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804411"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="d367f-101">カスタム DataTemplate を使用しているとき、断続的に、ItemsControl (ListBox や DataGrid など) 内の最後の項目までスクロールできない</span><span class="sxs-lookup"><span data-stu-id="d367f-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d367f-102">説明</span><span class="sxs-lookup"><span data-stu-id="d367f-102">Details</span></span>|<span data-ttu-id="d367f-103">場合によっては、.NET Framework 4.5 のバグにより、カスタム DataTemplate を使用していると、ItemsControl (<xref:System.Windows.Controls.ListBox?displayProperty=name>、<xref:System.Windows.Controls.ComboBox?displayProperty=name>、<xref:System.Windows.Controls.DataGrid?displayProperty=name> など) の最後の項目までスクロールできません。</span><span class="sxs-lookup"><span data-stu-id="d367f-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="d367f-104">(上へスクロールした後で) もう一度スクロールを試みると、今度はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="d367f-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>|
|<span data-ttu-id="d367f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d367f-105">Suggestion</span></span>|<span data-ttu-id="d367f-106">この問題は .NET Framework 4.5.2 で修正されたため、このバージョン (またはそれ以降のバージョン) の .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="d367f-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="d367f-107">または、ユーザーは、スクロール バーをこれらのコレクションの最後の項目までドラッグできますが、2 回試みなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d367f-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>|
|<span data-ttu-id="d367f-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="d367f-108">Scope</span></span>|<span data-ttu-id="d367f-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="d367f-109">Minor</span></span>|
|<span data-ttu-id="d367f-110">Version</span><span class="sxs-lookup"><span data-stu-id="d367f-110">Version</span></span>|<span data-ttu-id="d367f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="d367f-111">4.5</span></span>|
|<span data-ttu-id="d367f-112">型</span><span class="sxs-lookup"><span data-stu-id="d367f-112">Type</span></span>|<span data-ttu-id="d367f-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d367f-113">Runtime</span></span>|
