---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274767"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="87a18-101">SignalR:HubConnectionContext コンストラクターが変更されました</span><span class="sxs-lookup"><span data-stu-id="87a18-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="87a18-102">オプションの追加を将来においても利用できるように、SignalR の `HubConnectionContext` コンストラクターが複数のパラメーターではなく、1 つの options 型を受け取るように変更されました。</span><span class="sxs-lookup"><span data-stu-id="87a18-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="87a18-103">この変更により、2 つのコンストラクターが、options 型を受け取る 1 つのコンストラクターに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="87a18-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="87a18-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="87a18-104">Version introduced</span></span>

<span data-ttu-id="87a18-105">3.0</span><span class="sxs-lookup"><span data-stu-id="87a18-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="87a18-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="87a18-106">Old behavior</span></span>

<span data-ttu-id="87a18-107">`HubConnectionContext` にはコンストラクターが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="87a18-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="87a18-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="87a18-108">New behavior</span></span>

<span data-ttu-id="87a18-109">2 つのコンストラクターが削除され、1 つのコンストラクターに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="87a18-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="87a18-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="87a18-110">Reason for change</span></span>

<span data-ttu-id="87a18-111">新しいコンストラクターでは、新しい options オブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87a18-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="87a18-112">結果的に、コンストラクターや破壊的変更を増やすことなく、将来にわたり `HubConnectionContext` の機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="87a18-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="87a18-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="87a18-113">Recommended action</span></span>

<span data-ttu-id="87a18-114">次のコンストラクターを使用する代わりに:</span><span class="sxs-lookup"><span data-stu-id="87a18-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="87a18-115">次のコンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="87a18-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="87a18-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="87a18-116">Category</span></span>

<span data-ttu-id="87a18-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="87a18-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="87a18-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="87a18-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
