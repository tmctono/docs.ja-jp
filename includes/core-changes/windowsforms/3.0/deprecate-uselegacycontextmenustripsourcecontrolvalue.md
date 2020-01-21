---
ms.openlocfilehash: 5aca2b8b3ca6572194692888eae3c5614245b481
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937039"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="eddb3-101">UseLegacyContextMenuStripSourceControlValue 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="eddb3-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="eddb3-102">.NET Framework 4.7.2 で導入された `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eddb3-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eddb3-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="eddb3-103">Change description</span></span>

<span data-ttu-id="eddb3-104">.NET Framework 4.7.2 以降、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 互換性スイッチを使用すると、開発者は <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> プロパティの新しい動作を無効にできます。これにより、ソース管理への参照が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eddb3-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="eddb3-105">プロパティの以前の動作では、`null` が返されました。</span><span class="sxs-lookup"><span data-stu-id="eddb3-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="eddb3-106">詳細については、「[\<AppContextSwitchOverrides> 要素](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eddb3-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="eddb3-107">.NET Core では、`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eddb3-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eddb3-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="eddb3-108">Version introduced</span></span>

<span data-ttu-id="eddb3-109">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="eddb3-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eddb3-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="eddb3-110">Recommended action</span></span>

<span data-ttu-id="eddb3-111">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="eddb3-111">Remove the switch.</span></span> <span data-ttu-id="eddb3-112">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="eddb3-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="eddb3-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="eddb3-113">Category</span></span>

<span data-ttu-id="eddb3-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="eddb3-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eddb3-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="eddb3-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
