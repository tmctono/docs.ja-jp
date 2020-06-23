---
title: ASP.NET Core の破壊的変更
titleSuffix: ''
description: ASP.NET Core における破壊的変更をリストアップします。
ms.date: 06/11/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: a6ddf97f907a1cba57e51d6fd516d1f94272f725
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803271"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="b6828-103">ASP.NET Core の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="b6828-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="b6828-104">ASP.NET Core からは、.NET Core で使用される Web アプリ開発機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b6828-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="b6828-105">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6828-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="b6828-106">Antiforgery、CORS、Diagnostics、MVC、Routing の古い API の削除</span><span class="sxs-lookup"><span data-stu-id="b6828-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="b6828-107">認証:Google+ の非推奨</span><span class="sxs-lookup"><span data-stu-id="b6828-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="b6828-108">認証:HttpContext.Authentication プロパティの削除</span><span class="sxs-lookup"><span data-stu-id="b6828-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="b6828-109">認証:Newtonsoft.Json 型の置き換え</span><span class="sxs-lookup"><span data-stu-id="b6828-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="b6828-110">認証:OAuthHandler ExchangeCodeAsync 署名の変更</span><span class="sxs-lookup"><span data-stu-id="b6828-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="b6828-111">承認:AddAuthorization のオーバーロードを別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="b6828-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="b6828-112">承認:AuthorizationFilterContext.Filters から IAllowAnonymous を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="b6828-113">承認:IAuthorizationPolicyProvider の実装に新しいメソッドが必要</span><span class="sxs-lookup"><span data-stu-id="b6828-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="b6828-114">Azure:Microsoft というプレフィックスが付いた Azure 統合パッケージが削除された</span><span class="sxs-lookup"><span data-stu-id="b6828-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="b6828-115">キャッシュ:CompactOnMemoryPressure プロパティの削除</span><span class="sxs-lookup"><span data-stu-id="b6828-115">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="b6828-116">キャッシュ:Microsoft.Extensions.Caching.SqlServer で新しい SqlClient パッケージを使用</span><span class="sxs-lookup"><span data-stu-id="b6828-116">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="b6828-117">キャッシュ:ResponseCaching の "pubternal" 型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="b6828-117">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b6828-118">データ保護:DataProtection.AzureStorage で新しい Azure Storage API を使用</span><span class="sxs-lookup"><span data-stu-id="b6828-118">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="b6828-119"> 拡張機能:一部の NuGet パッケージに影響するパッケージ参照の変更</span><span class="sxs-lookup"><span data-stu-id="b6828-119">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="b6828-120">ホスティング:Windows ホスティング バンドルから AspNetCoreModule V1 を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-120">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="b6828-121">ホスティング:汎用ホストによる Startup コンストラクター挿入の制限</span><span class="sxs-lookup"><span data-stu-id="b6828-121">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="b6828-122">ホスティング:IIS アウトプロセス アプリ用に HTTPS リダイレクトを有効化</span><span class="sxs-lookup"><span data-stu-id="b6828-122">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="b6828-123">ホスティング:IHostingEnvironment と IApplicationLifetime の型を置き換え</span><span class="sxs-lookup"><span data-stu-id="b6828-123">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b6828-124">ホスティング:WebHostBuilder 依存関係から ObjectPoolProvider を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-124">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="b6828-125">HTTP:Kestrel および IIS BadHttpRequestException の種類を古い形式としてマークし、置換</span><span class="sxs-lookup"><span data-stu-id="b6828-125">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b6828-126">HTTP:ブラウザー SameSite の変更による認証への影響</span><span class="sxs-lookup"><span data-stu-id="b6828-126">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="b6828-127">HTTP:DefaultHttpContext の機能拡張の削除</span><span class="sxs-lookup"><span data-stu-id="b6828-127">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="b6828-128">HTTP:HeaderNames フィールドを静的読み取り専用に変更</span><span class="sxs-lookup"><span data-stu-id="b6828-128">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="b6828-129">HTTP:IHttpClientFactory ログの整数状態コードによって作成された HttpClient インスタンス</span><span class="sxs-lookup"><span data-stu-id="b6828-129">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="b6828-130">HTTP:応答本文のインフラストラクチャの変更</span><span class="sxs-lookup"><span data-stu-id="b6828-130">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="b6828-131">HTTP:一部の cookie SameSite の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="b6828-131">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="b6828-132">HTTP:同期 IO を既定で無効化</span><span class="sxs-lookup"><span data-stu-id="b6828-132">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="b6828-133">ID:AddDefaultUI メソッド オーバーロードの削除</span><span class="sxs-lookup"><span data-stu-id="b6828-133">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="b6828-134">ID:UI ブートストラップ バージョンの変更</span><span class="sxs-lookup"><span data-stu-id="b6828-134">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="b6828-135">ID:SignInAsync が認証されていない ID に対して例外をスロー</span><span class="sxs-lookup"><span data-stu-id="b6828-135">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="b6828-136">ID:SignInManager コンストラクターで新しいパラメーターの受け入れ</span><span class="sxs-lookup"><span data-stu-id="b6828-136">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="b6828-137">ID:UI で静的な Web 資産機能を使用</span><span class="sxs-lookup"><span data-stu-id="b6828-137">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="b6828-138">Kestrel:実行時に構成変更が既定で検出される</span><span class="sxs-lookup"><span data-stu-id="b6828-138">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="b6828-139">Kestrel:接続アダプターを削除</span><span class="sxs-lookup"><span data-stu-id="b6828-139">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="b6828-140">Kestrel:既定でサポートされている TLS プロトコル バージョンの変更</span><span class="sxs-lookup"><span data-stu-id="b6828-140">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="b6828-141">Kestrel:空の HTTPS アセンブリを削除</span><span class="sxs-lookup"><span data-stu-id="b6828-141">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="b6828-142">Kestrel:要求トレーラー ヘッダーを新しいコレクションに移動</span><span class="sxs-lookup"><span data-stu-id="b6828-142">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="b6828-143">Kestrel:トランスポート抽象化レイヤーの変更</span><span class="sxs-lookup"><span data-stu-id="b6828-143">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="b6828-144">ローカリゼーション:API を古いとしてマーク</span><span class="sxs-lookup"><span data-stu-id="b6828-144">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="b6828-145">ローカリゼーション:"Pubternal" API の削除</span><span class="sxs-lookup"><span data-stu-id="b6828-145">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="b6828-146">ローカリゼーション:ResourceManagerWithCultureStringLocalizer クラスと WithCulture インターフェイス メンバーを削除</span><span class="sxs-lookup"><span data-stu-id="b6828-146">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="b6828-147">ログ:internal になった DebugLogger クラス</span><span class="sxs-lookup"><span data-stu-id="b6828-147">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="b6828-148">MVC:コントローラー アクション Async サフィックスを削除</span><span class="sxs-lookup"><span data-stu-id="b6828-148">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="b6828-149">MVC:JsonResult を Microsoft.AspNetCore.Mvc.Core に移動</span><span class="sxs-lookup"><span data-stu-id="b6828-149">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="b6828-150">MVC:プリコンパイル ツールを非推奨</span><span class="sxs-lookup"><span data-stu-id="b6828-150">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="b6828-151">MVC:型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="b6828-151">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b6828-152">MVC:Web API 互換性 shim を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-152">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="b6828-153">Razor:実行時コンパイルをパッケージに移動</span><span class="sxs-lookup"><span data-stu-id="b6828-153">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="b6828-154">セッション状態:古い API を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-154">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="b6828-155">共有フレームワーク:Microsoft.AspNetCore.App からアセンブリの削除</span><span class="sxs-lookup"><span data-stu-id="b6828-155">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="b6828-156">共有フレームワーク:Microsoft.AspNetCore.All を削除</span><span class="sxs-lookup"><span data-stu-id="b6828-156">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="b6828-157">SignalR:HandshakeProtocol.SuccessHandshakeData を置き換え</span><span class="sxs-lookup"><span data-stu-id="b6828-157">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="b6828-158">SignalR:HubConnection メソッドを削除</span><span class="sxs-lookup"><span data-stu-id="b6828-158">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="b6828-159">SignalR:HubConnectionContext コンストラクターを変更</span><span class="sxs-lookup"><span data-stu-id="b6828-159">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="b6828-160">SignalR:JavaScript クライアント パッケージ名を変更</span><span class="sxs-lookup"><span data-stu-id="b6828-160">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="b6828-161">SignalR:MessagePack ハブ プロトコルが MessagePack 2.x パッケージに移動された</span><span class="sxs-lookup"><span data-stu-id="b6828-161">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="b6828-162">SignalR:MessagePack ハブ プロトコル オプションの種類を変更</span><span class="sxs-lookup"><span data-stu-id="b6828-162">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="b6828-163">SignalR:古い API</span><span class="sxs-lookup"><span data-stu-id="b6828-163">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="b6828-164">SignalR:UseSignalR メソッドと UseConnections メソッドが削除された</span><span class="sxs-lookup"><span data-stu-id="b6828-164">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="b6828-165">SPA:SpaServices および NodeServices コンソール ロガー フォールバックの既定値を変更</span><span class="sxs-lookup"><span data-stu-id="b6828-165">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="b6828-166">SPA:SpaServices および NodeServices を古いとしてマーク</span><span class="sxs-lookup"><span data-stu-id="b6828-166">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="b6828-167">静的ファイル: CSV コンテンツ タイプが標準準拠に変更されました</span><span class="sxs-lookup"><span data-stu-id="b6828-167">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="b6828-168">ターゲット フレームワーク: .NET Framework がサポートされない</span><span class="sxs-lookup"><span data-stu-id="b6828-168">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="b6828-169">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="b6828-169">ASP.NET Core 5.0</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="b6828-170">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b6828-170">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="b6828-171">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b6828-171">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
