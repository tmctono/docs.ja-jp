---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643905"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="b3ca1-101">Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="b3ca1-101">Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="b3ca1-102">.NET Framework 4.7.2 で導入された `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b3ca1-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="b3ca1-103">Change description</span></span>

<span data-ttu-id="b3ca1-104">.NET Framework 4.7.2 以降、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換性スイッチを使用すると、開発者は <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> プロパティの新しい動作を無効にできます。これにより、ソース管理への参照が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="b3ca1-105">プロパティの以前の動作では、`null` が返されました。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="b3ca1-106">詳細については、「[\<AppContextSwitchOverrides> 要素](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="b3ca1-107">.NET Core では、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3ca1-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b3ca1-108">Version introduced</span></span>

<span data-ttu-id="b3ca1-109">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="b3ca1-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3ca1-110">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="b3ca1-110">Recommended action</span></span>

<span data-ttu-id="b3ca1-111">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-111">Remove the switch.</span></span> <span data-ttu-id="b3ca1-112">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="b3ca1-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="b3ca1-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b3ca1-113">Category</span></span>

<span data-ttu-id="b3ca1-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="b3ca1-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3ca1-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b3ca1-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
