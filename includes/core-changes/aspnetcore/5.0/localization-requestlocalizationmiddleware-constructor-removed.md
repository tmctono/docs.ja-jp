---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309155"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="4f5c2-101">ローカリゼーション:ローカライズ ミドルウェア要求で古いコンストラクターを削除</span><span class="sxs-lookup"><span data-stu-id="4f5c2-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="4f5c2-102"><xref:Microsoft.Extensions.Logging.ILoggerFactory> パラメーターのない <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> コンストラクターは[このコミットで](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0)非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="4f5c2-103">ASP.NET Core 5.0 では、非推奨コンストラクターが削除されました。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="4f5c2-104">ディスカッションについては、[dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4f5c2-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="4f5c2-105">Version introduced</span></span>

<span data-ttu-id="4f5c2-106">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="4f5c2-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4f5c2-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="4f5c2-107">Old behavior</span></span>

<span data-ttu-id="4f5c2-108">非推奨 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` コンストラクターが存在します。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4f5c2-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="4f5c2-109">New behavior</span></span>

<span data-ttu-id="4f5c2-110">非推奨 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` コンストラクターが存在しません。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4f5c2-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="4f5c2-111">Reason for change</span></span>

<span data-ttu-id="4f5c2-112">この変更により、ローカライズ ミドルウェア要求で常にロガーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4f5c2-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="4f5c2-113">Recommended action</span></span>

<span data-ttu-id="4f5c2-114">`RequestLocalizationMiddleware` のインスタンスを手動で構築するとき、コンストラクターで `ILoggerFactory` インスタンスを渡します。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="4f5c2-115">そのコンテキストで有効な `ILoggerFactory` インスタンスが利用できない場合、ミドルウェア コンストラクターに <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> インスタンスを渡すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4f5c2-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="4f5c2-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4f5c2-116">Category</span></span>

<span data-ttu-id="4f5c2-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4f5c2-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4f5c2-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4f5c2-118">Affected APIs</span></span>

[<span data-ttu-id="4f5c2-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="4f5c2-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
