---
title: .NET Core のランタイム識別子 (RID) のカタログ
description: ランタイム識別子 (RID) と .NET Core での RID の使用方法について説明します。
ms.date: 02/22/2019
ms.openlocfilehash: e6bc3f75858d4b67cc8598e49ff4ad75521f16d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100919"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="3a26e-103">.NET Core の RID カタログ</span><span class="sxs-lookup"><span data-stu-id="3a26e-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="3a26e-104">RID は*ランタイム識別子*の略です。</span><span class="sxs-lookup"><span data-stu-id="3a26e-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="3a26e-105">RID の値は、アプリケーションが実行されている対象プラットフォームの識別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="3a26e-106">これは NuGet パッケージのプラットフォーム固有のアセットを表すために、.NET パッケージによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="3a26e-107">RID は、たとえば `linux-x64`、`ubuntu.14.04-x64`、`win7-x64`、または `osx.10.12-x64` などの値です。</span><span class="sxs-lookup"><span data-stu-id="3a26e-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="3a26e-108">ネイティブ依存関係のあるパッケージの場合、パッケージを復元できるプラットフォームが RID によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="3a26e-109">プロジェクト ファイルの `<RuntimeIdentifier>` 要素では、1 つの RID を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="3a26e-110">複数の RID は、プロジェクト ファイルの `<RuntimeIdentifiers>` 要素でセミコロン区切りのリストとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="3a26e-111">以下の [.NET Core CLI コマンド](./tools/index.md)の `--runtime` オプションで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="3a26e-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="3a26e-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="3a26e-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3a26e-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="3a26e-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="3a26e-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="3a26e-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="3a26e-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="3a26e-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="3a26e-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="3a26e-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="3a26e-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="3a26e-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="3a26e-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="3a26e-119">具体的なオペレーティング システムを表す RID は通常、`[os].[version]-[architecture]-[additional qualifiers]` のようなパターンになります。それぞれ、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="3a26e-120">`[os]` はオペレーティング システムまたはプラットフォーム システムのモニカーです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="3a26e-121">たとえば、`ubuntu` のようにします。</span><span class="sxs-lookup"><span data-stu-id="3a26e-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="3a26e-122">`[version]` は、オペレーティング システムのバージョンをドット区切りの形式 (`.`) で表したバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="3a26e-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="3a26e-123">たとえば、`15.10` のようにします。</span><span class="sxs-lookup"><span data-stu-id="3a26e-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="3a26e-124">バージョンはマーケティング バージョンに**しないでください**。プラットフォームの API アクセス領域が異なる、オペレーティング システムの複数の別々のバージョンを表すことがあるためです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="3a26e-125">`[architecture]` はプロセッサ アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="3a26e-126">たとえば `x86`、`x64`、`arm` または `arm64` などです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="3a26e-127">`[additional qualifiers]` はさまざまなプラットフォームをさらに区別します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="3a26e-128">たとえば、`aot` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="3a26e-129">RID グラフ</span><span class="sxs-lookup"><span data-stu-id="3a26e-129">RID graph</span></span>

<span data-ttu-id="3a26e-130">RID グラフまたはランタイム フォールバック グラフとは、相互に互換性のある RID の一覧です。</span><span class="sxs-lookup"><span data-stu-id="3a26e-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="3a26e-131">RID は [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) パッケージで定義されています。</span><span class="sxs-lookup"><span data-stu-id="3a26e-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="3a26e-132">サポートされている RID および RID グラフの一覧は、CoreFX リポジトリにある [*runtime.json*](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) ファイルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="3a26e-133">このファイルでは、基本となる RID を除くすべての RID に `"#import"` ステートメントが記述されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="3a26e-134">このステートメントは互換性のある RID を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a26e-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="3a26e-135">NuGet はパッケージを復元する際、指定されたランタイムと正確に一致するものを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="3a26e-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="3a26e-136">正確に一致するものが見つからない場合、NuGet は、RID グラフに基づいて最も互換性のあるシステムが見つかるまでグラフを遡ります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="3a26e-137">次に示す例は、`osx.10.12-x64` の RID として実際に記述されているものです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="3a26e-138">上の RID は `osx.10.12-x64` が `osx.10.11-x64` をインポートすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="3a26e-139">そのため、NuGet はパッケージを復元する際、`osx.10.12-x64` と正確に一致するものをパッケージから見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="3a26e-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="3a26e-140">特定のランタイムが見つからなかった場合、NuGet は、たとえば `osx.10.11-x64` ランタイムを指定しているパッケージを復元できます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="3a26e-141">次の例は、*runtime.json* ファイルにも定義されている少し大きめの RID グラフです。</span><span class="sxs-lookup"><span data-stu-id="3a26e-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="3a26e-142">すべての RID は最終的にルート `any` RID にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="3a26e-143">RID を使用する際に留意しておく必要のある注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="3a26e-144">RID は**不透明な文字列**であり、ブラック ボックスとして処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="3a26e-145">RID をプログラムによって作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="3a26e-146">プラットフォームであらかじめ定義されている RID を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="3a26e-147">RID は特定の値である必要があるため、実際の値から推測した値にしないでください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="3a26e-148">RID の使用</span><span class="sxs-lookup"><span data-stu-id="3a26e-148">Using RIDs</span></span>

