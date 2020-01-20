---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901911"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="baf36-101">ホスティング: 汎用ホストによる Startup コンストラクター挿入の制限</span><span class="sxs-lookup"><span data-stu-id="baf36-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="baf36-102">汎用ホストが `Startup` クラスのコンストラクター挿入でサポートする型は、`IHostEnvironment`、`IWebHostEnvironment`、`IConfiguration` だけです。</span><span class="sxs-lookup"><span data-stu-id="baf36-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="baf36-103">`WebHost` を使用しているアプリは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="baf36-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="baf36-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="baf36-104">Change description</span></span>

<span data-ttu-id="baf36-105">ASP.NET Core 3.0 より前では、コンストラクター挿入は `Startup` クラスのコンストラクターの任意の型に使用できました。</span><span class="sxs-lookup"><span data-stu-id="baf36-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="baf36-106">ASP.NET Core 3.0 では、Web スタックが汎用ホスト ライブラリに再プラットフォーム化されました。</span><span class="sxs-lookup"><span data-stu-id="baf36-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="baf36-107">この変更は、テンプレートの *Program.cs* ファイルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="baf36-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="baf36-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="baf36-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="baf36-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="baf36-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="baf36-110">`Host` では、1 つの依存関係挿入 (DI) コンテナーを使用してアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="baf36-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="baf36-111">`WebHost` ホストでは 2 つのコンテナーを使用します。1 つがホスト用、もう 1 つがアプリ用です。</span><span class="sxs-lookup"><span data-stu-id="baf36-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="baf36-112">これにより、`Startup` コンストラクターでは、カスタム サービス挿入がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="baf36-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="baf36-113">挿入できるのは、`IHostEnvironment`、`IWebHostEnvironment`、`IConfiguration` だけです。</span><span class="sxs-lookup"><span data-stu-id="baf36-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="baf36-114">この変更により、シングルトン サービスの重複作成などの DI の問題を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="baf36-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="baf36-115">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="baf36-115">Version introduced</span></span>

<span data-ttu-id="baf36-116">3.0</span><span class="sxs-lookup"><span data-stu-id="baf36-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="baf36-117">変更理由</span><span class="sxs-lookup"><span data-stu-id="baf36-117">Reason for change</span></span>

<span data-ttu-id="baf36-118">この変更は、汎用ホスト ライブラリへの Web スタックの再プラットフォーム化の結果です。</span><span class="sxs-lookup"><span data-stu-id="baf36-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="baf36-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="baf36-119">Recommended action</span></span>

<span data-ttu-id="baf36-120">サービスを `Startup.Configure` メソッド シグネチャに挿入します。</span><span class="sxs-lookup"><span data-stu-id="baf36-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="baf36-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="baf36-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="baf36-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="baf36-122">Category</span></span>

<span data-ttu-id="baf36-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="baf36-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="baf36-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="baf36-124">Affected APIs</span></span>

<span data-ttu-id="baf36-125">None</span><span class="sxs-lookup"><span data-stu-id="baf36-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
