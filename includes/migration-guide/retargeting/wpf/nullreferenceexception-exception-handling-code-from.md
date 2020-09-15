---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614849"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="88042-101">ImageSourceConverter.ConvertFrom からの例外処理コード内の NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="88042-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="88042-102">説明</span><span class="sxs-lookup"><span data-stu-id="88042-102">Details</span></span>

<span data-ttu-id="88042-103"><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> の例外処理コードのエラーでは、目的の例外 (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> または <xref:System.IO.FileNotFoundException?displayProperty=fullName>) の代わりに <xref:System.NullReferenceException?displayProperty=fullName> が誤ってスローされていました。</span><span class="sxs-lookup"><span data-stu-id="88042-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="88042-104">この変更によりエラーが修正されるため、このメソッドは正しい例外をスローするようになりました。</span><span class="sxs-lookup"><span data-stu-id="88042-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="88042-105">既定では、.NET Framework 4.6.2 以前を対象とするすべてのアプリケーションが、引き続き互換性のために <xref:System.NullReferenceException?displayProperty=fullName> をスローします。</span><span class="sxs-lookup"><span data-stu-id="88042-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="88042-106">.NET Framework 4.7 以降を使用する開発者には、正しい例外が表示されます。</span><span class="sxs-lookup"><span data-stu-id="88042-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="88042-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="88042-107">Suggestion</span></span>

<span data-ttu-id="88042-108">NET Framework 4.7 以降を対象とする場合に <xref:System.NullReferenceException?displayProperty=fullName> を取得する構成に戻したい開発者は、アプリケーションの App.config ファイルに次のコードを追加/マージします。</span><span class="sxs-lookup"><span data-stu-id="88042-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="88042-109">名前</span><span class="sxs-lookup"><span data-stu-id="88042-109">Name</span></span>    | <span data-ttu-id="88042-110">値</span><span class="sxs-lookup"><span data-stu-id="88042-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="88042-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="88042-111">Scope</span></span>   | <span data-ttu-id="88042-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="88042-112">Edge</span></span>        |
| <span data-ttu-id="88042-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="88042-113">Version</span></span> | <span data-ttu-id="88042-114">4.7</span><span class="sxs-lookup"><span data-stu-id="88042-114">4.7</span></span>         |
| <span data-ttu-id="88042-115">種類</span><span class="sxs-lookup"><span data-stu-id="88042-115">Type</span></span>    | <span data-ttu-id="88042-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="88042-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="88042-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="88042-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
