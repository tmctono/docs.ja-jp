---
ms.openlocfilehash: 4e937f56f6315ce2abf76dd56989f4d2c4059f22
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065193"
---
### <a name="ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a><span data-ttu-id="a0514-101">CA1831: 文字列に範囲ベースのインデクサーの代わりに AsSpan を使用します</span><span class="sxs-lookup"><span data-stu-id="a0514-101">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>

<span data-ttu-id="a0514-102">.NET コード アナライザー ルール [CA1831](/visualstudio/code-quality/ca1831) は .NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a0514-102">.NET code analyzer rule [CA1831](/visualstudio/code-quality/ca1831) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="a0514-103"><xref:System.Range> ベースのインデクサーが文字列で使用されているが、コピーが意図されていないコードでは、ビルド警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0514-103">It produces a build warning for any code where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a0514-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="a0514-104">Change description</span></span>

<span data-ttu-id="a0514-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0514-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="a0514-106">これらのルールのいくつかは、既定では [CA1831](/visualstudio/code-quality/ca1831) を含めて有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a0514-106">Several of these rules are enabled, by default, including [CA1831](/visualstudio/code-quality/ca1831).</span></span> <span data-ttu-id="a0514-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0514-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="a0514-108">ルール CA1831 は、文字列で <xref:System.Range> ベースのインデクサーが使用されているが、コピーが意図されていないインスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="a0514-108">Rule CA1831 finds instances where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span> <span data-ttu-id="a0514-109"><xref:System.Range> ベースのインデクサーを文字列で直接使用して暗黙的なキャストを生成する場合は、文字列の要求された部分の不要なコピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0514-109">If the <xref:System.Range>-based indexer is used directly on a string to produce an implicit cast, then an unnecessary copy of the requested portion of the string is created.</span></span> <span data-ttu-id="a0514-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a0514-110">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

<span data-ttu-id="a0514-111">CA1831 では、代わりに文字列の "*スパン*" で <xref:System.Range> ベースのインデクサーを使用することが提案されます。</span><span class="sxs-lookup"><span data-stu-id="a0514-111">CA1831 suggests using the <xref:System.Range>-based indexer on a *span* of the string, instead.</span></span> <span data-ttu-id="a0514-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a0514-112">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

#### <a name="version-introduced"></a><span data-ttu-id="a0514-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a0514-113">Version introduced</span></span>

<span data-ttu-id="a0514-114">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a0514-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a0514-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a0514-115">Recommended action</span></span>

- <span data-ttu-id="a0514-116">コードを修正し、不要な割り当てを回避するには、<xref:System.Range> ベースのインデクサーを使用する前に <xref:System.MemoryExtensions.AsSpan(System.String)> または <xref:System.MemoryExtensions.AsMemory(System.String)> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a0514-116">To correct your code and avoid unnecessary allocations, call <xref:System.MemoryExtensions.AsSpan(System.String)> or <xref:System.MemoryExtensions.AsMemory(System.String)> before using the <xref:System.Range>-based indexer.</span></span> <span data-ttu-id="a0514-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a0514-117">For example:</span></span>

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- <span data-ttu-id="a0514-118">コードを変更しない場合は、その重要度を `suggestion` または `none` に設定して、ルールを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0514-118">If you don't want to change your code, you can disable the rule by setting its severity to `suggestion` or `none`.</span></span> <span data-ttu-id="a0514-119">詳細については、「[コード分析ルールを構成する](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0514-119">For more information, see [Configure code analysis rules](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md).</span></span>

- <span data-ttu-id="a0514-120">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a0514-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="a0514-121">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0514-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="a0514-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a0514-122">Category</span></span>

<span data-ttu-id="a0514-123">コード分析</span><span class="sxs-lookup"><span data-stu-id="a0514-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0514-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a0514-124">Affected APIs</span></span>

- <xref:System.Range?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Range`

-->