<span data-ttu-id="3a26e-149">RID を使用するには、どのような RID があるのか知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="3a26e-150">プラットフォームには新しい RID が定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="3a26e-151">最新の完全バージョンについては、CoreFX リポジトリの [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) ファイルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="3a26e-152">.NET Core 2.0 SDK には、ポータブル RID の概念が導入されています。</span><span class="sxs-lookup"><span data-stu-id="3a26e-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="3a26e-153">それらは、RID グラフに新しく追加された値であり、特定のバージョンや OS のディストリビューションに関連付けられていません。 .NET Core 2.0 以降を使用するときは、それらを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a26e-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="3a26e-154">ほとんどのディストリビューション RID はポータブル RID にマップされるため、複数の Linux ディストリビューションを扱うときは特に便利です。</span><span class="sxs-lookup"><span data-stu-id="3a26e-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="3a26e-155">次の一覧では、各 OS に使用される最も一般的な RID の小さいサブセットを示します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="3a26e-156">Windows RID</span><span class="sxs-lookup"><span data-stu-id="3a26e-156">Windows RIDs</span></span>

<span data-ttu-id="3a26e-157">一般的な値のみを示します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-157">Only common values are listed.</span></span> <span data-ttu-id="3a26e-158">最新の完全バージョンについては、CoreFX リポジトリの [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) ファイルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

- <span data-ttu-id="3a26e-159">ポータブル (.NET Core 2.0 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="3a26e-160">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3a26e-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="3a26e-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3a26e-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="3a26e-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3a26e-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="3a26e-163">詳細については、「[Windows における .NET Core の前提条件](windows-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="3a26e-164">Linux RID</span><span class="sxs-lookup"><span data-stu-id="3a26e-164">Linux RIDs</span></span>

<span data-ttu-id="3a26e-165">一般的な値のみを示します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-165">Only common values are listed.</span></span> <span data-ttu-id="3a26e-166">最新の完全バージョンについては、CoreFX リポジトリの [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) ファイルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span> <span data-ttu-id="3a26e-167">以下の一覧にないディストリビューションが実行されているデバイスでも、ポータブル RID のいずれかで動作する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a26e-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="3a26e-168">たとえば、一覧にない Linux ディストリビューションが実行されている Raspberry Pi デバイスは、`linux-arm` の対象にできます。</span><span class="sxs-lookup"><span data-stu-id="3a26e-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="3a26e-169">ポータブル (.NET Core 2.0 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-169">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="3a26e-170">`linux-x64` (CentOS、Debian、Fedora、Ubuntu、および派生ディストリビューションなどのほとんどのデスクトップ ディストリビューション)</span><span class="sxs-lookup"><span data-stu-id="3a26e-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu and derivatives)</span></span>
  - <span data-ttu-id="3a26e-171">`linux-musl-x64` (Alpine Linux など、[musl](https://wiki.musl-libc.org/projects-using-musl.html) を使用している軽量ディストリビューション)</span><span class="sxs-lookup"><span data-stu-id="3a26e-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="3a26e-172">`linux-arm` (Raspberry Pi など、ARM で実行されている Linux ディストリビューション)</span><span class="sxs-lookup"><span data-stu-id="3a26e-172">`linux-arm` (Linux distributions running on ARM like Raspberry Pi)</span></span>
- <span data-ttu-id="3a26e-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="3a26e-173">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="3a26e-174">`rhel-x64` (RHEL バージョン 6 より後では、`linux-x64` に置き換えられます)</span><span class="sxs-lookup"><span data-stu-id="3a26e-174">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - <span data-ttu-id="3a26e-175">`rhel.6-x64` (.NET Core 2.0 以降)</span><span class="sxs-lookup"><span data-stu-id="3a26e-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="3a26e-176">Tizen (.NET Core 2.0 以降)</span><span class="sxs-lookup"><span data-stu-id="3a26e-176">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="3a26e-177">詳細については、「[Linux における .NET Core の前提条件](linux-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-177">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="3a26e-178">macOS RID</span><span class="sxs-lookup"><span data-stu-id="3a26e-178">macOS RIDs</span></span>

<span data-ttu-id="3a26e-179">macOS RID では、以前の "OSX" ブランドが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3a26e-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="3a26e-180">一般的な値のみを示します。</span><span class="sxs-lookup"><span data-stu-id="3a26e-180">Only common values are listed.</span></span> <span data-ttu-id="3a26e-181">最新の完全バージョンについては、CoreFX リポジトリの [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) ファイルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

- <span data-ttu-id="3a26e-182">ポータブル (.NET Core 2.0 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-182">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="3a26e-183">`osx-x64` (最小 OS バージョンは、macOS 10.12 Sierra です)</span><span class="sxs-lookup"><span data-stu-id="3a26e-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="3a26e-184">macOS 10.10 Yosemite</span><span class="sxs-lookup"><span data-stu-id="3a26e-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="3a26e-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="3a26e-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="3a26e-186">macOS 10.12 Sierra (.NET Core 1.1 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-186">macOS 10.12 Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="3a26e-187">macOS 10.13 High Sierra (.NET Core 1.1 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-187">macOS 10.13 High Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="3a26e-188">macOS 10.14 Mojave (.NET Core 1.1 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="3a26e-188">macOS 10.14 Mojave (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.14-x64`

<span data-ttu-id="3a26e-189">詳細については、「[macOS における .NET Core の前提条件](macos-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a26e-189">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a26e-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a26e-190">See also</span></span>

- [<span data-ttu-id="3a26e-191">ランタイム ID</span><span class="sxs-lookup"><span data-stu-id="3a26e-191">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/readme.md)
