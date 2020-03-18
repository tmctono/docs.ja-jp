---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937100"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="d764b-101">EnableVisualStyleValidation 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d764b-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="d764b-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換性スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d764b-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d764b-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="d764b-103">Change description</span></span>

<span data-ttu-id="d764b-104">.NET Framework では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換スイッチによって、アプリケーションで、数値形式で指定された視覚スタイルの検証を無効にすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="d764b-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="d764b-105">.NET Core では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d764b-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d764b-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d764b-106">Version introduced</span></span>

<span data-ttu-id="d764b-107">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="d764b-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d764b-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="d764b-108">Recommended action</span></span>

<span data-ttu-id="d764b-109">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="d764b-109">Remove the switch.</span></span> <span data-ttu-id="d764b-110">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="d764b-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d764b-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d764b-111">Category</span></span>

<span data-ttu-id="d764b-112">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="d764b-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d764b-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d764b-113">Affected APIs</span></span>

- <span data-ttu-id="d764b-114">なし</span><span class="sxs-lookup"><span data-stu-id="d764b-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
