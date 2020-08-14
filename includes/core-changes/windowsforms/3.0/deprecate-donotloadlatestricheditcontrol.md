---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556198"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="5cd91-101">DoNotLoadLatestRichEditControl 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="5cd91-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="5cd91-102">.NET Framework 4.7.1 で導入された `Switch.System.Windows.Forms.UseLegacyImages` 互換性スイッチは、.NET Core または .NET 5.0 以降上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5cd91-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5cd91-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="5cd91-103">Change description</span></span>

<span data-ttu-id="5cd91-104">.NET Framework 4.6.2 とそれ以前のバージョンでは、<xref:System.Windows.Forms.RichTextBox> コントロールによって Win32 RichEdit コントロール v3.0 がインスタンス化され、.NET Framework 4.7.1 をターゲットとするアプリケーションの場合、<xref:System.Windows.Forms.RichTextBox> コントロールによって RichEdit v4.1 (*msftedit.dll*) がインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="5cd91-104">In .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control instantiates the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control instantiates RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="5cd91-105">`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 互換性スイッチは、.NET Framework 4.7.1 以降のバージョンをターゲットとするアプリケーションが新しい RichEdit v4.1 コントロールをオプトアウトし、代わりに古い RichEdit v3 コントロールを使用できるようにするために導入されました。</span><span class="sxs-lookup"><span data-stu-id="5cd91-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="5cd91-106">.NET Core と .NET 5.0 以降のバージョンでは、`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5cd91-106">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="5cd91-107"><xref:System.Windows.Forms.RichTextBox> コントロールの新しいバージョンのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5cd91-107">Only new versions of the <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5cd91-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="5cd91-108">Version introduced</span></span>

<span data-ttu-id="5cd91-109">3.0</span><span class="sxs-lookup"><span data-stu-id="5cd91-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5cd91-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="5cd91-110">Recommended action</span></span>

<span data-ttu-id="5cd91-111">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="5cd91-111">Remove the switch.</span></span> <span data-ttu-id="5cd91-112">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="5cd91-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="5cd91-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="5cd91-113">Category</span></span>

<span data-ttu-id="5cd91-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="5cd91-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5cd91-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5cd91-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
