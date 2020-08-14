---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474380"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="cc502-101">Kestrel:非推奨としてマークされている Libuv トランスポート</span><span class="sxs-lookup"><span data-stu-id="cc502-101">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="cc502-102">早期バージョンの ASP.NET Core では、非同期出入力方法の実装詳細として Libuv が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="cc502-102">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="cc502-103">ASP.NET Core 2.0 では、代替となる <xref:System.Net.Sockets.Socket> ベースのトランスポートが開発されました。</span><span class="sxs-lookup"><span data-stu-id="cc502-103">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="cc502-104">ASP.NET Core 2.1 では、Kestrel は既定で `Socket` ベースのトランスポートを使用するように切り替えられました。</span><span class="sxs-lookup"><span data-stu-id="cc502-104">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="cc502-105">Libuv サポートは、互換性の問題で維持されました。</span><span class="sxs-lookup"><span data-stu-id="cc502-105">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="cc502-106">この時点では、`Socket` ベースのトランスポートの使用は Libuv トランスポートよりもはるかに一般的です。</span><span class="sxs-lookup"><span data-stu-id="cc502-106">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="cc502-107">結果的に、Libuv サポートは .NET 5.0 で非推奨となり、.NET 6.0 では完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cc502-107">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="cc502-108">この変更の一環として、新しいオペレーティング システム プラットフォーム (Windows ARM64 など) の Libuv サポートが .NET 5.0 の存続中に追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cc502-108">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="cc502-109">Libuv トランスポートを使用する必要があるブロッキング問題については、GitHub イシューをご覧ください ([dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409))。</span><span class="sxs-lookup"><span data-stu-id="cc502-109">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc502-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cc502-110">Version introduced</span></span>

<span data-ttu-id="cc502-111">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="cc502-111">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cc502-112">以前の動作</span><span class="sxs-lookup"><span data-stu-id="cc502-112">Old behavior</span></span>

<span data-ttu-id="cc502-113">Libuv API は非推奨ではありません。</span><span class="sxs-lookup"><span data-stu-id="cc502-113">The Libuv APIs aren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cc502-114">新しい動作</span><span class="sxs-lookup"><span data-stu-id="cc502-114">New behavior</span></span>

<span data-ttu-id="cc502-115">Libuv API は非推奨です。</span><span class="sxs-lookup"><span data-stu-id="cc502-115">The Libuv APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cc502-116">変更理由</span><span class="sxs-lookup"><span data-stu-id="cc502-116">Reason for change</span></span>

<span data-ttu-id="cc502-117">`Socket` ベースのトランスポートが既定です。</span><span class="sxs-lookup"><span data-stu-id="cc502-117">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="cc502-118">Libuv トランスポートの使用を続けることについて説得力のある理由がありません。</span><span class="sxs-lookup"><span data-stu-id="cc502-118">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc502-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="cc502-119">Recommended action</span></span>

<span data-ttu-id="cc502-120">[Libuv パッケージ](https://www.nuget.org/packages/Libuv)と拡張メソッドの使用を止める。</span><span class="sxs-lookup"><span data-stu-id="cc502-120">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

#### <a name="category"></a><span data-ttu-id="cc502-121">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cc502-121">Category</span></span>

<span data-ttu-id="cc502-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc502-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc502-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cc502-123">Affected APIs</span></span>

- [<span data-ttu-id="cc502-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="cc502-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="cc502-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="cc502-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="cc502-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="cc502-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="cc502-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="cc502-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="cc502-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
