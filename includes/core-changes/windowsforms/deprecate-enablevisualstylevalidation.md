---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181762"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="41ceb-101">Switch.System.Windows.Forms.EnableVisualStyleValidation 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="41ceb-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="41ceb-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換性スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41ceb-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="41ceb-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="41ceb-103">Change description</span></span>

<span data-ttu-id="41ceb-104">.NET Framework では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換スイッチによって、アプリケーションで、数値形式で指定された視覚スタイルの検証を無効にすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="41ceb-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span> 

<span data-ttu-id="41ceb-105">.NET Core では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41ceb-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41ceb-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="41ceb-106">Version introduced</span></span>

<span data-ttu-id="41ceb-107">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="41ceb-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41ceb-108">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="41ceb-108">Recommended action</span></span>

<span data-ttu-id="41ceb-109">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="41ceb-109">Remove the switch.</span></span> <span data-ttu-id="41ceb-110">スイッチはサポートされておらず、代替機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="41ceb-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="41ceb-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="41ceb-111">Category</span></span>

<span data-ttu-id="41ceb-112">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="41ceb-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41ceb-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="41ceb-113">Affected APIs</span></span>

- <span data-ttu-id="41ceb-114">なし</span><span class="sxs-lookup"><span data-stu-id="41ceb-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
