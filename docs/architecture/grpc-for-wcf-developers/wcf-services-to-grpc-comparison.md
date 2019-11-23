---
title: Wcf 開発者向けの WCF と gRPC-gRPC の比較
description: 分散アプリケーションを構築するための WCF および gRPC フレームワークの比較。
ms.date: 09/02/2019
ms.openlocfilehash: 312492dcce4bdef61feff0bf924c6df287b9c676
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966951"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="e6411-103">WCF と gRPC の比較</span><span class="sxs-lookup"><span data-stu-id="e6411-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="e6411-104">前の章では、Protobuf と gRPC がメッセージを処理する方法について詳しく説明しました。</span><span class="sxs-lookup"><span data-stu-id="e6411-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="e6411-105">WCF から gRPC への詳細な変換を実行する前に、現在 WCF で利用できる機能の範囲が gRPC でどのように処理されるか、および同等の gRPC でないと思われる場合に使用できる回避策について確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e6411-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="e6411-106">特に、この章では次の項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6411-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="e6411-107">操作とメソッド</span><span class="sxs-lookup"><span data-stu-id="e6411-107">Operations and methods</span></span>
- <span data-ttu-id="e6411-108">バインドとトランスポート</span><span class="sxs-lookup"><span data-stu-id="e6411-108">Bindings and transports</span></span>
- <span data-ttu-id="e6411-109">RPC の種類</span><span class="sxs-lookup"><span data-stu-id="e6411-109">RPC types</span></span>
- <span data-ttu-id="e6411-110">メタデータ</span><span class="sxs-lookup"><span data-stu-id="e6411-110">Metadata</span></span>
- <span data-ttu-id="e6411-111">エラー処理</span><span class="sxs-lookup"><span data-stu-id="e6411-111">Error handling</span></span>
- <span data-ttu-id="e6411-112">WS-MANAGEMENT プロトコル\*</span><span class="sxs-lookup"><span data-stu-id="e6411-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="e6411-113">gRPC の例</span><span class="sxs-lookup"><span data-stu-id="e6411-113">gRPC example</span></span>

<span data-ttu-id="e6411-114">Visual Studio 2019 またはコマンドラインから新しい ASP.NET Core 3.0 gRPC プロジェクトを作成すると、"Hello World" に相当する gRPC が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e6411-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="e6411-115">これは、サービスとそのメッセージを定義する `greeter.proto` ファイルと、サービスを実装する `GreeterService.cs` ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e6411-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="e6411-116">この章では、gRPC のさまざまな概念と機能について説明するときに、このコード例を参照します。</span><span class="sxs-lookup"><span data-stu-id="e6411-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e6411-117">[前へ](protobuf-maps.md)
>[次へ](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="e6411-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
