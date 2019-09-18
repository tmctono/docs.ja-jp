---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988499"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="1cb56-101">Microsoft.VisualBasic.Constants.vbNewLine は古い</span><span class="sxs-lookup"><span data-stu-id="1cb56-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="1cb56-102">.NET Framework の <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数は[廃止](xref:System.ObsoleteAttribute)とマークされていますが、この属性は以前の .NET Core 3.0 ライブラリには存在していませんでした。</span><span class="sxs-lookup"><span data-stu-id="1cb56-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1cb56-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="1cb56-103">Version introduced</span></span>

<span data-ttu-id="1cb56-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="1cb56-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="1cb56-105">説明</span><span class="sxs-lookup"><span data-stu-id="1cb56-105">Details</span></span>

<span data-ttu-id="1cb56-106">.NET Core 3.0 Preview 8 以降では、.NET Framework の `vbNewLine` に準拠するため、[廃止](xref:System.ObsoleteAttribute)属性が <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 定数に適用されています。</span><span class="sxs-lookup"><span data-stu-id="1cb56-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="1cb56-107">`vbNewLine` 定数を使用すると、コンパイラの警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="1cb56-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="1cb56-108">以前のバージョンの .NET Core では、`vbNewLine` によりコンパイラの警告は発生しませんでした。</span><span class="sxs-lookup"><span data-stu-id="1cb56-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1cb56-109">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="1cb56-109">Recommended action</span></span>

<span data-ttu-id="1cb56-110">`vbNewLine` に対する[廃止](xref:System.ObsoleteAttribute)属性メッセージには、次の推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1cb56-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="1cb56-111">キャリッジ リターンとライン フィードの場合は、[vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb56-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="1cb56-112">現在のプラットフォームの改行の場合は、<xref:System.Environment.NewLine?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb56-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="1cb56-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1cb56-113">Category</span></span>

<span data-ttu-id="1cb56-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cb56-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1cb56-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1cb56-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

