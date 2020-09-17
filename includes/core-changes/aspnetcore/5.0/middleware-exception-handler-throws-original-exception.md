---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022969"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="8194f-101">ミドルウェア:ハンドラーが見つからない場合、例外ハンドラー ミドルウェアから元の例外がスローされる</span><span class="sxs-lookup"><span data-stu-id="8194f-101">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="8194f-102">ASP.NET Core 5.0 より前では、例外が発生したときに、[Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) によって構成済みの例外ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-102">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="8194f-103"><xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> で構成された例外ハンドラーが見つからない場合は、HTTP 404 応答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-103">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="8194f-104">この応答は、次のような誤解を招きます。</span><span class="sxs-lookup"><span data-stu-id="8194f-104">The response is misleading in that it:</span></span>

* <span data-ttu-id="8194f-105">ユーザー エラーのように見える。</span><span class="sxs-lookup"><span data-stu-id="8194f-105">Seems to be a user error.</span></span>
* <span data-ttu-id="8194f-106">サーバーで例外が発生したという事実がわからなくなる。</span><span class="sxs-lookup"><span data-stu-id="8194f-106">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="8194f-107">ASP.NET Core 5.0 のこの誤解を招くエラーに対処するために、例外ハンドラーが見つからない場合、`ExceptionHandlerMiddleware` からは元の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8194f-107">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="8194f-108">その結果、サーバーによって HTTP 500 応答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-108">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="8194f-109">この応答であれば、発生したエラーをデバッグするときにサーバー ログで簡単に調べることができます。</span><span class="sxs-lookup"><span data-stu-id="8194f-109">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="8194f-110">ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8194f-110">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8194f-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="8194f-111">Version introduced</span></span>

<span data-ttu-id="8194f-112">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="8194f-112">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8194f-113">以前の動作</span><span class="sxs-lookup"><span data-stu-id="8194f-113">Old behavior</span></span>

<span data-ttu-id="8194f-114">構成された例外ハンドラーが見つからない場合は、Exception Handler Middleware によって HTTP 404 応答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-114">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8194f-115">新しい動作</span><span class="sxs-lookup"><span data-stu-id="8194f-115">New behavior</span></span>

<span data-ttu-id="8194f-116">構成された例外ハンドラーが見つからない場合は、Exception Handler Middleware からは元の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8194f-116">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8194f-117">変更理由</span><span class="sxs-lookup"><span data-stu-id="8194f-117">Reason for change</span></span>

<span data-ttu-id="8194f-118">HTTP 404 エラーを受け取っても、サーバーで例外が発生したことが明らかにはなりません。</span><span class="sxs-lookup"><span data-stu-id="8194f-118">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="8194f-119">この変更により、HTTP 500 エラーが生成され、次のことが明らかになります。</span><span class="sxs-lookup"><span data-stu-id="8194f-119">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="8194f-120">問題の原因はユーザー エラーではない。</span><span class="sxs-lookup"><span data-stu-id="8194f-120">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="8194f-121">サーバー上で例外が発生した。</span><span class="sxs-lookup"><span data-stu-id="8194f-121">An exception was encountered on the server.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8194f-122">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="8194f-122">Recommended action</span></span>

<span data-ttu-id="8194f-123">API の変更はありません。</span><span class="sxs-lookup"><span data-stu-id="8194f-123">There are no API changes.</span></span> <span data-ttu-id="8194f-124">既存のすべてのアプリは引き続きコンパイルされ、実行されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-124">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="8194f-125">スローされた例外は、サーバーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-125">The exception thrown is handled by the server.</span></span> <span data-ttu-id="8194f-126">たとえば、例外は [Kestrel](/aspnet/core/fundamentals/servers/kestrel) または [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) によって HTTP 500 エラー応答に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8194f-126">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

#### <a name="category"></a><span data-ttu-id="8194f-127">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="8194f-127">Category</span></span>

<span data-ttu-id="8194f-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8194f-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8194f-129">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8194f-129">Affected APIs</span></span>

<span data-ttu-id="8194f-130">なし</span><span class="sxs-lookup"><span data-stu-id="8194f-130">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
