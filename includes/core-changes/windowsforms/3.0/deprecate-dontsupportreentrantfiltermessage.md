---
ms.openlocfilehash: 3272dc562981269b868df4ca9d3a5806918aba5f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937013"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="dee62-101">DontSupportReentrantFilterMessage 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="dee62-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="dee62-102">.NET Framework 4.6.1 で導入された `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dee62-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dee62-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="dee62-103">Change description</span></span>

<span data-ttu-id="dee62-104">.NET Framework 4.6.1 以降、`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 互換性スイッチでは、カスタムの <xref:System.IndexOutOfRangeException> 実装で <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> メッセージが呼び出されたときに発生する可能性がある <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 例外に対処します。</span><span class="sxs-lookup"><span data-stu-id="dee62-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="dee62-105">詳細については、[「軽減策: カスタムの IMessageFilter.PreFilterMessage 実装」](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee62-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="dee62-106">.NET Core では、`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dee62-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dee62-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dee62-107">Version introduced</span></span>

<span data-ttu-id="dee62-108">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="dee62-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dee62-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="dee62-109">Recommended action</span></span>

<span data-ttu-id="dee62-110">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="dee62-110">Remove the switch.</span></span> <span data-ttu-id="dee62-111">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="dee62-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="dee62-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dee62-112">Category</span></span>

<span data-ttu-id="dee62-113">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="dee62-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dee62-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dee62-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
