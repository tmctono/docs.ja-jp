---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937067"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="52011-101">DomainUpDown.UseLegacyScrolling 互換性スイッチはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="52011-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="52011-102">.NET Framework 4.7.1 で導入された `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 互換スイッチは、.NET Core 3.0 上の Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="52011-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="52011-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="52011-103">Change description</span></span>

<span data-ttu-id="52011-104">.NET Framework 4.7.1 以降では、`Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 互換スイッチを使用して、開発者が独立した <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> および <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> アクションをオプトアウトできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52011-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="52011-105">このスイッチによって、コンテキスト テキストが存在する場合は <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> が無視されるという従来の動作が復元されました。開発者は、コントロールに対して <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> アクションの前に <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> アクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52011-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="52011-106">詳細については、「[\<AppContextSwitchOverrides> 要素](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52011-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="52011-107">.NET Core では、`Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` スイッチはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="52011-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="52011-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="52011-108">Version introduced</span></span>

<span data-ttu-id="52011-109">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="52011-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="52011-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="52011-110">Recommended action</span></span>

<span data-ttu-id="52011-111">スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="52011-111">Remove the switch.</span></span> <span data-ttu-id="52011-112">そのスイッチはサポートされておらず、代替機能はありません。</span><span class="sxs-lookup"><span data-stu-id="52011-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="52011-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="52011-113">Category</span></span>

<span data-ttu-id="52011-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="52011-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="52011-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="52011-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
