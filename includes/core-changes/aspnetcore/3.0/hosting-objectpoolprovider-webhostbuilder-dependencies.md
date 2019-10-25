---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394313"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="99660-101">ホスティング:ObjectPoolProvider が WebHostBuilder 依存関係から削除されました</span><span class="sxs-lookup"><span data-stu-id="99660-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="99660-102">ASP.NET Core の定額課金を増やすために、`ObjectPoolProvider` が主な依存関係のセットから削除されました。</span><span class="sxs-lookup"><span data-stu-id="99660-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="99660-103">`ObjectPoolProvider` に依存する特定のコンポーネント自体で、それが追加されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="99660-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="99660-104">詳細については、[aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99660-104">For discussion, see [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="99660-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="99660-105">Version introduced</span></span>

<span data-ttu-id="99660-106">3.0</span><span class="sxs-lookup"><span data-stu-id="99660-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="99660-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="99660-107">Old behavior</span></span>

<span data-ttu-id="99660-108">`WebHostBuilder` によって、DI コンテナーに既定で `ObjectPoolProvider` が提供されます。</span><span class="sxs-lookup"><span data-stu-id="99660-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="99660-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="99660-109">New behavior</span></span>

<span data-ttu-id="99660-110">`WebHostBuilder` によって、DI コンテナーに既定で `ObjectPoolProvider` が提供されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="99660-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="99660-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="99660-111">Reason for change</span></span>

<span data-ttu-id="99660-112">この変更は、ASP.NET Core の定額課金を増やすために行われました。</span><span class="sxs-lookup"><span data-stu-id="99660-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="99660-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="99660-113">Recommended action</span></span>

<span data-ttu-id="99660-114">コンポーネントに `ObjectPoolProvider` が必要な場合は、`IServiceCollection` を介して依存関係に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99660-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="99660-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="99660-115">Category</span></span>

<span data-ttu-id="99660-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="99660-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="99660-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="99660-117">Affected APIs</span></span>

<span data-ttu-id="99660-118">なし</span><span class="sxs-lookup"><span data-stu-id="99660-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
