---
ms.openlocfilehash: 5ef785f476b795a9c53e511d51b2683b99e6da05
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182013"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="cdf3b-101">Microsoft.VisualBasic.Constants.vbNewLine は古い</span><span class="sxs-lookup"><span data-stu-id="cdf3b-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="cdf3b-102"><xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数は、.NET Core 3.0 Preview 8 以降では[廃止](xref:System.ObsoleteAttribute)としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cdf3b-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cdf3b-103">Version introduced</span></span>

<span data-ttu-id="cdf3b-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="cdf3b-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="cdf3b-105">説明</span><span class="sxs-lookup"><span data-stu-id="cdf3b-105">Details</span></span>

<span data-ttu-id="cdf3b-106">.NET Core 3.0 Preview 8 以降では、[廃止](xref:System.ObsoleteAttribute)属性が <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数に適用されています。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="cdf3b-107">その定数を使用すると、コンパイラの警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="cdf3b-108">.NET Core と .NET Framework の両方の以前のリリースでは、廃止としてマークされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-108">In previous releases of both .NET Core and .NET Framework, it was not marked as obsolete.</span></span>

<span data-ttu-id="cdf3b-109">この変更は、Visual Basic をマルチプラットフォーム開発用の言語としてサポートするために行われました。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="cdf3b-110">`vbNewLine` 定数は、Windows での改行文字シーケンスである `\r\n` と同等です。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-110">The `vbNewLine` constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="cdf3b-111">Unix ベースのシステムでは、改行文字は `\n` です。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-111">On Unix-based systems, the newline character is `\n`.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="cdf3b-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="cdf3b-112">Recommended action</span></span>

<span data-ttu-id="cdf3b-113">`vbNewLine` に対する[廃止](xref:System.ObsoleteAttribute)属性メッセージには、次の推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="cdf3b-114">キャリッジ リターンとライン フィードの場合は、[vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-114">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="cdf3b-115">現在のプラットフォームの改行の場合は、<xref:System.Environment.NewLine?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdf3b-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="cdf3b-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cdf3b-116">Category</span></span>

<span data-ttu-id="cdf3b-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cdf3b-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cdf3b-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cdf3b-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

