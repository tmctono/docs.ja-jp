---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620192"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="9b034-101">Regex.CompileToAssembly でコンパイルされたアセンブリは 4.0 と 4.5 の間で区別されます</span><span class="sxs-lookup"><span data-stu-id="9b034-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="9b034-102">説明</span><span class="sxs-lookup"><span data-stu-id="9b034-102">Details</span></span>

<span data-ttu-id="9b034-103">コンパイル済みの正規表現のアセンブリが .NET Framework 4.5 でビルドされ、.NET Framework 4 を対象としている場合、.NET Framework 4 がインストールされているシステム上でそのアセンブリの正規表現の 1 つを使用しようとすると、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9b034-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b034-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9b034-104">Suggestion</span></span>

<span data-ttu-id="9b034-105">この問題を回避するには、次のいずれかの方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b034-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="9b034-106">.NET Framework 4 を使用して正規表現を含むアセンブリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9b034-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="9b034-107">解釈される正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b034-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="9b034-108">名前</span><span class="sxs-lookup"><span data-stu-id="9b034-108">Name</span></span>    | <span data-ttu-id="9b034-109">[値]</span><span class="sxs-lookup"><span data-stu-id="9b034-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b034-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="9b034-110">Scope</span></span>   |<span data-ttu-id="9b034-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="9b034-111">Minor</span></span>|
|<span data-ttu-id="9b034-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="9b034-112">Version</span></span>|<span data-ttu-id="9b034-113">4.5</span><span class="sxs-lookup"><span data-stu-id="9b034-113">4.5</span></span>|
|<span data-ttu-id="9b034-114">種類</span><span class="sxs-lookup"><span data-stu-id="9b034-114">Type</span></span>|<span data-ttu-id="9b034-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="9b034-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9b034-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9b034-116">Affected APIs</span></span>

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
