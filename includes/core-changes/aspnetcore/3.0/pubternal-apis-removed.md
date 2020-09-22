---
ms.openlocfilehash: 224cd3c7897c64ef05baba7d3d31dbe5ac0dd610
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606755"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="eb1c3-101">"Pubternal" API の削除</span><span class="sxs-lookup"><span data-stu-id="eb1c3-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="eb1c3-102">ASP.NET Core のパブリック API サーフェイスを管理しやすくするため、`*.Internal` 名前空間のほとんどの型 (:::no-loc text="\"pubternal\""::: API と呼んでいたもの) が本当に internal になりました。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="eb1c3-103">これらの名前空間のメンバーは、公開 API としてサポートされるべきものではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="eb1c3-104">API の破壊的変更はマイナー リリースで発生する可能性があり、よく発生しています。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="eb1c3-105">ASP.NET Core 3.0 に更新すると、これらの API に依存するコードは破壊的変更の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="eb1c3-106">詳細については、[dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) および [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eb1c3-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="eb1c3-107">Version introduced</span></span>

<span data-ttu-id="eb1c3-108">3.0</span><span class="sxs-lookup"><span data-stu-id="eb1c3-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="eb1c3-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="eb1c3-109">Old behavior</span></span>

<span data-ttu-id="eb1c3-110">影響を受ける API は `public` アクセス修飾子でマークされ、`*.Internal` 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="eb1c3-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="eb1c3-111">New behavior</span></span>

<span data-ttu-id="eb1c3-112">影響を受ける API は、[internal](../../../../docs/csharp/language-reference/keywords/internal.md) アクセス修飾子でマークされ、そのアセンブリ外のコードでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-112">The affected APIs are marked with the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="eb1c3-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="eb1c3-113">Reason for change</span></span>

<span data-ttu-id="eb1c3-114">これらの :::no-loc text="\"pubternal\""::: API のガイダンスでは以下が示されていました。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="eb1c3-115">予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-115">Could change without notice.</span></span>
* <span data-ttu-id="eb1c3-116">破壊的変更を防ぐために、.NET ポリシーの対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="eb1c3-117">API を `public` (`*.Internal` 名前空間でも) にしておくことは、ユーザーにとって混乱を招きます。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eb1c3-118">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="eb1c3-118">Recommended action</span></span>

<span data-ttu-id="eb1c3-119">これらの :::no-loc text="\"pubternal\""::: API の使用を停止します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="eb1c3-120">代わりの API について不明点がある場合は、[dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) リポジトリで問題を提起します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="eb1c3-121">たとえば、ASP.NET Core 2.2 プロジェクトの次の HTTP 要求バッファーリング コードを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="eb1c3-122">`EnableRewind` 拡張メソッドは、`Microsoft.AspNetCore.Http.Internal` 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="eb1c3-123">ASP.NET Core 3.0 プロジェクトで、`EnableRewind` 呼び出しを `EnableBuffering` 拡張メソッドへの呼び出しで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="eb1c3-124">要求バッファーリング機能は、以前と同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="eb1c3-125">`EnableBuffering` は `internal` API を呼び出すようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="eb1c3-126">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="eb1c3-126">Category</span></span>

<span data-ttu-id="eb1c3-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="eb1c3-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eb1c3-128">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="eb1c3-128">Affected APIs</span></span>

<span data-ttu-id="eb1c3-129">名前空間名に `Internal` セグメントが含まれる、`Microsoft.AspNetCore.*` 名前空間と `Microsoft.Extensions.*` 名前空間のすべての API。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="eb1c3-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb1c3-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
