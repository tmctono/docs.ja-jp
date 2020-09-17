---
ms.openlocfilehash: e3c9f23ca73ed9b85d09680ec15251ebe02c7f8e
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065220"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="3db23-101">CA1416: プラットフォームの互換性</span><span class="sxs-lookup"><span data-stu-id="3db23-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="3db23-102">.NET コード アナライザー ルール CA1416 は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3db23-102">.NET code analyzer rule CA1416 is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="3db23-103">オペレーティング システムが検証されていない呼び出しサイトからのプラットフォーム固有の API への呼び出しに対し、ビルドの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3db23-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3db23-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="3db23-104">Change description</span></span>

<span data-ttu-id="3db23-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3db23-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="3db23-106">これらのルールのいくつかは、CA1416 を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3db23-106">Several of these rules are enabled, by default, including CA1416.</span></span> <span data-ttu-id="3db23-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3db23-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="3db23-108">ルール CA1416 では、プラットフォームのコンテキストが検証されていない場所からプラットフォーム固有の API を使用していることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="3db23-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="3db23-109">ルール CA1416 のプラットフォーム互換性アナライザーは、.NET 5.0 の他の新機能の一部と連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="3db23-109">Rule CA1416, the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="3db23-110">.NET 5.0 において導入された `SupportedOSPlatformAttribute` 属性と `UnsupportedOSPlatformAttribute` 属性 (以前のプレビュー リリースでの名前は <xref:System.Runtime.Versioning.MinimumOSPlatformAttribute> および <xref:System.Runtime.Versioning.RemovedInOSPlatformAttribute>) を使用すると、API がサポートされて "*いる*"、またはサポートされて "*いない*" プラットフォームを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3db23-110">.NET 5.0 introduces `SupportedOSPlatformAttribute` and `UnsupportedOSPlatformAttribute` attributes (named <xref:System.Runtime.Versioning.MinimumOSPlatformAttribute> and <xref:System.Runtime.Versioning.RemovedInOSPlatformAttribute> in an earlier preview release), which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="3db23-111">これらの属性が存在しない場合、API はすべてのプラットフォームでサポートされているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="3db23-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="3db23-112">これらの属性は、Core .NET ライブラリ内のプラットフォーム固有の API に適用されています。</span><span class="sxs-lookup"><span data-stu-id="3db23-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="3db23-113">プロジェクトで使用されている API が、プロジェクトのターゲット プラットフォームでは使用できないものである場合、ルール CA1416 により、プラットフォームのコンテキストが検証されないプラットフォーム固有のすべての API 呼び出しに、フラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3db23-113">In projects that target platforms for which APIs that they use aren't available, rule CA1416 flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="3db23-114">`SupportedOSPlatformAttribute` 属性および `UnsupportedOSPlatformAttribute` 属性で装飾されている API のほとんどでは、サポートされていないオペレーティング システムで呼び出されると、<xref:System.PlatformNotSupportedException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3db23-114">Most of the APIs that are now decorated with the `SupportedOSPlatformAttribute` and `UnsupportedOSPlatformAttribute` attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="3db23-115">これらの API はプラットフォーム固有としてマークされるようになったので、ルール CA1416 は、OS のチェックを呼び出しサイトに追加することで、実行時の <xref:System.PlatformNotSupportedException> 例外を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3db23-115">Now that these APIs are marked as platform-specific, rule CA1416 helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="3db23-116">例</span><span class="sxs-lookup"><span data-stu-id="3db23-116">Examples</span></span>

