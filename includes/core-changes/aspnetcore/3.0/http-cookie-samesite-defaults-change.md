---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282529"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="c9e41-101">HTTP:SameSite の cookie オプションの既定値が一部、None に変更されました</span><span class="sxs-lookup"><span data-stu-id="c9e41-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="c9e41-102">`SameSite` は、一部のクロスサイト リクエスト フォージェリ (CSRF) 攻撃の軽減に貢献する cookie のオプションです。</span><span class="sxs-lookup"><span data-stu-id="c9e41-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="c9e41-103">このオプションが初めて導入されたとき、さまざまな ASP.NET Core API で使用されていた既定値に整合性がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="c9e41-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="c9e41-104">整合性がないことで、結果は混乱を招きました。</span><span class="sxs-lookup"><span data-stu-id="c9e41-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="c9e41-105">ASP.NET Core 3.0 より、この既定値の整合性が改善されました。</span><span class="sxs-lookup"><span data-stu-id="c9e41-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="c9e41-106">この機能はコンポーネントごとに選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e41-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c9e41-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c9e41-107">Version introduced</span></span>

<span data-ttu-id="c9e41-108">3.0</span><span class="sxs-lookup"><span data-stu-id="c9e41-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c9e41-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="c9e41-109">Old behavior</span></span>

<span data-ttu-id="c9e41-110">同様の ASP.NET Core API で異なる既定 <xref:Microsoft.AspNetCore.Http.SameSiteMode> 値が使用されました。</span><span class="sxs-lookup"><span data-stu-id="c9e41-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="c9e41-111">不整合の例は `HttpResponse.Cookies.Append(String, String)` と `HttpResponse.Cookies.Append(String, String, CookieOptions)` で確認できます。それぞれ、既定値は `SameSiteMode.None` と `SameSiteMode.Lax` でした。</span><span class="sxs-lookup"><span data-stu-id="c9e41-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c9e41-112">新しい動作</span><span class="sxs-lookup"><span data-stu-id="c9e41-112">New behavior</span></span>

<span data-ttu-id="c9e41-113">影響を受ける API の既定値はすべて `SameSiteMode.None` になります。</span><span class="sxs-lookup"><span data-stu-id="c9e41-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c9e41-114">変更理由</span><span class="sxs-lookup"><span data-stu-id="c9e41-114">Reason for change</span></span>

<span data-ttu-id="c9e41-115">既定値が変更され、`SameSite` がオプトイン機能になりました。</span><span class="sxs-lookup"><span data-stu-id="c9e41-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c9e41-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="c9e41-116">Recommended action</span></span>

<span data-ttu-id="c9e41-117">cookie を出す各コンポーネントでは、そのシナリオに `SameSite` が適切かどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e41-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="c9e41-118">影響を受ける API の使用状況を確認し、必要に応じて `SameSite` を再構成します。</span><span class="sxs-lookup"><span data-stu-id="c9e41-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="c9e41-119">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c9e41-119">Category</span></span>

<span data-ttu-id="c9e41-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c9e41-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c9e41-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c9e41-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
