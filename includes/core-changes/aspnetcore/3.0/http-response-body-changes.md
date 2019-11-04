---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198484"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="51f9b-101">HTTP:応答本文のインフラストラクチャの変更</span><span class="sxs-lookup"><span data-stu-id="51f9b-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="51f9b-102">HTTP 応答本文を支えるインフラストラクチャが変更されました。</span><span class="sxs-lookup"><span data-stu-id="51f9b-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="51f9b-103">`HttpResponse` を直接使用する場合は、コードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51f9b-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="51f9b-104">`HttpResponse.Body` をラップまたは置換する場合や `HttpContext.Features` にアクセスする場合は、以下をお読みください。</span><span class="sxs-lookup"><span data-stu-id="51f9b-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="51f9b-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="51f9b-105">Version introduced</span></span>

<span data-ttu-id="51f9b-106">3.0</span><span class="sxs-lookup"><span data-stu-id="51f9b-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="51f9b-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="51f9b-107">Old behavior</span></span>

<span data-ttu-id="51f9b-108">HTTP 応答本文に関連付けられた次の 3 つの API がありました。</span><span class="sxs-lookup"><span data-stu-id="51f9b-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="51f9b-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="51f9b-109">New behavior</span></span>

<span data-ttu-id="51f9b-110">`HttpResponse.Body` を置き換えると、`IHttpResponseBodyFeature` 全体が、`StreamResponseBodyFeature` を使用して予想されるすべての API の既定の実装を提供する特定のストリームのラッパーに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="51f9b-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="51f9b-111">元のストリームに戻すと、この変更が元に戻されます。</span><span class="sxs-lookup"><span data-stu-id="51f9b-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="51f9b-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="51f9b-112">Reason for change</span></span>

<span data-ttu-id="51f9b-113">目的は、応答本文の API を単一の新しい機能インターフェイスに結合することです。</span><span class="sxs-lookup"><span data-stu-id="51f9b-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="51f9b-114">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="51f9b-114">Recommended action</span></span>

<span data-ttu-id="51f9b-115">`IHttpResponseFeature.Body`、`IHttpSendFileFeature`、または `IHttpBufferingFeature` を以前に使用していた場所で `IHttpResponseBodyFeature` を使用します。</span><span class="sxs-lookup"><span data-stu-id="51f9b-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="51f9b-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="51f9b-116">Category</span></span>

<span data-ttu-id="51f9b-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="51f9b-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="51f9b-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="51f9b-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
