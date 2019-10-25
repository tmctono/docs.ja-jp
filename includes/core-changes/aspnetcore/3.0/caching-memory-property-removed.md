---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394213"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="47a09-101">キャッシュ:CompactOnMemoryPressure プロパティが削除された</span><span class="sxs-lookup"><span data-stu-id="47a09-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="47a09-102">ASP.NET Core 3.0 のリリースでは、[古い MemoryCacheOptions API](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) が削除されました。</span><span class="sxs-lookup"><span data-stu-id="47a09-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="47a09-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="47a09-103">Change description</span></span>

<span data-ttu-id="47a09-104">この変更は、[aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221) に対するフォローアップです。</span><span class="sxs-lookup"><span data-stu-id="47a09-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="47a09-105">ディスカッションについては、[aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a09-105">For discussion, see [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="47a09-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="47a09-106">Version introduced</span></span>

<span data-ttu-id="47a09-107">3.0</span><span class="sxs-lookup"><span data-stu-id="47a09-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="47a09-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="47a09-108">Old behavior</span></span>

<span data-ttu-id="47a09-109">`MemoryCacheOptions.CompactOnMemoryPressure` プロパティを使用できました。</span><span class="sxs-lookup"><span data-stu-id="47a09-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="47a09-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="47a09-110">New behavior</span></span>

<span data-ttu-id="47a09-111">`MemoryCacheOptions.CompactOnMemoryPressure` プロパティは削除されました。</span><span class="sxs-lookup"><span data-stu-id="47a09-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="47a09-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="47a09-112">Reason for change</span></span>

<span data-ttu-id="47a09-113">キャッシュを自動的に圧縮すると、問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="47a09-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="47a09-114">予期しない動作を避けるため、キャッシュは必要なときにのみ圧縮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47a09-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="47a09-115">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="47a09-115">Recommended action</span></span>

<span data-ttu-id="47a09-116">キャッシュを圧縮するには、`MemoryCache` にダウンキャストし、必要に応じて `Compact` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="47a09-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="47a09-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="47a09-117">Category</span></span>

<span data-ttu-id="47a09-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47a09-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47a09-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="47a09-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
