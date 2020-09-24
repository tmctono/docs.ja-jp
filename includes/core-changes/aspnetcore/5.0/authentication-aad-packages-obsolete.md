---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539507"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>認証:AzureAD.UI および AzureADB2C.UI の API とパッケージが非推奨としてマークされる

ASP.NET Core 2.1 では、Azure Active Directory (Azure AD) と Azure Active Directory B2C (Azure AD B2C) の認証の統合は、[Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) パッケージと [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) パッケージによって提供されます。 これらのパッケージによって提供される機能は、Azure AD v1.0 エンドポイントに基づいています。

ASP.NET Core 5.0 以降では、Azure AD と Azure AD B2C の認証の統合は、[Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) パッケージによって提供されます。 このパッケージは、以前は Azure AD v2.0 エンドポイントと呼ばれていた Microsoft ID プラットフォームに基づいています。 そのため、`Microsoft.AspNetCore.Authentication.AzureAD.UI` パッケージと `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` パッケージの古い API は非推奨となりました。

ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807) を参照してください。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="old-behavior"></a>以前の動作

API は非推奨としてマークされていませんでした。

#### <a name="new-behavior"></a>新しい動作

API は非推奨としてマークされています。

#### <a name="reason-for-change"></a>変更理由

Azure AD および Azure AD B2C の認証機能は、`Microsoft.Identity.Web` によって提供される Microsoft Authentication Library (MSAL) API に移行されました。

#### <a name="recommended-action"></a>推奨アクション

[Web アプリ](https://github.com/azuread/microsoft-identity-web/wiki/web-apps)と [Web API](https://github.com/azuread/microsoft-identity-web/wiki/web-apis) の `Microsoft.Identity.Web` API ガイダンスに従って下さい。

#### <a name="category"></a>カテゴリ

ASP.NET Core

#### <a name="affected-apis"></a>影響を受ける API

* [Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
