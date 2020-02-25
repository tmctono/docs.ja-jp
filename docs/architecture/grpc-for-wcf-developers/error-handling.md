---
title: エラー処理-WCF 開発者向け gRPC
description: GRPC でのエラー処理に関するトピック。 最も一般的に使用されるステータスコードの表が含まれています。
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542794"
---
# <a name="error-handling"></a><span data-ttu-id="ebee6-104">エラー処理</span><span class="sxs-lookup"><span data-stu-id="ebee6-104">Error handling</span></span>

<span data-ttu-id="ebee6-105">Windows Communication Foundation (WCF) は <xref:System.ServiceModel.FaultException%601> と[Faultcontract](xref:System.ServiceModel.FaultContractAttribute)を使用して、SOAP Fault standard のサポートなど、詳細なエラー情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ebee6-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="ebee6-106">残念ながら、現在のバージョンの gRPC には、WCF での洗練された機能がありません。単純なステータスコードとメタデータに基づいて組み込まれたエラー処理は限られています。</span><span class="sxs-lookup"><span data-stu-id="ebee6-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="ebee6-107">次の表に、最も一般的に使用されるステータスコードの簡単なガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="ebee6-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="ebee6-108">status code</span><span class="sxs-lookup"><span data-stu-id="ebee6-108">Status code</span></span> | <span data-ttu-id="ebee6-109">問題</span><span class="sxs-lookup"><span data-stu-id="ebee6-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="ebee6-110">メソッドが書き込まれていません。</span><span class="sxs-lookup"><span data-stu-id="ebee6-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="ebee6-111">サービス全体に問題があります。</span><span class="sxs-lookup"><span data-stu-id="ebee6-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="ebee6-112">無効な応答です。</span><span class="sxs-lookup"><span data-stu-id="ebee6-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="ebee6-113">エンコード/デコードに問題があります。</span><span class="sxs-lookup"><span data-stu-id="ebee6-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="ebee6-114">認証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ebee6-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="ebee6-115">承認に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ebee6-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="ebee6-116">呼び出しはキャンセルされました。通常は呼び出し元によって行われます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="ebee6-117">ASP.NET Core gRPC でエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ebee6-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="ebee6-118">ASP.NET Core gRPC サービスは、`RpcException`をスローすることによってエラー応答を送信することができます。これは、同じプロセスにあるかのようにクライアントからキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="ebee6-119">`RpcException` には、状態コードと説明を含める必要があります。また、必要に応じて、メタデータと長い例外メッセージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="ebee6-120">メタデータを使用して、サポートデータを送信することができます。これは、`FaultContract` オブジェクトが WCF エラーに対して追加データを伝達する方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="ebee6-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="ebee6-121">GRPC クライアントでエラーをキャッチする</span><span class="sxs-lookup"><span data-stu-id="ebee6-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="ebee6-122">WCF クライアントが <xref:System.ServiceModel.FaultException%601> エラーをキャッチできるのと同様に、gRPC クライアントは、エラーを処理するための `RpcException` をキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="ebee6-123">`RpcException` はジェネリック型ではないため、異なるブロックでさまざまなエラーの種類をキャッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ebee6-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="ebee6-124">ただし、次のC#例に示すように、の*例外フィルター*機能を使用して、状態コードごとに個別の `catch` ブロックを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="ebee6-125">エラーのために追加のメタデータを指定する場合は、API のドキュメント、または `.proto` ファイルのコメントで、関連するキーと値を必ず文書化してください。</span><span class="sxs-lookup"><span data-stu-id="ebee6-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="ebee6-126">gRPC の豊富なエラーモデル</span><span class="sxs-lookup"><span data-stu-id="ebee6-126">gRPC richer error model</span></span>

<span data-ttu-id="ebee6-127">Google は、WCF の[Faultcontract](xref:System.ServiceModel.FaultContractAttribute)のようなより[豊富なエラーモデル](https://cloud.google.com/apis/design/errors#error_model)を開発しましたが、 C#このモデルはまだではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ebee6-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="ebee6-128">現在、このファイルは、ゴー、Java、Python、およびC++でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebee6-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ebee6-129">[前へ](metadata.md)
>[次へ](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="ebee6-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
