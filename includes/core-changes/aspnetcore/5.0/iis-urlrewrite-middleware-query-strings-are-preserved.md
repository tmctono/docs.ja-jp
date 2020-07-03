---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325201"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="1dbb9-101">IIS:UrlRewrite ミドルウェア クエリ文字列は保持されます</span><span class="sxs-lookup"><span data-stu-id="1dbb9-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="1dbb9-102">IIS UrlRewrite ミドルウェアの不具合により、クエリ文字列は書き換えルールに保持されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="1dbb9-103">IIS UrlRewrite モジュールの動作との一貫性を維持するため、この不具合が修正されました。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="1dbb9-104">ディスカッションについては、イシュー [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1dbb9-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="1dbb9-105">Version introduced</span></span>

<span data-ttu-id="1dbb9-106">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="1dbb9-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1dbb9-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="1dbb9-107">Old behavior</span></span>

<span data-ttu-id="1dbb9-108">次の書き換えルールについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="1dbb9-109">上記のルールでは、クエリ文字列は追加されません。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="1dbb9-110">`/about?id=1` のような URI は、`/contact?id=1` ではなく、`/contact` にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="1dbb9-111">`appendQueryString` 属性は既定で `true` にもなります。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1dbb9-112">新しい動作</span><span class="sxs-lookup"><span data-stu-id="1dbb9-112">New behavior</span></span>

<span data-ttu-id="1dbb9-113">クエリ文字列は保持されます。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-113">The query string is preserved.</span></span> <span data-ttu-id="1dbb9-114">[以前の動作](#old-behavior)の例からの URI は `/contact?id=1` になります。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1dbb9-115">変更理由</span><span class="sxs-lookup"><span data-stu-id="1dbb9-115">Reason for change</span></span>

<span data-ttu-id="1dbb9-116">以前の動作は、IIS UrlRewrite モジュールの動作と一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="1dbb9-117">ミドルウェアとモジュールの間で移植をサポートするため、目標は一貫性のある動作を維持することになります。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1dbb9-118">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="1dbb9-118">Recommended action</span></span>

<span data-ttu-id="1dbb9-119">クエリ文字列を削除する動作を優先する場合、`action` 要素を `appendQueryString="false"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="1dbb9-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="1dbb9-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1dbb9-120">Category</span></span>

<span data-ttu-id="1dbb9-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dbb9-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1dbb9-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1dbb9-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
