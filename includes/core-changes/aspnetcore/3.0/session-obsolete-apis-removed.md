---
ms.openlocfilehash: bbf8a02096a4a654a041cfe17c760939fc17f2f5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394153"
---
### <a name="session-state-obsolete-apis-removed"></a><span data-ttu-id="e10a2-101">セッション状態: 古い API が削除された</span><span class="sxs-lookup"><span data-stu-id="e10a2-101">Session state: Obsolete APIs removed</span></span> 

<span data-ttu-id="e10a2-102">セッション Cookie を構成するための古い API が削除されました。</span><span class="sxs-lookup"><span data-stu-id="e10a2-102">Obsolete APIs for configuring session cookies were removed.</span></span> <span data-ttu-id="e10a2-103">詳細については、[aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e10a2-103">For more information, see [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e10a2-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e10a2-104">Version introduced</span></span>

<span data-ttu-id="e10a2-105">3.0</span><span class="sxs-lookup"><span data-stu-id="e10a2-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e10a2-106">変更理由</span><span class="sxs-lookup"><span data-stu-id="e10a2-106">Reason for change</span></span>

<span data-ttu-id="e10a2-107">この変更により、Cookie を使用する機能を構成するための API 間の一貫性が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e10a2-107">This change enforces consistency across APIs for configuring features that use cookies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e10a2-108">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="e10a2-108">Recommended action</span></span>

<span data-ttu-id="e10a2-109">削除された API の使用箇所を、置換された新しい API に移行します。</span><span class="sxs-lookup"><span data-stu-id="e10a2-109">Migrate usage of the removed APIs to their newer replacements.</span></span> <span data-ttu-id="e10a2-110">`Startup.ConfigureServices` での次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e10a2-110">Consider the following example in `Startup.ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a><span data-ttu-id="e10a2-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e10a2-111">Category</span></span>

<span data-ttu-id="e10a2-112">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e10a2-112">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e10a2-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e10a2-113">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