- <span data-ttu-id="3db23-117"><xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> メソッドは、Windows でのみサポートされています (`[SupportedOSPlatform("windows")]` で修飾されます)。</span><span class="sxs-lookup"><span data-stu-id="3db23-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows (it's decorated with `[SupportedOSPlatform("windows")]`).</span></span> <span data-ttu-id="3db23-118">次のコードでは、プロジェクトの[ターゲット](../../../../docs/standard/frameworks.md)が `net5.0` である場合 (ただし `net5.0-windows` は除きます)、ビルド時に CA1416 警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3db23-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="3db23-119">警告を回避するために実行できる対応については、「[推奨アクション](#recommended-action)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db23-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="3db23-120"><xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> メソッドは、ブラウザーではサポートされていません (`[UnsupportedOSPlatform("browser")]` で修飾されています)。</span><span class="sxs-lookup"><span data-stu-id="3db23-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser (it's decorated with `[UnsupportedOSPlatform("browser")]`).</span></span> <span data-ttu-id="3db23-121">プロジェクトで Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) が使用されている場合、またはプロジェクト ファイルにサポートされるプラットフォーム (`<SupportedPlatform Include="browser" />`) として `browser` が含まれている場合、次のコードではビルド時に CA1416 警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3db23-121">The following code will produce a CA1416 warning at build time if the project uses the Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) or includes `browser` as a supported platform (`<SupportedPlatform Include="browser" />`) in the project file.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a><span data-ttu-id="3db23-122">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="3db23-122">Version introduced</span></span>

<span data-ttu-id="3db23-123">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="3db23-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3db23-124">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="3db23-124">Recommended action</span></span>

<span data-ttu-id="3db23-125">コードが適切なプラットフォームで実行されている場合にのみ、プラットフォーム固有の API を呼び出すようにします。</span><span class="sxs-lookup"><span data-stu-id="3db23-125">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="3db23-126">プラットフォーム固有の API を呼び出す前に、<xref:System.OperatingSystem?displayProperty=nameWithType> クラスの `Is<Platform>` メソッドのいずれか (`System.OperatingSystem.IsWindows()` など) を使用して、現在のオペレーティング システムを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="3db23-126">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, `System.OperatingSystem.IsWindows()`, before calling a platform-specific API.</span></span>

<span data-ttu-id="3db23-127">`if` ステートメントの条件内で、`Is<Platform>` メソッドのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3db23-127">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="3db23-128">または、`if` ステートメントを追加して実行時のオーバーヘッドを増やしたくない場合は、代わりに <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3db23-128">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="3db23-129">また、API をプラットフォーム固有としてマークすることもできます。その場合、要件の確認は呼び出し元で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3db23-129">You can also mark your API as platform-specific, in which case the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="3db23-130">特定のメソッドや型、またはアセンブリ全体をマークできます。</span><span class="sxs-lookup"><span data-stu-id="3db23-130">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="3db23-131">すべての呼び出しサイトを修正したくない場合は、次のいずれかのオプションを選択して警告を抑制できます。</span><span class="sxs-lookup"><span data-stu-id="3db23-131">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="3db23-132">ルール CA1416 を抑制するには、`#pragma` または [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) コンパイラ フラグを使用するか、.editorconfig ファイルで[ルールの重大度を `none` に設定](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations)します。</span><span class="sxs-lookup"><span data-stu-id="3db23-132">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="3db23-133">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="3db23-133">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="3db23-134">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db23-134">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="3db23-135">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3db23-135">Category</span></span>

- <span data-ttu-id="3db23-136">コード分析</span><span class="sxs-lookup"><span data-stu-id="3db23-136">Code analysis</span></span>
- <span data-ttu-id="3db23-137">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="3db23-137">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3db23-138">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3db23-138">Affected APIs</span></span>

<span data-ttu-id="3db23-139">Windows プラットフォームの場合:</span><span class="sxs-lookup"><span data-stu-id="3db23-139">For Windows platform:</span></span>

- <span data-ttu-id="3db23-140"><https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> に記載されているすべての API。</span><span class="sxs-lookup"><span data-stu-id="3db23-140">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="3db23-141">Blazor WebAssembly の場合:</span><span class="sxs-lookup"><span data-stu-id="3db23-141">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="3db23-142"><https://github.com/dotnet/runtime/issues/41087> に記載されているすべての API。</span><span class="sxs-lookup"><span data-stu-id="3db23-142">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="3db23-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="3db23-143">See also</span></span>

- [<span data-ttu-id="3db23-144">.NET API アナライザー</span><span class="sxs-lookup"><span data-stu-id="3db23-144">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
