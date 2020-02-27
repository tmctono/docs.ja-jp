---
title: WCF 開発者向けのメタデータ-gRPC
description: GRPC でメタデータを使用して、クライアントとサーバーの間に追加のコンテキストを渡す方法。
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628580"
---
# <a name="metadata"></a><span data-ttu-id="d3cb6-103">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d3cb6-103">Metadata</span></span>

<span data-ttu-id="d3cb6-104">*メタデータ*とは、要求と応答の処理中に役立つ可能性のある追加データを指しますが、実際のアプリケーションデータには含まれません。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="d3cb6-105">メタデータには、認証トークン、監視用の要求 id とタグ、データセット内のレコードの数などのデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="d3cb6-106"><xref:System.ServiceModel.OperationContextScope> と <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> プロパティを使用して Windows Communication Foundation (WCF) メッセージに汎用キー/値ヘッダーを追加し、<xref:System.ServiceModel.Channels.MessageProperties>を使用して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="d3cb6-107">gRPC の呼び出しと応答には、HTTP ヘッダーに似たメタデータを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="d3cb6-108">このメタデータは、ほとんどの場合 gRPC 自体には見えず、アプリケーションコードまたはミドルウェアによって処理されるために渡されます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="d3cb6-109">メタデータは、キーと値のペアとして表されます。キーは文字列で、値は文字列またはバイナリデータのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="d3cb6-110">`.proto` ファイルでメタデータを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="d3cb6-111">メタデータは、 [Grpc. Core. Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet パッケージの `Metadata` クラスによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="d3cb6-112">このクラスは、コレクション初期化子構文と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="d3cb6-113">この例でC#は、クライアントからの呼び出しにメタデータを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-113">This example shows how to add metadata to a call from a C# client:</span></span>

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

<span data-ttu-id="d3cb6-114">gRPC サービスは、`ServerCallContext` 引数の `RequestHeaders` プロパティからメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

<span data-ttu-id="d3cb6-115">サービスは、`ServerCallContext`の `ResponseTrailers` プロパティを使用して、クライアントにメタデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d3cb6-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="d3cb6-116">[前へ](rpc-types.md)
>[次へ](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="d3cb6-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
