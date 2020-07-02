---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614708"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a><span data-ttu-id="f9537-101">Application.FilterMessage は、IMessageFilter.PreFilterMessage の再入可能な実装についてスローしなくなりました</span><span class="sxs-lookup"><span data-stu-id="f9537-101">Application.FilterMessage no longer throws for re-entrant implementations of IMessageFilter.PreFilterMessage</span></span>

#### <a name="details"></a><span data-ttu-id="f9537-102">説明</span><span class="sxs-lookup"><span data-stu-id="f9537-102">Details</span></span>

<span data-ttu-id="f9537-103">.NET Framework 4.6.1 以前は、<xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> または <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (さらに <xref:System.Windows.Forms.Application.DoEvents>) を呼び出す<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> で <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> を呼び出すと、<xref:System.IndexOutOfRangeException?displayProperty=fullName> が発生していました。</span><span class="sxs-lookup"><span data-stu-id="f9537-103">Prior to the .NET Framework 4.6.1, calling <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> with an <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> which called <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> or <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (while also calling <xref:System.Windows.Forms.Application.DoEvents>) would cause an <xref:System.IndexOutOfRangeException?displayProperty=fullName>.</span></span><p/><span data-ttu-id="f9537-104">.NET Framework 4.6.1 以降を対象とするアプリケーションでは、この例外がスローされなくなり、上述の再入可能フィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9537-104">Beginning with applications targeting the .NET Framework 4.6.1, this exception is no longer thrown, and re-entrant filters as described above may be used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f9537-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f9537-105">Suggestion</span></span>

<span data-ttu-id="f9537-106">上述の再入可能な <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> の動作に対して <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> はスローされなくなります。</span><span class="sxs-lookup"><span data-stu-id="f9537-106">Be aware that <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> will no longer throw for the re-entrant <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> behavior described above.</span></span> <span data-ttu-id="f9537-107">これは、.NET Framework 4.6.1 をターゲットとするアプリケーションにのみ影響します。 .NET Framework 4.6.1 を対象とするアプリは、[DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation) 互換性スイッチを使用することによって、この変更を解除できます (または、以前の Framework をターゲットとしているアプリは、変更を受け入れることができます)。</span><span class="sxs-lookup"><span data-stu-id="f9537-107">This only affects applications targeting the .NET Framework 4.6.1.Apps targeting the .NET Framework 4.6.1 can opt out of this change (or apps targeting older Frameworks may opt in) by using the [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="f9537-108">名前</span><span class="sxs-lookup"><span data-stu-id="f9537-108">Name</span></span>          | <span data-ttu-id="f9537-109">[値]</span><span class="sxs-lookup"><span data-stu-id="f9537-109">Value</span></span>       |
|:--------------|:------------|
| <span data-ttu-id="f9537-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="f9537-110">Scope</span></span>         | <span data-ttu-id="f9537-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="f9537-111">Edge</span></span>        |
| <span data-ttu-id="f9537-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="f9537-112">Version</span></span>       | <span data-ttu-id="f9537-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f9537-113">4.6.1</span></span>       |
| <span data-ttu-id="f9537-114">種類</span><span class="sxs-lookup"><span data-stu-id="f9537-114">Type</span></span>          | <span data-ttu-id="f9537-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="f9537-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f9537-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f9537-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>
