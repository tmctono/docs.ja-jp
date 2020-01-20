---
title: .NET ライブラリのクロス プラットフォーム ターゲット
description: クロス プラットフォームの .NET ライブラリを作成する際のベスト プラクティスの推奨事項。
ms.date: 08/12/2019
ms.openlocfilehash: 45eb67837c924558ec51381dd924abf9fd0fa315
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706518"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="199dc-103">クロス プラットフォーム ターゲット</span><span class="sxs-lookup"><span data-stu-id="199dc-103">Cross-platform targeting</span></span>

<span data-ttu-id="199dc-104">最新の .NET では、複数のオペレーティング システムとデバイスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="199dc-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="199dc-105">.NET のオープンソース ライブラリでは、開発者が Azure でホストされる ASP.NET Web サイトを構築しているか、Unity で .NET ゲームを構築しているかに関わらず、できるだけ多くの開発者をサポートすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="199dc-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="199dc-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="199dc-106">.NET Standard</span></span>

<span data-ttu-id="199dc-107">.NET Standard は、.NET ライブラリにクロスプラットフォーム サポートを追加する最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="199dc-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="199dc-108">[.NET Standard](../net-standard.md) は、すべての .NET 実装で使用できる .NET API の仕様です。</span><span class="sxs-lookup"><span data-stu-id="199dc-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="199dc-109">.NET Standard をターゲットにすることで、特定のバージョンの .NET Standard 内にある API を使用するように制約されるライブラリを作成できます。これは、そのバージョンの .NET Standard を実装するすべてのプラットフォームで使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="199dc-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="199dc-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="199dc-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="199dc-111">.NET Standard をターゲットとし、プロジェクトを正常にコンパイルした場合、すべてのプラットフォームでライブラリが正常に実行されることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="199dc-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="199dc-112">プラットフォーム固有の API は、他のプラットフォームでは失敗します。</span><span class="sxs-lookup"><span data-stu-id="199dc-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="199dc-113">たとえば、<xref:Microsoft.Win32.Registry?displayProperty=nameWithType> は Windows では成功し、他の OS で使用する場合、<xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="199dc-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="199dc-114">API の動作はそれぞれ異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="199dc-114">APIs can behave differently.</span></span> <span data-ttu-id="199dc-115">たとえば、アプリケーションによって iOS や UWP で Ahead Of Time コンパイルが使用される場合、リフレクション API のパフォーマンス特性は異なります。</span><span class="sxs-lookup"><span data-stu-id="199dc-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="199dc-116">.NET チームによって [Roslyn アナライザー](../analyzers/api-analyzer.md)が提供されます。これは、考えられる問題を検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="199dc-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="199dc-117">**✔️ すべきこと**: まず、`netstandard2.0` ターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-117">**✔️ DO** start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="199dc-118">ほとんどの汎用ライブラリでは、.NET Standard 2.0 外の API は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="199dc-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="199dc-119">.NET Standard 2.0 はすべての最新のプラットフォームでサポートされており、1 つのターゲットで複数のプラットフォームをサポートする場合に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="199dc-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="199dc-120">**❌ 避けること**: `netstandard1.x` ターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-120">**❌ AVOID** including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="199dc-121">.NET Standard 1.x は、NuGet の細かいパッケージ セットとして配布されます。大きなパッケージの依存関係グラフが作成されるため、開発者は構築時に多くのパッケージをダウンロードすることになります。</span><span class="sxs-lookup"><span data-stu-id="199dc-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="199dc-122">.NET Framework 4.6.1、UWP および Xamarin など、最新の .NET プラットフォームではすべて、.NET Standard 2.0 がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="199dc-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="199dc-123">特に古いプラットフォームをターゲットにする必要がある場合は、.NET Standard 1.x のみをターゲットにしてください。</span><span class="sxs-lookup"><span data-stu-id="199dc-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="199dc-124">**✔️ すべきこと**: `netstandard1.x` ターゲットが必要な場合は、`netstandard2.0` ターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-124">**✔️ DO** include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="199dc-125">.NET Standard 2.0 をサポートするすべてのプラットフォームでは `netstandard2.0` ターゲットを使用し、より小さなパッケージ グラフを作成することで利点が得られますが、古いプラットフォームは引き続き動作し、`netstandard1.x` ターゲットを使用するようにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="199dc-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="199dc-126">**❌ してはいけないこと**: ライブラリがプラットフォーム固有のアプリ モデルに依存する場合に、.NET Standard ターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-126">**❌ DO NOT** include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="199dc-127">たとえば、UWP コントロール ツールキット ライブラリは、UWP でのみ使用できるアプリ モデルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="199dc-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="199dc-128">アプリ モデル固有の API を .NET Standard で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="199dc-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="199dc-129">マルチターゲット</span><span class="sxs-lookup"><span data-stu-id="199dc-129">Multi-targeting</span></span>

