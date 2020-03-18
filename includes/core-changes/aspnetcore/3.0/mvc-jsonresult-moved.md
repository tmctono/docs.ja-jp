---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901614"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="f4d82-101">MVC:JsonResult は Microsoft.AspNetCore.Mvc.Core に移動されました</span><span class="sxs-lookup"><span data-stu-id="f4d82-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="f4d82-102">`JsonResult` は `Microsoft.AspNetCore.Mvc.Core` アセンブリに移動されました。</span><span class="sxs-lookup"><span data-stu-id="f4d82-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="f4d82-103">この型は、[Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json) に定義されていました。</span><span class="sxs-lookup"><span data-stu-id="f4d82-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="f4d82-104">大多数のユーザーのこの問題に対処するために、アセンブリ レベルの [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) 属性が `Microsoft.AspNetCore.Mvc.Formatters.Json` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f4d82-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="f4d82-105">サードパーティのライブラリを使用するアプリでは問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4d82-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f4d82-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f4d82-106">Version introduced</span></span>

<span data-ttu-id="f4d82-107">3.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="f4d82-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f4d82-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="f4d82-108">Old behavior</span></span>

<span data-ttu-id="f4d82-109">2\.2 ベースのライブラリを使用するアプリは正常にビルドされます。</span><span class="sxs-lookup"><span data-stu-id="f4d82-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f4d82-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="f4d82-110">New behavior</span></span>

<span data-ttu-id="f4d82-111">2\.2 ベースのライブラリを使用するアプリはコンパイルに失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4d82-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="f4d82-112">次のテキストのバリエーションを含むエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4d82-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="f4d82-113">このような問題の例については、[dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d82-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f4d82-114">変更理由</span><span class="sxs-lookup"><span data-stu-id="f4d82-114">Reason for change</span></span>

<span data-ttu-id="f4d82-115">[aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325) で説明されているように、ASP.NET Core の構成に対するプラットフォーム レベルの変更。</span><span class="sxs-lookup"><span data-stu-id="f4d82-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4d82-116">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="f4d82-116">Recommended action</span></span>

<span data-ttu-id="f4d82-117">2\.2 バージョンの `Microsoft.AspNetCore.Mvc.Formatters.Json` に対してコンパイルされたライブラリでは、すべてのコンシューマーの問題に対処するために再コンパイルが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4d82-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="f4d82-118">影響を受ける場合は、ライブラリの作成者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f4d82-118">If affected, contact the library author.</span></span> <span data-ttu-id="f4d82-119">ASP.NET Core 3.0 を対象とするライブラリの再コンパイルを要請してください。</span><span class="sxs-lookup"><span data-stu-id="f4d82-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="f4d82-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f4d82-120">Category</span></span>

<span data-ttu-id="f4d82-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f4d82-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4d82-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f4d82-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
