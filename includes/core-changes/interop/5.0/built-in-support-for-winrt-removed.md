---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365652"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="f6acd-101">WinRT の組み込みサポートは .NET から削除されています</span><span class="sxs-lookup"><span data-stu-id="f6acd-101">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="f6acd-102">.NET の [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) API を使用するための組み込みサポートは削除されています。</span><span class="sxs-lookup"><span data-stu-id="f6acd-102">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f6acd-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f6acd-103">Version introduced</span></span>

<span data-ttu-id="f6acd-104">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="f6acd-104">5.0 Preview 6</span></span>

#### <a name="change-description"></a><span data-ttu-id="f6acd-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="f6acd-105">Change description</span></span>

<span data-ttu-id="f6acd-106">以前は、CoreCLR では、[Windows メタデータ (WinMD) ファイル](/uwp/winrt-cref/winmd-files)を使用し、WinRT タイプをアクティブ化し、使用していました。</span><span class="sxs-lookup"><span data-stu-id="f6acd-106">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="f6acd-107">.NET 5.0 以降、CoreCLR では、WinMD ファイルを直接使用することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f6acd-107">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="f6acd-108">サポートされていないアセンブリを参照しようとすると、<xref:System.IO.FileNotFoundException> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6acd-108">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="f6acd-109">WinRT クラスをアクティブ化すると、<xref:System.PlatformNotSupportedException> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6acd-109">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="f6acd-110">この破壊的変更は次の理由から行われました。</span><span class="sxs-lookup"><span data-stu-id="f6acd-110">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="f6acd-111">WinRT は .NET ランタイムとは別に開発し、改善できるため。</span><span class="sxs-lookup"><span data-stu-id="f6acd-111">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="f6acd-112">iOS や Android など、他のオペレーティング システムに提供されている相互運用システムと釣り合いを取るため。</span><span class="sxs-lookup"><span data-stu-id="f6acd-112">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="f6acd-113">C# の機能、中間言語 (IL) のリンク、Ahead Of Time (AOT) コンパイルなど、その他の .NET 機能を活用するため。</span><span class="sxs-lookup"><span data-stu-id="f6acd-113">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="f6acd-114">.NET ランタイム コードベースを簡略化するため。</span><span class="sxs-lookup"><span data-stu-id="f6acd-114">To simplify the .NET runtime codebase.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f6acd-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="f6acd-115">Recommended action</span></span>

- <span data-ttu-id="f6acd-116">[Microsoft.Windows.SDK.Contracts パッケージ](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts)への参照を削除し、[Microsoft.Windows.SDK.NET パッケージ](https://www.nuget.org/packages/microsoft.windows.sdk.net)への参照に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f6acd-116">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) and replace them with references to the [Microsoft.Windows.SDK.NET package](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span></span>

- <span data-ttu-id="f6acd-117">[C#/WinRT](/windows/uwp/csharp-winrt/) ツール チェーンを使用し、.NET 5.0 以降のバージョンで WinRT の API と型を生成するか、カスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f6acd-117">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types in .NET 5.0 and later versions.</span></span>

#### <a name="category"></a><span data-ttu-id="f6acd-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f6acd-118">Category</span></span>

<span data-ttu-id="f6acd-119">Interop</span><span class="sxs-lookup"><span data-stu-id="f6acd-119">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f6acd-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f6acd-120">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
