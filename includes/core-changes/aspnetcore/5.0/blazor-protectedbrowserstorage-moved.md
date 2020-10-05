---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077606"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="de4ef-101">Blazor: ProtectedBrowserStorage 機能を共有フレームワークに移行</span><span class="sxs-lookup"><span data-stu-id="de4ef-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="de4ef-102">ASP.NET Core 5.0 RC2 リリースの一部として、`ProtectedBrowserStorage` 機能は ASP.NET Core 共有フレームワークに移行されました。</span><span class="sxs-lookup"><span data-stu-id="de4ef-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="de4ef-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="de4ef-103">Version introduced</span></span>

<span data-ttu-id="de4ef-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="de4ef-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="de4ef-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="de4ef-105">Old behavior</span></span>

<span data-ttu-id="de4ef-106">ASP.NET Core 5.0 Preview 8 では、この機能は [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) パッケージの一部として利用できますが、Blazor WebAssembly でのみ使用可能でした。</span><span class="sxs-lookup"><span data-stu-id="de4ef-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="de4ef-107">ASP.NET Core 5.0 RC1 では、この機能は `Microsoft.AspNetCore.App` 共有フレームワークが参照される [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) パッケージの一部として利用できます。</span><span class="sxs-lookup"><span data-stu-id="de4ef-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="de4ef-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="de4ef-108">New behavior</span></span>

<span data-ttu-id="de4ef-109">ASP.NET Core 5.0 RC2 では、機能を参照して使用するために NuGet パッケージ参照が不要になりました。</span><span class="sxs-lookup"><span data-stu-id="de4ef-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="de4ef-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="de4ef-110">Reason for change</span></span>

<span data-ttu-id="de4ef-111">共有フレームワークへの移行は、お客様が期待するユーザー エクスペリエンスにより適っています。</span><span class="sxs-lookup"><span data-stu-id="de4ef-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="de4ef-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="de4ef-112">Recommended action</span></span>

<span data-ttu-id="de4ef-113">ASP.NET Core 5.0 RC1 からアップグレードする場合は、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="de4ef-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="de4ef-114">プロジェクトから `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` パッケージ参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="de4ef-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="de4ef-115">`using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` を `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;` で置き換え</span><span class="sxs-lookup"><span data-stu-id="de4ef-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="de4ef-116">`Startup` クラスから `AddProtectedBrowserStorage` への呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="de4ef-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="de4ef-117">ASP.NET Core 5.0 Preview 8 からアップグレードする場合は、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="de4ef-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="de4ef-118">プロジェクトから `Microsoft.AspNetCore.Components.Web.Extensions` パッケージ参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="de4ef-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="de4ef-119">`using Microsoft.AspNetCore.Components.Web.Extensions;` を `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;` で置き換え</span><span class="sxs-lookup"><span data-stu-id="de4ef-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="de4ef-120">`Startup` クラスから `AddProtectedBrowserStorage` への呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="de4ef-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="de4ef-121">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="de4ef-121">Category</span></span>

<span data-ttu-id="de4ef-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="de4ef-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="de4ef-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="de4ef-123">Affected APIs</span></span>

<span data-ttu-id="de4ef-124">なし</span><span class="sxs-lookup"><span data-stu-id="de4ef-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
