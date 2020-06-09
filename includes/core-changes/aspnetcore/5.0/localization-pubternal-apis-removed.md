---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446974"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="b7773-101">ローカリゼーション:"Pubternal" API の削除</span><span class="sxs-lookup"><span data-stu-id="b7773-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="b7773-102">ASP.NET Core のパブリック API サーフェイスをより適切に維持するために、一部の :::no-loc text="\"pubternal\""::: ローカライズ API を削除しました。</span><span class="sxs-lookup"><span data-stu-id="b7773-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="b7773-103">:::no-loc text="\"pubternal\""::: API には、`public` のアクセス修飾子があり、[internal](/dotnet/csharp/language-reference/keywords/internal) インテントを意味する名前空間に定義されています。</span><span class="sxs-lookup"><span data-stu-id="b7773-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](/dotnet/csharp/language-reference/keywords/internal) intent.</span></span>

<span data-ttu-id="b7773-104">ディスカッションについては、[dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7773-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b7773-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b7773-105">Version introduced</span></span>

<span data-ttu-id="b7773-106">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="b7773-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b7773-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="b7773-107">Old behavior</span></span>

<span data-ttu-id="b7773-108">次の API が `public` でした。</span><span class="sxs-lookup"><span data-stu-id="b7773-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="b7773-109">次のいずれかのパラメーター型を取る `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` コンストラクター オーバーロード。</span><span class="sxs-lookup"><span data-stu-id="b7773-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="b7773-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="b7773-110">New behavior</span></span>

<span data-ttu-id="b7773-111">変更一覧の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b7773-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="b7773-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` が `Microsoft.Extensions.Localization.AssemblyWrapper` となり、現在 `internal` になりました。</span><span class="sxs-lookup"><span data-stu-id="b7773-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="b7773-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` が `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` となり、現在 `internal` になりました。</span><span class="sxs-lookup"><span data-stu-id="b7773-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="b7773-114">次のいずれかのパラメーター型を取る `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` コンストラクター オーバーロードは、現在 `internal` になりました。</span><span class="sxs-lookup"><span data-stu-id="b7773-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="b7773-115">変更理由</span><span class="sxs-lookup"><span data-stu-id="b7773-115">Reason for change</span></span>

<span data-ttu-id="b7773-116">詳細は、[aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882) で説明していますが、:::no-loc text="\"pubternal\""::: 型が `public` API サーフェイスから削除されました。</span><span class="sxs-lookup"><span data-stu-id="b7773-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="b7773-117">これらの変更により、その設計判断により多くのクラスを順応させることができます。</span><span class="sxs-lookup"><span data-stu-id="b7773-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="b7773-118">問題のクラスは、チームの内部テストの拡張ポイントを意味していました。</span><span class="sxs-lookup"><span data-stu-id="b7773-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b7773-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="b7773-119">Recommended action</span></span>

<span data-ttu-id="b7773-120">可能性は低いですが、一部のアプリが意図的にまたは誤って :::no-loc text="\"pubternal\""::: 型に依存するようになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7773-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="b7773-121">この型から移行する方法については、「[新しい動作](#new-behavior)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7773-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="b7773-122">この変更の前にはパブリックとして許可されていた API が、現在では許可されなくなったシナリオを特定した場合は、[dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) にイシューを立ててください。</span><span class="sxs-lookup"><span data-stu-id="b7773-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="b7773-123">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b7773-123">Category</span></span>

<span data-ttu-id="b7773-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7773-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b7773-125">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b7773-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
