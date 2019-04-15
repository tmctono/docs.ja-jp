---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234687"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="d0a12-101">WPF TextBox.Text とデータ バインドを非同期にできる</span><span class="sxs-lookup"><span data-stu-id="d0a12-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d0a12-102">説明</span><span class="sxs-lookup"><span data-stu-id="d0a12-102">Details</span></span>|<span data-ttu-id="d0a12-103">場合によっては、データ バインディングの書き込み操作中にプロパティが変更された場合、<xref:System.Windows.Controls.TextBox.Text> プロパティにデータ バインディング プロパティ値の以前の値が反映されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0a12-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="d0a12-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d0a12-104">Suggestion</span></span>|<span data-ttu-id="d0a12-105">これによって生じる悪影響はないはずです。</span><span class="sxs-lookup"><span data-stu-id="d0a12-105">This should have no negative impact.</span></span> <span data-ttu-id="d0a12-106">ただし、<xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> プロパティを <code>false</code> に設定して、以前の動作を復元することは可能です。</span><span class="sxs-lookup"><span data-stu-id="d0a12-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="d0a12-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="d0a12-107">Scope</span></span>|<span data-ttu-id="d0a12-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="d0a12-108">Edge</span></span>|
|<span data-ttu-id="d0a12-109">Version</span><span class="sxs-lookup"><span data-stu-id="d0a12-109">Version</span></span>|<span data-ttu-id="d0a12-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d0a12-110">4.5</span></span>|
|<span data-ttu-id="d0a12-111">型</span><span class="sxs-lookup"><span data-stu-id="d0a12-111">Type</span></span>|<span data-ttu-id="d0a12-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d0a12-112">Retargeting</span></span>|
|<span data-ttu-id="d0a12-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d0a12-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
