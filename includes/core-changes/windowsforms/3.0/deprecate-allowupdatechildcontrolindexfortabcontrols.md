---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556199"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="c0af9-101">AllowUpdateChildControlIndexForTabControls 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c0af9-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="c0af9-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチは、.NET Framework 4.6 以降のバージョンの Windows フォームではサポートされていますが、.NET Core または .NET 5.0 以降ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c0af9-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c0af9-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="c0af9-103">Change description</span></span>

<span data-ttu-id="c0af9-104">.NET Framework 4.6 以降のバージョンでは、タブを選択すると、そのコントロール コレクションが並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="c0af9-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="c0af9-105">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチを使用すると、この動作が望ましくない場合に、アプリケーションでこの並べ替えをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="c0af9-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="c0af9-106">.NET Core と .NET 5.0 以降では、`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c0af9-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c0af9-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c0af9-107">Version introduced</span></span>

<span data-ttu-id="c0af9-108">3.0</span><span class="sxs-lookup"><span data-stu-id="c0af9-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c0af9-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c0af9-109">Recommended action</span></span>

<span data-ttu-id="c0af9-110">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0af9-110">Remove the switch.</span></span> <span data-ttu-id="c0af9-111">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="c0af9-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="c0af9-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c0af9-112">Category</span></span>

<span data-ttu-id="c0af9-113">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="c0af9-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0af9-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c0af9-114">Affected APIs</span></span>

- <span data-ttu-id="c0af9-115">なし</span><span class="sxs-lookup"><span data-stu-id="c0af9-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
