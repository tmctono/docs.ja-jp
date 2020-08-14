---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556196"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="db22d-101">EnableVisualStyleValidation 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="db22d-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="db22d-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換性スイッチは、.NET Core または .NET 5.0 以降上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db22d-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="db22d-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="db22d-103">Change description</span></span>

<span data-ttu-id="db22d-104">.NET Framework では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` 互換スイッチによって、アプリケーションで、数値形式で指定された視覚スタイルの検証を無効にすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="db22d-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="db22d-105">.NET Core と .NET 5.0 以降では、`Switch.System.Windows.Forms.EnableVisualStyleValidation` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db22d-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="db22d-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="db22d-106">Version introduced</span></span>

<span data-ttu-id="db22d-107">3.0</span><span class="sxs-lookup"><span data-stu-id="db22d-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="db22d-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="db22d-108">Recommended action</span></span>

<span data-ttu-id="db22d-109">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="db22d-109">Remove the switch.</span></span> <span data-ttu-id="db22d-110">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="db22d-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="db22d-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="db22d-111">Category</span></span>

<span data-ttu-id="db22d-112">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="db22d-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="db22d-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="db22d-113">Affected APIs</span></span>

- <span data-ttu-id="db22d-114">なし</span><span class="sxs-lookup"><span data-stu-id="db22d-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
