---
title: エラー処理-WCF 開発者向け gRPC
description: 記述予定
ms.date: 09/02/2019
ms.openlocfilehash: 2c44bd9264c877a7c7a86c115b6da9f759006016
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967793"
---
# <a name="error-handling"></a><span data-ttu-id="638ce-103">エラー処理</span><span class="sxs-lookup"><span data-stu-id="638ce-103">Error handling</span></span>

<span data-ttu-id="638ce-104">WCF は `FaultException<T>` と `FaultContract` を使用して、SOAP Fault standard のサポートなど、詳細なエラー情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="638ce-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="638ce-105">残念ながら、現在のバージョンの gRPC では、WCF での洗練された機能が不足しており、単純なステータスコードとメタデータに基づいて組み込まれたエラー処理は限られています。</span><span class="sxs-lookup"><span data-stu-id="638ce-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="638ce-106">次の表に、最も一般的に使用されるステータスコードの簡単なガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="638ce-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="638ce-107">状態コード</span><span class="sxs-lookup"><span data-stu-id="638ce-107">Status Code</span></span> | <span data-ttu-id="638ce-108">Problem</span><span class="sxs-lookup"><span data-stu-id="638ce-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="638ce-109">メソッドが書き込まれていません。</span><span class="sxs-lookup"><span data-stu-id="638ce-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="638ce-110">サービス全体に問題があります。</span><span class="sxs-lookup"><span data-stu-id="638ce-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="638ce-111">無効な応答です。</span><span class="sxs-lookup"><span data-stu-id="638ce-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="638ce-112">エンコード/デコードに問題があります。</span><span class="sxs-lookup"><span data-stu-id="638ce-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="638ce-113">認証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="638ce-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="638ce-114">承認に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="638ce-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="638ce-115">呼び出しはキャンセルされました。通常は呼び出し元によって行われます。</span><span class="sxs-lookup"><span data-stu-id="638ce-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="638ce-116">ASP.NET Core gRPC でエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="638ce-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="638ce-117">ASP.NET Core gRPC サービスは、`RpcException`をスローすることによってエラー応答を送信することができます。これは、同じプロセスにあるかのようにクライアントからキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="638ce-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="638ce-118">`RpcException` には、状態コードと説明を含める必要があります。また、必要に応じて、メタデータと長い例外メッセージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="638ce-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="638ce-119">メタデータを使用して、サポートデータを送信することができます。これは、`FaultContract` オブジェクトが WCF エラーに対して追加データを伝達する方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="638ce-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="638ce-120">GRPC クライアントでのエラーのキャッチ</span><span class="sxs-lookup"><span data-stu-id="638ce-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="638ce-121">WCF クライアントが <xref:System.ServiceModel.FaultException%601> エラーをキャッチできるのと同様に、gRPC クライアントは、エラーを処理するための `RpcException` をキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="638ce-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="638ce-122">`RpcException` はジェネリック型ではないため、異なるブロックでさまざまなエラーの種類をキャッチすることC#はできませんが、次の例に示すように、の*例外フィルター*機能を使用して、さまざまな状態コードに対して個別の `catch` ブロックを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="638ce-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="638ce-123">エラーのために追加のメタデータを指定する場合は、API のドキュメント、または `.proto` ファイルのコメントで、関連するキーと値を必ず文書化してください。</span><span class="sxs-lookup"><span data-stu-id="638ce-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="638ce-124">gRPC の豊富なエラーモデル</span><span class="sxs-lookup"><span data-stu-id="638ce-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="638ce-125">今後、Google は、WCF の[Faultcontract](xref:System.ServiceModel.FaultContractAttribute)のようなより[豊富なエラーモデル](https://cloud.google.com/apis/design/errors#error_model)を開発しましたがC# 、ではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="638ce-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="638ce-126">現在は、ゴー、Java、Python およびC++でのみ使用できますが、のC#サポートは来年に予定されています。</span><span class="sxs-lookup"><span data-stu-id="638ce-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="638ce-127">[前へ](metadata.md)
>[次へ](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="638ce-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
