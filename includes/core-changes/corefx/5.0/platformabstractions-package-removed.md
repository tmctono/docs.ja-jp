---
ms.openlocfilehash: d85fb8df7afdc5f4c3faecebcd24d11677798bc9
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365617"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="95264-101">Microsoft.DotNet.PlatformAbstractions パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="95264-101">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="95264-102">新しいバージョンの [Microsoft.DotNet.PlatformAbstractions NuGet パッケージ](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/)は生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="95264-102">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

#### <a name="change-description"></a><span data-ttu-id="95264-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="95264-103">Change description</span></span>

<span data-ttu-id="95264-104">これまで、新しいバージョンの <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> ライブラリは、新しいバージョンの .NET Core と共に生成されていました。</span><span class="sxs-lookup"><span data-stu-id="95264-104">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="95264-105">今後は、ライブラリに新機能が追加されなくなり、新しいメジャー バージョンはリリースされなくなります。</span><span class="sxs-lookup"><span data-stu-id="95264-105">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="95264-106">しかし、既存のバージョンのライブラリは引き続き動作し、サービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="95264-106">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="95264-107"><xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> ライブラリは、System.\* 名前空間に既に確立されている API と重複します。</span><span class="sxs-lookup"><span data-stu-id="95264-107">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="95264-108">また、一部の <xref:Microsoft.DotNet.PlatformAbstractions> API は、System.\*API の他の部分と同じレベルの監視と長期的なサポートを考慮して設計されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="95264-108">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="95264-109">たとえば、<xref:Microsoft.DotNet.PlatformAbstractions> では、`Platform` 列挙型を使用して、現在のオペレーティング システムのプラットフォームを記述します。</span><span class="sxs-lookup"><span data-stu-id="95264-109">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="95264-110">この列挙型の設計は、新しいプラットフォームおよび今後の柔軟性に対応できるように、<xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API が設計されたときに明示的に拒否されました。</span><span class="sxs-lookup"><span data-stu-id="95264-110">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="95264-111"><xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> ライブラリで有効にされたシナリオは、それがなくても実現できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="95264-111">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="95264-112">既存のバージョンは、.NET 5.0 以降でも引き続き動作し、以前のバージョンの .NET Core と共にサービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="95264-112">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="95264-113">しかし、新機能はライブラリに追加されなくなります。</span><span class="sxs-lookup"><span data-stu-id="95264-113">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="95264-114">代わりに、他のライブラリと API に新機能が追加されるようになります。</span><span class="sxs-lookup"><span data-stu-id="95264-114">Instead, new functionality will be added to other libraries and APIs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95264-115">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="95264-115">Version introduced</span></span>

<span data-ttu-id="95264-116">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="95264-116">5.0 Preview 6</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95264-117">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="95264-117">Recommended action</span></span>

- <span data-ttu-id="95264-118">要件が満たされている場合は、古いバージョンのライブラリを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="95264-118">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="95264-119">以前のバージョンで要件が満たされていない場合は、`PlatformAbstractions` API の代わりに推奨される代替を使用してください。</span><span class="sxs-lookup"><span data-stu-id="95264-119">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="95264-120">`PlatformAbstractions` API</span><span class="sxs-lookup"><span data-stu-id="95264-120">`PlatformAbstractions` API</span></span> | <span data-ttu-id="95264-121">推奨代替</span><span class="sxs-lookup"><span data-stu-id="95264-121">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="95264-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> および <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="95264-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="95264-123">`RuntimeEnvironment.OperatingSystem` と `RuntimeEnvironment.OperatingSystemVersion` のほとんどのユース ケースは、表示目的で使用されます。たとえば、ユーザー、ログ記録、テレメトリに表示するためのものです。</span><span class="sxs-lookup"><span data-stu-id="95264-123">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="95264-124">オペレーティング システム (OS) のバージョンに基づいて、実行時の決定を行うことはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="95264-124">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="95264-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> では、Windows および macOS オペレーティング システムの正しいバージョンが返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="95264-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now returns the correct version for Windows and macOS operating systems.</span></span> <span data-ttu-id="95264-126">しかし、ほとんどの Unix ディストリビューションでは、どのようなものを "OS バージョン" と見なすかは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="95264-126">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="95264-127">たとえば、Linux カーネル バージョンの場合もあれば、ディストリビューション バージョンの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="95264-127">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="95264-128">ほとんどの Unix プラットフォームでは、<xref:System.Environment.OSVersion?displayProperty=nameWithType> と <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> から、`uname` で返されるバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="95264-128">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="95264-129">Linux ディストリビューションの名前とバージョン情報を取得する場合は、 */etc/os-release* ファイルを読み取ることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95264-129">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

#### <a name="category"></a><span data-ttu-id="95264-130">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="95264-130">Category</span></span>

<span data-ttu-id="95264-131">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="95264-131">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95264-132">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="95264-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
