---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394374"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="b8a7b-101">Kestrel: 要求トレーラー ヘッダーを新しいコレクションに移動</span><span class="sxs-lookup"><span data-stu-id="b8a7b-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="b8a7b-102">以前のバージョンでは、要求本文が最後まで読み取られると、Kestrel によって HTTP/1.1 チャンク トレーラー ヘッダーが要求ヘッダー コレクションに追加されていました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="b8a7b-103">この動作により、ヘッダーとトレーラー間のあいまいさに関する懸念が生じていました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="b8a7b-104">トレーラーを新しいコレクションに移動することが決定されました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="b8a7b-105">HTTP/2 要求トレーラーは ASP.NET Core 2.2 では使用できませんでしたが、ASP.NET Core 3.0 ではこの新しいコレクションでも使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="b8a7b-106">これらのトレーラーにアクセスするために、新しい要求拡張メソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="b8a7b-107">HTTP/1.1 トレーラーは、要求本文全体が読み取られると利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="b8a7b-108">HTTP/2 トレーラーは、クライアントから受信すると利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="b8a7b-109">クライアントは、要求本文全体がサーバーによって少なくともバッファーされるまで、トレーラーを送信しません。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="b8a7b-110">バッファー領域を解放するために、要求本文を読み取ることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="b8a7b-111">要求本文を最後まで読み取ると、トレーラーをいつでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="b8a7b-112">トレーラーは本文の終わりをマークします。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b8a7b-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8a7b-113">Version introduced</span></span>

<span data-ttu-id="b8a7b-114">3.0</span><span class="sxs-lookup"><span data-stu-id="b8a7b-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b8a7b-115">以前の動作</span><span class="sxs-lookup"><span data-stu-id="b8a7b-115">Old behavior</span></span>

<span data-ttu-id="b8a7b-116">要求トレーラー ヘッダーは、`HttpRequest.Headers` コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b8a7b-117">新しい動作</span><span class="sxs-lookup"><span data-stu-id="b8a7b-117">New behavior</span></span>

<span data-ttu-id="b8a7b-118">要求トレーラー ヘッダーは、`HttpRequest.Headers` コレクションには**存在しません**。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="b8a7b-119">トレーラー ヘッダーにアクセスするには、`HttpRequest` で次の拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="b8a7b-120">`GetDeclaredTrailers()` - 本文の後に予想されるトレーラーを示す、要求の "Trailer" ヘッダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="b8a7b-121">`SupportsTrailers()` - 要求でトレーラー ヘッダーの受信がサポートされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="b8a7b-122">`CheckTrailersAvailable()` - 要求でトレーラーがサポートされているかどうかと、それらを読み取りに使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="b8a7b-123">`GetTrailer(string trailerName)` - 要求された末尾のヘッダーを応答から取得します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b8a7b-124">変更理由</span><span class="sxs-lookup"><span data-stu-id="b8a7b-124">Reason for change</span></span>

<span data-ttu-id="b8a7b-125">トレーラーは、gRPC などのシナリオにおける重要な機能です。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="b8a7b-126">要求ヘッダーへのトレーラーのマージは、ユーザーの混乱を招いていました。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b8a7b-127">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="b8a7b-127">Recommended action</span></span>

<span data-ttu-id="b8a7b-128">トレーラーにアクセスするには、`HttpRequest` でトレーラー関連の拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a7b-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="b8a7b-129">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b8a7b-129">Category</span></span>

<span data-ttu-id="b8a7b-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b8a7b-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b8a7b-131">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b8a7b-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
