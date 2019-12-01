---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643875"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="ce2f2-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ce2f2-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="ce2f2-102">.NET Framework 4.7.1 で導入された `Switch.System.Windows.Forms.UseLegacyImages` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ce2f2-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="ce2f2-103">Change description</span></span>

<span data-ttu-id="ce2f2-104">.NET Framework 4.6.2 とそれ以前のバージョンでは、<xref:System.Windows.Forms.RichTextBox> コントロールによって Win32 RichEdit コントロール v3.0 がインスタンス化され、.NET Framework 4.7.1 をターゲットとするアプリケーションの場合、<xref:System.Windows.Forms.RichTextBox> コントロールによって RichEdit v4.1 (*msftedit.dll*) がインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="ce2f2-105">`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 互換性スイッチは、.NET Framework 4.7.1 以降のバージョンをターゲットとするアプリケーションが新しい RichEdit v4.1 コントロールをオプトアウトし、代わりに古い RichEdit v3 コントロールを使用できるようにするために導入されました。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="ce2f2-106">.NET Core では、`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="ce2f2-107"><xref:System.Windows.Forms.RichTextBox> コントロールの新しいバージョンのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ce2f2-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ce2f2-108">Version introduced</span></span>

<span data-ttu-id="ce2f2-109">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="ce2f2-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ce2f2-110">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="ce2f2-110">Recommended action</span></span>

<span data-ttu-id="ce2f2-111">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-111">Remove the switch.</span></span> <span data-ttu-id="ce2f2-112">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="ce2f2-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ce2f2-113">Category</span></span>

<span data-ttu-id="ce2f2-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="ce2f2-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ce2f2-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ce2f2-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
