---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617232"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="d7689-101">WPF TextBox.Text とデータ バインドを非同期にできる</span><span class="sxs-lookup"><span data-stu-id="d7689-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

#### <a name="details"></a><span data-ttu-id="d7689-102">説明</span><span class="sxs-lookup"><span data-stu-id="d7689-102">Details</span></span>

<span data-ttu-id="d7689-103">場合によっては、データ バインディングの書き込み操作中にプロパティが変更された場合、<xref:System.Windows.Controls.TextBox.Text> プロパティにデータ バインディング プロパティ値の以前の値が反映されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d7689-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7689-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d7689-104">Suggestion</span></span>

<span data-ttu-id="d7689-105">これによって生じる悪影響はないはずです。</span><span class="sxs-lookup"><span data-stu-id="d7689-105">This should have no negative impact.</span></span> <span data-ttu-id="d7689-106">ただし、<xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> プロパティを `false` に設定して、以前の動作を復元することは可能です。</span><span class="sxs-lookup"><span data-stu-id="d7689-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to `false`.</span></span>

| <span data-ttu-id="d7689-107">名前</span><span class="sxs-lookup"><span data-stu-id="d7689-107">Name</span></span>    | <span data-ttu-id="d7689-108">[値]</span><span class="sxs-lookup"><span data-stu-id="d7689-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7689-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d7689-109">Scope</span></span>   | <span data-ttu-id="d7689-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="d7689-110">Edge</span></span>        |
| <span data-ttu-id="d7689-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="d7689-111">Version</span></span> | <span data-ttu-id="d7689-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d7689-112">4.5</span></span>         |
|<span data-ttu-id="d7689-113">種類</span><span class="sxs-lookup"><span data-stu-id="d7689-113">Type</span></span>|<span data-ttu-id="d7689-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d7689-114">Retargeting</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7689-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d7689-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
