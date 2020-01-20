---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901942"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="b0c07-101">MVC:コントローラー アクション名から Async サフィックスを削除</span><span class="sxs-lookup"><span data-stu-id="b0c07-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="b0c07-102">[dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849) への対処の一環として、ASP.NET Core MVC では、アクション名から `Async` サフィックスが既定で削除されます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-102">As part of addressing [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="b0c07-103">ASP.NET Core 3.0 以降、この変更はルーティングとリンク生成の両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b0c07-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b0c07-104">Version introduced</span></span>

<span data-ttu-id="b0c07-105">3.0</span><span class="sxs-lookup"><span data-stu-id="b0c07-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b0c07-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="b0c07-106">Old behavior</span></span>

<span data-ttu-id="b0c07-107">次の ASP.NET Core MVC コントローラーについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="b0c07-107">Consider the following ASP.NET Core MVC controller:</span></span>

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

<span data-ttu-id="b0c07-108">このアクションは、`Product/ListAsync` を介してルーティング可能です。</span><span class="sxs-lookup"><span data-stu-id="b0c07-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="b0c07-109">リンクの生成には、`Async` サフィックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="b0c07-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="b0c07-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="b0c07-111">New behavior</span></span>

<span data-ttu-id="b0c07-112">ASP.NET Core 3.0 では、このアクションは `Product/List` を介してルーティング可能です。</span><span class="sxs-lookup"><span data-stu-id="b0c07-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="b0c07-113">リンク生成コードでは、`Async` サフィックスを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="b0c07-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="b0c07-115">この変更は、`[ActionName]` 属性を使用して指定された名前には影響しません。</span><span class="sxs-lookup"><span data-stu-id="b0c07-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="b0c07-116">新しい動作は、`Startup.ConfigureServices` で `MvcOptions.SuppressAsyncSuffixInActionNames` を `false` に設定することによって無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="b0c07-117">変更理由</span><span class="sxs-lookup"><span data-stu-id="b0c07-117">Reason for change</span></span>

<span data-ttu-id="b0c07-118">規則に従い、非同期 .NET メソッドには `Async` サフィックスを付加します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="b0c07-119">ただし、メソッドで MVC アクションを定義する場合、`Async` サフィックスを使用するのは望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="b0c07-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b0c07-120">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="b0c07-120">Recommended action</span></span>

<span data-ttu-id="b0c07-121">アプリが、名前の `Async` サフィックスを保持する MVC アクションに依存している場合、次のいずれかの軽減策を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="b0c07-122">`[ActionName]` 属性を使用して、元の名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="b0c07-123">`Startup.ConfigureServices` で `MvcOptions.SuppressAsyncSuffixInActionNames` を `false` に設定して、名前の変更を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="b0c07-124">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b0c07-124">Category</span></span>

<span data-ttu-id="b0c07-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b0c07-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b0c07-126">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b0c07-126">Affected APIs</span></span>

<span data-ttu-id="b0c07-127">None</span><span class="sxs-lookup"><span data-stu-id="b0c07-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