<span data-ttu-id="199dc-130">場合によっては、ご利用のライブラリからフレームワーク固有の API にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="199dc-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="199dc-131">フレームワーク固有の API を呼び出す最善の方法は、1 つだけでなく、多くの [.NET ターゲット フレームワーク](../frameworks.md)に対するプロジェクトを構築する、マルチ ターゲットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="199dc-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="199dc-132">コンシューマーが個々のフレームワークに対して構築しなくても済むように、.NET Standard 出力に加え、1 つ以上のフレームワーク固有の出力が得られるようにします。</span><span class="sxs-lookup"><span data-stu-id="199dc-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="199dc-133">マルチ ターゲットを使用すると、単一の NuGet アセンブリ内にすべてのアセンブリがパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="199dc-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="199dc-134">その後、コンシューマーは同じパッケージを参照でき、NuGet では適切な実装が選択されます。</span><span class="sxs-lookup"><span data-stu-id="199dc-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="199dc-135">.NET Standard ライブラリはフォールバック ライブラリとして機能します。このライブラリは、NuGet パッケージでフレームワーク固有の実装が提供される場合を除き、あらゆる場所で使用されます。</span><span class="sxs-lookup"><span data-stu-id="199dc-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="199dc-136">マルチ ターゲットでは、コードで条件付きコンパイルを使用して、フレームワーク固有の API を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="199dc-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="199dc-137">![複数のアセンブリを含む NuGet パッケージ](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "複数のアセンブリを含む NuGet パッケージ")</span><span class="sxs-lookup"><span data-stu-id="199dc-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="199dc-138">**✔️ 検討すること**: .NET Standard に加え、.NET 実装をターゲットにする。</span><span class="sxs-lookup"><span data-stu-id="199dc-138">**✔️ CONSIDER** targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="199dc-139">.NET 実装をターゲットにすることで、.NET Standard 外にあるプラットフォーム固有の API を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="199dc-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="199dc-140">これを行うときに、.NET Standard のサポートを放棄しないでください。</span><span class="sxs-lookup"><span data-stu-id="199dc-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="199dc-141">代わりに、実装から分離させて、機能 API を提供します。</span><span class="sxs-lookup"><span data-stu-id="199dc-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="199dc-142">これにより、ライブラリを任意の場所で使用でき、ランタイムの機能を際立たせることができます。</span><span class="sxs-lookup"><span data-stu-id="199dc-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="199dc-143">**❌ 避けること**: すべてのターゲットでソース コードが同じである場合に、マルチ ターゲットを行う、または .NET Standard をターゲットにする。</span><span class="sxs-lookup"><span data-stu-id="199dc-143">**❌ AVOID** multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="199dc-144">.NET Standard アセンブリは、NuGet によって自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="199dc-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="199dc-145">個々の .NET 実装をターゲットにすると、`*.nupkg` サイズが増えるだけで、利点はありません。</span><span class="sxs-lookup"><span data-stu-id="199dc-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="199dc-146">**✔️ 検討すること**: `netstandard2.0` ターゲットを提供する際に、`net461` のターゲットを追加する。</span><span class="sxs-lookup"><span data-stu-id="199dc-146">**✔️ CONSIDER** adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="199dc-147">.NET Framework から .NET Standard 2.0 を使用する場合、いくつかの問題がありますが、.NET Framework 4.7.2 で対処されました。</span><span class="sxs-lookup"><span data-stu-id="199dc-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="199dc-148">.NET Framework 4.6.1 から 4.7.1 を引き続き使用している開発者に、.NET Framework 4.6.1 用にビルドされているバイナリを提供することで、その開発者のエクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="199dc-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="199dc-149">NuGet パッケージを使用してご利用のライブラリの配布を **✔️ 実施**してください。</span><span class="sxs-lookup"><span data-stu-id="199dc-149">**✔️ DO** distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="199dc-150">NuGet では開発者にとって最適なターゲットが選択され、開発者が適切な実装を選ぶ必要はなくなります。</span><span class="sxs-lookup"><span data-stu-id="199dc-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="199dc-151">**✔️ すべきこと**: マルチ ターゲットを行う場合に、プロジェクト ファイルの `TargetFrameworks` プロパティを使用する。</span><span class="sxs-lookup"><span data-stu-id="199dc-151">**✔️ DO** use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="199dc-152">**✔️ 検討すること**: プロジェクト ファイルが大幅に簡素化されるため、UWP と Xamarin に対するマルチ ターゲットを行う場合に、[MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) を使用する。</span><span class="sxs-lookup"><span data-stu-id="199dc-152">**✔️ CONSIDER** using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="199dc-153">古いターゲット</span><span class="sxs-lookup"><span data-stu-id="199dc-153">Older targets</span></span>

<span data-ttu-id="199dc-154">.NET では、長い間サポート対象外になっている NET Framework のバージョンと、一般的には使用されなくなったプラットフォームをターゲットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="199dc-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="199dc-155">できるだけ多くのターゲットでライブラリを動作させる価値はありますが、API の欠落を回避する必要がある場合、オーバーヘッドが大幅に増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="199dc-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="199dc-156">その範囲と制限事項を考えれば、特定のフレームワークをターゲットとする価値はなくなったと思われます。</span><span class="sxs-lookup"><span data-stu-id="199dc-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="199dc-157">**❌ してはいけないこと**: ポータブル クラス ライブラリ (PCL) ターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-157">**❌ DO NOT** include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="199dc-158">たとえば、`portable-net45+win8+wpa81+wp8` のようにします。</span><span class="sxs-lookup"><span data-stu-id="199dc-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="199dc-159">.NET Standard は、クロスプラットフォームの .NET ライブラリをサポートする最新の方法であり、PCL に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="199dc-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="199dc-160">**❌ してはいけないこと**: サポートされなくなった .NET プラットフォームのターゲットを含める。</span><span class="sxs-lookup"><span data-stu-id="199dc-160">**❌ DO NOT** include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="199dc-161">たとえば、`SL4`、`WP` のようになります。</span><span class="sxs-lookup"><span data-stu-id="199dc-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="199dc-162">[前へ](get-started.md)
>[次へ](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="199dc-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
