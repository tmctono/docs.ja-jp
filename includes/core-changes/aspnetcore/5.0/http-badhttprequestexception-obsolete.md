---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507090"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="c87e4-101">HTTP:Kestrel 型と IIS BadHttpRequestException 型が非推奨となり、置換されました</span><span class="sxs-lookup"><span data-stu-id="c87e4-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="c87e4-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` と `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` は非推奨となっており、`Microsoft.AspNetCore.Http.BadHttpRequestException` から誘導するように変更されています。</span><span class="sxs-lookup"><span data-stu-id="c87e4-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="c87e4-103">Kestrel サーバーと IIS サーバーでは、下位互換性のために、今後も以前の例外型がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c87e4-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="c87e4-104">非推奨になった型は、将来のリリースで削除される予定です。</span><span class="sxs-lookup"><span data-stu-id="c87e4-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="c87e4-105">ディスカッションについては、[dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c87e4-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c87e4-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c87e4-106">Version introduced</span></span>

<span data-ttu-id="c87e4-107">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="c87e4-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c87e4-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="c87e4-108">Old behavior</span></span>

<span data-ttu-id="c87e4-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` と`Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` は <xref:System.IO.IOException?displayProperty=nameWithType> から派生しています。</span><span class="sxs-lookup"><span data-stu-id="c87e4-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c87e4-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="c87e4-110">New behavior</span></span>

<span data-ttu-id="c87e4-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` と `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` は非推奨になっています。</span><span class="sxs-lookup"><span data-stu-id="c87e4-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="c87e4-112">型は、`System.IO.IOException` の派生型である `Microsoft.AspNetCore.Http.BadHttpRequestException` からも派生します。</span><span class="sxs-lookup"><span data-stu-id="c87e4-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c87e4-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="c87e4-113">Reason for change</span></span>

<span data-ttu-id="c87e4-114">次の変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="c87e4-114">The change was made to:</span></span>

* <span data-ttu-id="c87e4-115">重複する型を統合します。</span><span class="sxs-lookup"><span data-stu-id="c87e4-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="c87e4-116">異なるサーバー実装間で動作を統一します。</span><span class="sxs-lookup"><span data-stu-id="c87e4-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="c87e4-117">Kestrel または IIS の使用時、アプリで基本例外 `Microsoft.AspNetCore.Http.BadHttpRequestException` をキャッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87e4-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c87e4-118">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c87e4-118">Recommended action</span></span>

<span data-ttu-id="c87e4-119">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` と `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` の使用状況を `Microsoft.AspNetCore.Http.BadHttpRequestException` に置換します。</span><span class="sxs-lookup"><span data-stu-id="c87e4-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="c87e4-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c87e4-120">Category</span></span>

<span data-ttu-id="c87e4-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c87e4-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c87e4-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c87e4-122">Affected APIs</span></span>

- [<span data-ttu-id="c87e4-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="c87e4-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="c87e4-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="c87e4-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
