---
ms.openlocfilehash: 3fb8807a9b6f0bb0d2bc746f5e89eaa8a81d6aa8
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556203"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="e3e91-101">DoNotSupportSelectAllShortcutInMultilineTextBox 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="e3e91-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="e3e91-102">.NET Framework 4.6.1 で導入された `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 互換性スイッチは、.NET Core と .NET 5.0 以降上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e3e91-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core and .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e3e91-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="e3e91-103">Change description</span></span>

<span data-ttu-id="e3e91-104">.NET Framework 4.6.1 以降、<xref:System.Windows.Forms.TextBox> コントロールで <kbd>Ctrl</kbd> + <kbd>A</kbd> ショートカット キーを押すと、すべてのテキストが選択されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3e91-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="e3e91-105">.NET Framework 4.6 およびそれ以前のバージョンでは、[Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) および <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> プロパティが `true` に選択されていた場合、<kbd>Ctrl</kbd> + <kbd>A</kbd> ショートカット キーを選択してもすべてのテキストが選択されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e3e91-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="e3e91-106">`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 互換性スイッチは、元の動作を保持するために .NET Framework 4.6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3e91-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="e3e91-107">詳細については、「<xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e91-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e3e91-108">.NET Core と .NET 5.0 以降のバージョンでは、`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e3e91-108">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e3e91-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e3e91-109">Version introduced</span></span>

<span data-ttu-id="e3e91-110">3.0</span><span class="sxs-lookup"><span data-stu-id="e3e91-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e3e91-111">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e3e91-111">Recommended action</span></span>

<span data-ttu-id="e3e91-112">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="e3e91-112">Remove the switch.</span></span> <span data-ttu-id="e3e91-113">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="e3e91-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e3e91-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e3e91-114">Category</span></span>

<span data-ttu-id="e3e91-115">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="e3e91-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e3e91-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e3e91-116">Affected APIs</span></span>

- <span data-ttu-id="e3e91-117">None</span><span class="sxs-lookup"><span data-stu-id="e3e91-117">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
