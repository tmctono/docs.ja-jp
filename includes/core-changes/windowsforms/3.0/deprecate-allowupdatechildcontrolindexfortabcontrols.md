---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937107"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="14863-101">AllowUpdateChildControlIndexForTabControls 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="14863-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="14863-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチは、.NET Framework 4.6 以降のバージョンの Windows フォームではサポートされていますが、.NET Core 3.0 以降の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="14863-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="14863-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="14863-103">Change description</span></span>

<span data-ttu-id="14863-104">.NET Framework 4.6 以降のバージョンでは、タブを選択すると、そのコントロール コレクションが並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="14863-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="14863-105">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 互換性スイッチを使用すると、この動作が望ましくない場合に、アプリケーションでこの並べ替えをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="14863-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="14863-106">.NET Core では、`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="14863-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="14863-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="14863-107">Version introduced</span></span>

<span data-ttu-id="14863-108">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="14863-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14863-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="14863-109">Recommended action</span></span>

<span data-ttu-id="14863-110">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="14863-110">Remove the switch.</span></span> <span data-ttu-id="14863-111">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="14863-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="14863-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="14863-112">Category</span></span>

<span data-ttu-id="14863-113">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="14863-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14863-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="14863-114">Affected APIs</span></span>

- <span data-ttu-id="14863-115">None</span><span class="sxs-lookup"><span data-stu-id="14863-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
