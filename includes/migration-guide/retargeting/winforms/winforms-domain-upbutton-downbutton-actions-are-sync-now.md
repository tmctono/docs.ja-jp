---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606670"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="17bb4-101">WinForm の Domain upbutton アクションと downbutton アクションが同期するようになった</span><span class="sxs-lookup"><span data-stu-id="17bb4-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="17bb4-102">説明</span><span class="sxs-lookup"><span data-stu-id="17bb4-102">Details</span></span>

<span data-ttu-id="17bb4-103">.NET Framework 4.7.1 およびそれより前のバージョンでは、コントロールにテキストが存在すると <xref:System.Windows.Forms.DomainUpDown> コントロールの <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> アクションが無視され、開発者は <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> アクションを使用する前にコントロールで <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> アクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb4-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="17bb4-104">.NET Framework 4.7.2 以降では、このシナリオで <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> アクションと <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> アクションの両方が独立して動作し、同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="17bb4-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="17bb4-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="17bb4-105">Suggestion</span></span>

<span data-ttu-id="17bb4-106">アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.2 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb4-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="17bb4-107">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="17bb4-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="17bb4-108">.NET Framework 4.7.2 を対象にして再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="17bb4-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="17bb4-109">.NET Framework 4.7.2 以降を対象とする Windows フォーム アプリケーションでは、この変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="17bb4-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="17bb4-110">下の例のように、app.config ファイルの `<runtime>` セクションに次の [AppContext スイッチ](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を追加し、それを `false` に設定することで、以前のスクロール動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="17bb4-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="17bb4-111">名前</span><span class="sxs-lookup"><span data-stu-id="17bb4-111">Name</span></span>    | <span data-ttu-id="17bb4-112">[値]</span><span class="sxs-lookup"><span data-stu-id="17bb4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="17bb4-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="17bb4-113">Scope</span></span>   | <span data-ttu-id="17bb4-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="17bb4-114">Edge</span></span>        |
| <span data-ttu-id="17bb4-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="17bb4-115">Version</span></span> | <span data-ttu-id="17bb4-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="17bb4-116">4.7.2</span></span>       |
| <span data-ttu-id="17bb4-117">種類</span><span class="sxs-lookup"><span data-stu-id="17bb4-117">Type</span></span>    | <span data-ttu-id="17bb4-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="17bb4-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="17bb4-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="17bb4-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
