---
ms.openlocfilehash: 424872b25436c7fcbe603639028e813eed6f9b99
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496708"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="2adc5-101">Regex.CompileToAssembly でコンパイルされたアセンブリは 4.0 と 4.5 の間で区別されます</span><span class="sxs-lookup"><span data-stu-id="2adc5-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="2adc5-102">説明</span><span class="sxs-lookup"><span data-stu-id="2adc5-102">Details</span></span>

<span data-ttu-id="2adc5-103">コンパイル済みの正規表現のアセンブリが .NET Framework 4.5 でビルドされ、.NET Framework 4 を対象としている場合、.NET Framework 4 がインストールされているシステム上でそのアセンブリの正規表現の 1 つを使用しようとすると、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2adc5-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2adc5-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2adc5-104">Suggestion</span></span>

<span data-ttu-id="2adc5-105">この問題を回避するには、次のいずれかの方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="2adc5-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="2adc5-106">.NET Framework 4 を使用して正規表現を含むアセンブリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2adc5-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="2adc5-107">解釈される正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="2adc5-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="2adc5-108">名前</span><span class="sxs-lookup"><span data-stu-id="2adc5-108">Name</span></span>    | <span data-ttu-id="2adc5-109">[値]</span><span class="sxs-lookup"><span data-stu-id="2adc5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2adc5-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="2adc5-110">Scope</span></span>   |<span data-ttu-id="2adc5-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="2adc5-111">Minor</span></span>|
|<span data-ttu-id="2adc5-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="2adc5-112">Version</span></span>|<span data-ttu-id="2adc5-113">4.5</span><span class="sxs-lookup"><span data-stu-id="2adc5-113">4.5</span></span>|
|<span data-ttu-id="2adc5-114">種類</span><span class="sxs-lookup"><span data-stu-id="2adc5-114">Type</span></span>|<span data-ttu-id="2adc5-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2adc5-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2adc5-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2adc5-116">Affected APIs</span></span>

- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)`

-->
