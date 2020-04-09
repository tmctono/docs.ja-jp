---
title: エラー処理 - WCF 開発者用 gRPC
description: gRPC でのエラー処理に関するトピック。 最も一般的に使用されるステータスコードの表が含まれています。
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988948"
---
# <a name="error-handling"></a><span data-ttu-id="c64ed-104">エラー処理</span><span class="sxs-lookup"><span data-stu-id="c64ed-104">Error handling</span></span>

<span data-ttu-id="c64ed-105">Windows 通信ファウンデーション<xref:System.ServiceModel.FaultException%601>(WCF) は、SOAP フォールト標準のサポートを含む詳細なエラー情報を提供するために使用および[FaultContract](xref:System.ServiceModel.FaultContractAttribute)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c64ed-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="c64ed-106">残念ながら、現在のバージョンの gRPC には WCF で見られる高度な機能が欠けており、単純な状態コードとメタデータに基づく組み込みのエラー処理のみが制限されています。</span><span class="sxs-lookup"><span data-stu-id="c64ed-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="c64ed-107">次の表は、最も一般的に使用されるステータスコードのクイックガイドです。</span><span class="sxs-lookup"><span data-stu-id="c64ed-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="c64ed-108">status code</span><span class="sxs-lookup"><span data-stu-id="c64ed-108">Status code</span></span> | <span data-ttu-id="c64ed-109">問題</span><span class="sxs-lookup"><span data-stu-id="c64ed-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="c64ed-110">メソッドが書かれていません。</span><span class="sxs-lookup"><span data-stu-id="c64ed-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="c64ed-111">サービス全体に問題があります。</span><span class="sxs-lookup"><span data-stu-id="c64ed-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="c64ed-112">無効な応答です。</span><span class="sxs-lookup"><span data-stu-id="c64ed-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="c64ed-113">エンコード/デコードに問題があります。</span><span class="sxs-lookup"><span data-stu-id="c64ed-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="c64ed-114">認証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c64ed-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="c64ed-115">承認に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c64ed-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="c64ed-116">呼び出しは、通常、呼び出し元によって取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c64ed-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="c64ed-117">ASP.NETコア gRPC でエラーを発生させる</span><span class="sxs-lookup"><span data-stu-id="c64ed-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="c64ed-118">ASP.NET Core gRPC サービスは`RpcException`、同じプロセスにあるかのようにクライアントがキャッチできる をスローすることでエラー応答を送信できます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="c64ed-119">には`RpcException`、ステータス コードと説明を含める必要があり、オプションでメタデータと長い例外メッセージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="c64ed-120">メタデータを使用すると、WCF エラーに対する追加データを`FaultContract`オブジェクトが伝送する方法と同様に、サポート データを送信できます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="c64ed-121">gRPC クライアントでエラーをキャッチする</span><span class="sxs-lookup"><span data-stu-id="c64ed-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="c64ed-122">WCF クライアントがエラーを<xref:System.ServiceModel.FaultException%601>キャッチできるのと同様に、gRPC`RpcException`クライアントはエラーを処理するをキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="c64ed-123">ジェネリック`RpcException`型ではないため、異なるブロックで異なるエラータイプをキャッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c64ed-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="c64ed-124">ただし、C# の*例外フィルター*機能を使用して、次`catch`の例に示すように、さまざまな状態コードに対して個別のブロックを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="c64ed-125">エラーの追加メタデータを提供する場合は、API ドキュメントまたはファイル内のコメントに関連するキーと値を必ず文書化`.proto`してください。</span><span class="sxs-lookup"><span data-stu-id="c64ed-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="c64ed-126">gRPC リッチ エラー モデル</span><span class="sxs-lookup"><span data-stu-id="c64ed-126">gRPC richer error model</span></span>

<span data-ttu-id="c64ed-127">Google は WCF の[FaultContract](xref:System.ServiceModel.FaultContractAttribute)に似た[より豊富なエラー モデル](https://cloud.google.com/apis/design/errors#error_model)を開発しましたが、このモデルはまだ C# ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c64ed-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="c64ed-128">現在のところ、Go、Java、Python、および C++ でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c64ed-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c64ed-129">[前へ](metadata.md)
>[次へ](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="c64ed-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
