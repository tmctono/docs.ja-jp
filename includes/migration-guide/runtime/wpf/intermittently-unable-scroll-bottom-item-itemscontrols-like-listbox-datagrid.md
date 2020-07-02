---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622022"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="8dfba-101">カスタム DataTemplate を使用しているとき、断続的に、ItemsControl (ListBox や DataGrid など) 内の最後の項目までスクロールできない</span><span class="sxs-lookup"><span data-stu-id="8dfba-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="8dfba-102">説明</span><span class="sxs-lookup"><span data-stu-id="8dfba-102">Details</span></span>

<span data-ttu-id="8dfba-103">場合によっては、.NET Framework 4.5 のバグにより、カスタム DataTemplate を使用していると、ItemsControl (<xref:System.Windows.Controls.ListBox?displayProperty=fullName>、<xref:System.Windows.Controls.ComboBox?displayProperty=fullName>、<xref:System.Windows.Controls.DataGrid?displayProperty=fullName> など) の最後の項目までスクロールできません。</span><span class="sxs-lookup"><span data-stu-id="8dfba-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="8dfba-104">(上へスクロールした後で) もう一度スクロールを試みると、今度はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="8dfba-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8dfba-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8dfba-105">Suggestion</span></span>

<span data-ttu-id="8dfba-106">この問題は .NET Framework 4.5.2 で修正されたため、このバージョン (またはそれ以降のバージョン) の .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="8dfba-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="8dfba-107">または、ユーザーは、スクロール バーをこれらのコレクションの最後の項目までドラッグできますが、2 回試みなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8dfba-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="8dfba-108">名前</span><span class="sxs-lookup"><span data-stu-id="8dfba-108">Name</span></span>    | <span data-ttu-id="8dfba-109">[値]</span><span class="sxs-lookup"><span data-stu-id="8dfba-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8dfba-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="8dfba-110">Scope</span></span>   |<span data-ttu-id="8dfba-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="8dfba-111">Minor</span></span>|
|<span data-ttu-id="8dfba-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="8dfba-112">Version</span></span>|<span data-ttu-id="8dfba-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8dfba-113">4.5</span></span>|
|<span data-ttu-id="8dfba-114">種類</span><span class="sxs-lookup"><span data-stu-id="8dfba-114">Type</span></span>|<span data-ttu-id="8dfba-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8dfba-115">Runtime</span></span>|
