---
title: ASP.NET Core の破壊的変更
titleSuffix: ''
description: ASP.NET Core における破壊的変更をリストアップします。
ms.date: 09/18/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: a4534367184127604ed53bf1fdafabbf8ff575d1
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406194"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="70c9b-103">ASP.NET Core の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="70c9b-104">ASP.NET Core からは、.NET Core で使用される Web アプリ開発機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="70c9b-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="70c9b-105">特定のバージョンの破壊的変更については、次のリンクのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="70c9b-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="70c9b-106">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="70c9b-106">ASP.NET Core 5.0</span></span>](#aspnet-core-50)
* [<span data-ttu-id="70c9b-107">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="70c9b-107">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="70c9b-108">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="70c9b-108">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="70c9b-109">ASP.NET Core 3.0、3.1、5.0 の次の破壊的変更はこのページに記録されています。</span><span class="sxs-lookup"><span data-stu-id="70c9b-109">The following breaking changes in ASP.NET Core 3.0, 3.1, and 5.0 are documented on this page:</span></span>

- [<span data-ttu-id="70c9b-110">Antiforgery、CORS、Diagnostics、MVC、Routing の古い API の削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-110">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="70c9b-111">認証:AzureAD.UI および AzureADB2C.UI の API とパッケージが非推奨としてマークされる</span><span class="sxs-lookup"><span data-stu-id="70c9b-111">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>](#authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete)
- [<span data-ttu-id="70c9b-112">認証:Google+ の非推奨</span><span class="sxs-lookup"><span data-stu-id="70c9b-112">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="70c9b-113">認証:HttpContext.Authentication プロパティの削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-113">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="70c9b-114">認証:Newtonsoft.Json 型の置き換え</span><span class="sxs-lookup"><span data-stu-id="70c9b-114">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="70c9b-115">認証:OAuthHandler ExchangeCodeAsync 署名の変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-115">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="70c9b-116">承認:AddAuthorization のオーバーロードを別のアセンブリに移動</span><span class="sxs-lookup"><span data-stu-id="70c9b-116">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="70c9b-117">承認:AuthorizationFilterContext.Filters から IAllowAnonymous を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-117">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="70c9b-118">承認:IAuthorizationPolicyProvider の実装に新しいメソッドが必要</span><span class="sxs-lookup"><span data-stu-id="70c9b-118">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="70c9b-119">承認:エンドポイント ルーティングのリソースは HttpContext</span><span class="sxs-lookup"><span data-stu-id="70c9b-119">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="70c9b-120">Azure:Microsoft というプレフィックスが付いた Azure 統合パッケージが削除された</span><span class="sxs-lookup"><span data-stu-id="70c9b-120">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="70c9b-121">BinaryFormatter シリアル化メソッドが古い形式になり、ASP.NET アプリでは使用不可に</span><span class="sxs-lookup"><span data-stu-id="70c9b-121">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [<span data-ttu-id="70c9b-122">Blazor:コンパイル時にコンポーネントからトリミングされる無意味な空白文字</span><span class="sxs-lookup"><span data-stu-id="70c9b-122">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="70c9b-123">Blazor:JSObjectReference および JSInProcessObjectReference 型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-123">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>](#blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal)
- [<span data-ttu-id="70c9b-124">Blazor:ProtectedBrowserStorage 機能を共有フレームワークに移行</span><span class="sxs-lookup"><span data-stu-id="70c9b-124">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>](#blazor-protectedbrowserstorage-feature-moved-to-shared-framework)
- [<span data-ttu-id="70c9b-125">Blazor:RenderTreeFrame の readonly のパブリック フィールドのプロパティ化</span><span class="sxs-lookup"><span data-stu-id="70c9b-125">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>](#blazor-rendertreeframe-readonly-public-fields-have-become-properties)
- [<span data-ttu-id="70c9b-126">Blazor:NuGet パッケージのターゲット フレームワークを変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-126">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="70c9b-127">キャッシュ:CompactOnMemoryPressure プロパティの削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-127">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="70c9b-128">キャッシュ:Microsoft.Extensions.Caching.SqlServer で新しい SqlClient パッケージを使用</span><span class="sxs-lookup"><span data-stu-id="70c9b-128">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="70c9b-129">キャッシュ:ResponseCaching の "pubternal" 型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-129">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="70c9b-130">データ保護:DataProtection.AzureStorage で新しい Azure Storage API を使用</span><span class="sxs-lookup"><span data-stu-id="70c9b-130">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="70c9b-131"> 拡張機能:一部の NuGet パッケージに影響するパッケージ参照の変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-131">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="70c9b-132">ホスティング:Windows ホスティング バンドルから AspNetCoreModule V1 を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-132">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="70c9b-133">ホスティング:汎用ホストによる Startup コンストラクター挿入の制限</span><span class="sxs-lookup"><span data-stu-id="70c9b-133">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="70c9b-134">ホスティング:IIS アウトプロセス アプリ用に HTTPS リダイレクトを有効化</span><span class="sxs-lookup"><span data-stu-id="70c9b-134">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="70c9b-135">ホスティング:IHostingEnvironment と IApplicationLifetime の型を置き換え</span><span class="sxs-lookup"><span data-stu-id="70c9b-135">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="70c9b-136">ホスティング:WebHostBuilder 依存関係から ObjectPoolProvider を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-136">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="70c9b-137">HTTP:Kestrel および IIS BadHttpRequestException の種類を古い形式としてマークし、置換</span><span class="sxs-lookup"><span data-stu-id="70c9b-137">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="70c9b-138">HTTP:ブラウザー SameSite の変更による認証への影響</span><span class="sxs-lookup"><span data-stu-id="70c9b-138">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="70c9b-139">HTTP:DefaultHttpContext の機能拡張の削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-139">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="70c9b-140">HTTP:HeaderNames フィールドを静的読み取り専用に変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-140">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="70c9b-141">HTTP:IHttpClientFactory ログの整数状態コードによって作成された HttpClient インスタンス</span><span class="sxs-lookup"><span data-stu-id="70c9b-141">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="70c9b-142">HTTP:応答本文のインフラストラクチャの変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-142">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="70c9b-143">HTTP:一部の cookie SameSite の既定値の変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-143">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="70c9b-144">HTTP:同期 IO を既定で無効化</span><span class="sxs-lookup"><span data-stu-id="70c9b-144">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="70c9b-145">HttpSys:既定で無効になっているクライアント証明書の再ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="70c9b-145">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="70c9b-146">ID:AddDefaultUI メソッド オーバーロードの削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-146">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="70c9b-147">ID:UI ブートストラップ バージョンの変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-147">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="70c9b-148">ID:SignInAsync が認証されていない ID に対して例外をスロー</span><span class="sxs-lookup"><span data-stu-id="70c9b-148">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="70c9b-149">ID:SignInManager コンストラクターで新しいパラメーターの受け入れ</span><span class="sxs-lookup"><span data-stu-id="70c9b-149">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="70c9b-150">ID:UI で静的な Web 資産機能を使用</span><span class="sxs-lookup"><span data-stu-id="70c9b-150">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="70c9b-151">IIS:UrlRewrite ミドルウェア クエリ文字列は保持されます</span><span class="sxs-lookup"><span data-stu-id="70c9b-151">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="70c9b-152">Kestrel:実行時に構成変更が既定で検出される</span><span class="sxs-lookup"><span data-stu-id="70c9b-152">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="70c9b-153">Kestrel:接続アダプターを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-153">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="70c9b-154">Kestrel:既定でサポートされている TLS プロトコル バージョンの変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-154">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="70c9b-155">Kestrel:空の HTTPS アセンブリを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-155">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="70c9b-156">Kestrel:互換性のない Windows バージョンでの TLS 経由の HTTP/2 の無効化</span><span class="sxs-lookup"><span data-stu-id="70c9b-156">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="70c9b-157">Kestrel:非推奨としてマークされている Libuv トランスポート</span><span class="sxs-lookup"><span data-stu-id="70c9b-157">Kestrel: Libuv transport marked as obsolete</span></span>](#kestrel-libuv-transport-marked-as-obsolete)
- [<span data-ttu-id="70c9b-158">Kestrel:要求トレーラー ヘッダーを新しいコレクションに移動</span><span class="sxs-lookup"><span data-stu-id="70c9b-158">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="70c9b-159">Kestrel:トランスポート抽象化レイヤーの変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-159">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="70c9b-160">ローカリゼーション:API を古いとしてマーク</span><span class="sxs-lookup"><span data-stu-id="70c9b-160">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="70c9b-161">ローカリゼーション:"Pubternal" API の削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-161">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="70c9b-162">ローカリゼーション:ローカライズ ミドルウェア要求で古いコンストラクターを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-162">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="70c9b-163">ローカリゼーション:ResourceManagerWithCultureStringLocalizer クラスと WithCulture インターフェイス メンバーを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-163">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="70c9b-164">ログ:internal になった DebugLogger クラス</span><span class="sxs-lookup"><span data-stu-id="70c9b-164">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="70c9b-165">ミドルウェア:非推奨とマークされたデータベース エラー ページ</span><span class="sxs-lookup"><span data-stu-id="70c9b-165">Middleware: Database error page marked as obsolete</span></span>](#middleware-database-error-page-marked-as-obsolete)
- [<span data-ttu-id="70c9b-166">ミドルウェア:ハンドラーが見つからない場合、例外ハンドラー ミドルウェアから元の例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="70c9b-166">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [<span data-ttu-id="70c9b-167">MVC:コントローラー アクション Async サフィックスを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-167">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="70c9b-168">MVC:JsonResult を Microsoft.AspNetCore.Mvc.Core に移動</span><span class="sxs-lookup"><span data-stu-id="70c9b-168">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="70c9b-169">MVC:プリコンパイル ツールを非推奨</span><span class="sxs-lookup"><span data-stu-id="70c9b-169">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="70c9b-170">MVC:型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-170">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="70c9b-171">MVC:Web API 互換性 shim を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-171">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="70c9b-172">Razor:RazorTemplateEngine API が削除されました</span><span class="sxs-lookup"><span data-stu-id="70c9b-172">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="70c9b-173">Razor:実行時コンパイルをパッケージに移動</span><span class="sxs-lookup"><span data-stu-id="70c9b-173">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="70c9b-174">セキュリティ:Cookie 名のエンコードを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-174">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="70c9b-175">セキュリティ:IdentityModel NuGet パッケージのバージョンを更新</span><span class="sxs-lookup"><span data-stu-id="70c9b-175">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="70c9b-176">セッション状態:古い API を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-176">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="70c9b-177">共有フレームワーク:Microsoft.AspNetCore.App からアセンブリの削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-177">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="70c9b-178">共有フレームワーク:Microsoft.AspNetCore.All を削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-178">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="70c9b-179">SignalR:HandshakeProtocol.SuccessHandshakeData を置き換え</span><span class="sxs-lookup"><span data-stu-id="70c9b-179">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="70c9b-180">SignalR:HubConnection メソッドを削除</span><span class="sxs-lookup"><span data-stu-id="70c9b-180">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="70c9b-181">SignalR:HubConnectionContext コンストラクターを変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-181">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="70c9b-182">SignalR:JavaScript クライアント パッケージ名を変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-182">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="70c9b-183">SignalR:MessagePack ハブ プロトコルが MessagePack 2.x パッケージに移動された</span><span class="sxs-lookup"><span data-stu-id="70c9b-183">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="70c9b-184">SignalR:MessagePack ハブ プロトコル オプションの種類を変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-184">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="70c9b-185">SignalR:古い API</span><span class="sxs-lookup"><span data-stu-id="70c9b-185">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="70c9b-186">SignalR:UseSignalR メソッドと UseConnections メソッドが削除された</span><span class="sxs-lookup"><span data-stu-id="70c9b-186">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="70c9b-187">SPA:SpaServices および NodeServices コンソール ロガー フォールバックの既定値を変更</span><span class="sxs-lookup"><span data-stu-id="70c9b-187">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="70c9b-188">SPA:SpaServices および NodeServices を古いとしてマーク</span><span class="sxs-lookup"><span data-stu-id="70c9b-188">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="70c9b-189">静的ファイル: CSV コンテンツ タイプが標準準拠に変更されました</span><span class="sxs-lookup"><span data-stu-id="70c9b-189">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="70c9b-190">Blazor WebAssembly で System.Security.Cryptography API がサポートされない</span><span class="sxs-lookup"><span data-stu-id="70c9b-190">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly)
- [<span data-ttu-id="70c9b-191">ターゲット フレームワーク: .NET Framework がサポートされない</span><span class="sxs-lookup"><span data-stu-id="70c9b-191">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="70c9b-192">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="70c9b-192">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete](~/includes/core-changes/aspnetcore/5.0/authentication-aad-packages-obsolete.md)]

***

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

***

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

***

[!INCLUDE[Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal](~/includes/core-changes/aspnetcore/5.0/blazor-jsobjectreference-to-internal.md)]

***

[!INCLUDE[Blazor: ProtectedBrowserStorage feature moved to shared framework](~/includes/core-changes/aspnetcore/5.0/blazor-protectedbrowserstorage-moved.md)]

***

[!INCLUDE[Blazor: RenderTreeFrame readonly public fields have become properties](~/includes/core-changes/aspnetcore/5.0/blazor-rendertreeframe-fields-become-properties.md)]

***

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

***

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

***

[!INCLUDE[Kestrel: Libuv transport marked as obsolete](~/includes/core-changes/aspnetcore/5.0/kestrel-libuv-transport-obsolete.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[Middleware: Database error page marked as obsolete](~/includes/core-changes/aspnetcore/5.0/middleware-database-error-page-obsolete.md)]

***

[!INCLUDE[Middleware: Exception Handler Middleware throws original exception if handler not found](~/includes/core-changes/aspnetcore/5.0/middleware-exception-handler-throws-original-exception.md)]

***

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

***

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="70c9b-193">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="70c9b-193">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="70c9b-194">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="70c9b-194">ASP.NET Core 3.0</span></span>

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

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

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
