---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643899"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="f0185-101">Switch.System.Windows.Forms.EnableVisualStyleValidation 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f0185-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="f0185-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換性スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0185-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f0185-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="f0185-103">Change description</span></span>

<span data-ttu-id="f0185-104">.NET Framework では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換スイッチによって、アプリケーションで、数値形式で指定された視覚スタイルの検証を無効にすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="f0185-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="f0185-105">.NET Core では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0185-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f0185-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f0185-106">Version introduced</span></span>

<span data-ttu-id="f0185-107">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="f0185-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f0185-108">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="f0185-108">Recommended action</span></span>

<span data-ttu-id="f0185-109">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="f0185-109">Remove the switch.</span></span> <span data-ttu-id="f0185-110">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="f0185-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f0185-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f0185-111">Category</span></span>

<span data-ttu-id="f0185-112">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="f0185-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f0185-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f0185-113">Affected APIs</span></span>

- <span data-ttu-id="f0185-114">なし</span><span class="sxs-lookup"><span data-stu-id="f0185-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
