---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643893"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="52b66-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="52b66-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="52b66-102">.NET Framework 4.6.1 で導入された `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="52b66-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="52b66-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="52b66-103">Change description</span></span>

<span data-ttu-id="52b66-104">.NET Framework 4.6.1 以降、`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 互換性スイッチでは、カスタムの <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 実装で <xref:System.IndexOutOfRangeException> メッセージが呼び出されたときに発生する可能性がある <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 例外に対処します。</span><span class="sxs-lookup"><span data-stu-id="52b66-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="52b66-105">詳細については、「[軽減策:カスタムの IMessageFilter.PreFilterMessage 実装](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52b66-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="52b66-106">.NET Core では、`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="52b66-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="52b66-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="52b66-107">Version introduced</span></span>

<span data-ttu-id="52b66-108">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="52b66-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="52b66-109">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="52b66-109">Recommended action</span></span>

<span data-ttu-id="52b66-110">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="52b66-110">Remove the switch.</span></span> <span data-ttu-id="52b66-111">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="52b66-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="52b66-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="52b66-112">Category</span></span>

<span data-ttu-id="52b66-113">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="52b66-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="52b66-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="52b66-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
