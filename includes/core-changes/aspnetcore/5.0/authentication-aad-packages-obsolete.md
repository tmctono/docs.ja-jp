---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539507"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="32396-101">認証:AzureAD.UI および AzureADB2C.UI の API とパッケージが非推奨としてマークされる</span><span class="sxs-lookup"><span data-stu-id="32396-101">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="32396-102">ASP.NET Core 2.1 では、Azure Active Directory (Azure AD) と Azure Active Directory B2C (Azure AD B2C) の認証の統合は、[Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) パッケージと [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) パッケージによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="32396-102">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="32396-103">これらのパッケージによって提供される機能は、Azure AD v1.0 エンドポイントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="32396-103">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="32396-104">ASP.NET Core 5.0 以降では、Azure AD と Azure AD B2C の認証の統合は、[Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) パッケージによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="32396-104">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="32396-105">このパッケージは、以前は Azure AD v2.0 エンドポイントと呼ばれていた Microsoft ID プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="32396-105">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="32396-106">そのため、`Microsoft.AspNetCore.Authentication.AzureAD.UI` パッケージと `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` パッケージの古い API は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="32396-106">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="32396-107">ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32396-107">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32396-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="32396-108">Version introduced</span></span>

<span data-ttu-id="32396-109">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="32396-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="32396-110">以前の動作</span><span class="sxs-lookup"><span data-stu-id="32396-110">Old behavior</span></span>

<span data-ttu-id="32396-111">API は非推奨としてマークされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="32396-111">The APIs weren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="32396-112">新しい動作</span><span class="sxs-lookup"><span data-stu-id="32396-112">New behavior</span></span>

<span data-ttu-id="32396-113">API は非推奨としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="32396-113">The APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="32396-114">変更理由</span><span class="sxs-lookup"><span data-stu-id="32396-114">Reason for change</span></span>

<span data-ttu-id="32396-115">Azure AD および Azure AD B2C の認証機能は、`Microsoft.Identity.Web` によって提供される Microsoft Authentication Library (MSAL) API に移行されました。</span><span class="sxs-lookup"><span data-stu-id="32396-115">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32396-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="32396-116">Recommended action</span></span>

<span data-ttu-id="32396-117">[Web アプリ](https://github.com/azuread/microsoft-identity-web/wiki/web-apps)と [Web API](https://github.com/azuread/microsoft-identity-web/wiki/web-apis) の `Microsoft.Identity.Web` API ガイダンスに従って下さい。</span><span class="sxs-lookup"><span data-stu-id="32396-117">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

#### <a name="category"></a><span data-ttu-id="32396-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="32396-118">Category</span></span>

<span data-ttu-id="32396-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="32396-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32396-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="32396-120">Affected APIs</span></span>

* [<span data-ttu-id="32396-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="32396-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="32396-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="32396-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="32396-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="32396-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="32396-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="32396-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="32396-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="32396-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="32396-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="32396-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
