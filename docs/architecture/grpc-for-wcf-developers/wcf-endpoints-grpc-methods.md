---
title: WCF エンドポイントと gRPC メソッド-WCF 開発者向け gRPC
description: ServiceContract および OperationContract 属性で宣言された WCF エンドポイントと、Protobuf で宣言されている gRPC メソッドの比較
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841301"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="19d8f-103">WCF エンドポイントと gRPC メソッド</span><span class="sxs-lookup"><span data-stu-id="19d8f-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="19d8f-104">WCF では、アプリケーションコードを記述するときに、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-104">In WCF, when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="19d8f-105">クラスにアプリケーションコードを記述し、 [Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性を使用してメソッドを装飾します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="19d8f-106">サービスのインターフェイスを宣言し、 [Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性をインターフェイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="19d8f-107">たとえば、WCF の `greet.proto` Greeter service に相当するものは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="19d8f-108">第3章では、Protobuf メッセージ定義を使用してデータクラスを生成する方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="19d8f-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="19d8f-109">サービスとメソッドの宣言は、サービスを実装するために継承する基本クラスを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="19d8f-110">`.proto` ファイルに実装するメソッドを宣言するだけで、オーバーライドする必要がある仮想メソッドを含む基本クラスがコンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="19d8f-111">OperationContract プロパティ</span><span class="sxs-lookup"><span data-stu-id="19d8f-111">OperationContract properties</span></span>

<span data-ttu-id="19d8f-112">[Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性には、その動作を制御または調整するためのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="19d8f-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="19d8f-113">gRPC メソッドでは、この種のコントロールは提供されません。</span><span class="sxs-lookup"><span data-stu-id="19d8f-113">gRPC methods don’t offer this type of control.</span></span> <span data-ttu-id="19d8f-114">次の表では、これらの `OperationContract` のプロパティと、gRPC で処理される機能 (またはではない) を設定します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-114">The following table sets out those `OperationContract` properties and how the functionality they specify is (or isn’t) dealt with in gRPC:</span></span>

| <span data-ttu-id="19d8f-115">`OperationContract` プロパティ</span><span class="sxs-lookup"><span data-stu-id="19d8f-115">`OperationContract` property</span></span> | <span data-ttu-id="19d8f-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="19d8f-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="19d8f-117">操作を識別する URI。</span><span class="sxs-lookup"><span data-stu-id="19d8f-117">URI identifying the operation.</span></span> <span data-ttu-id="19d8f-118">gRPC は、`.proto` ファイルの `package`、`service`、および `rpc` の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-118">gRPC uses the name of the `package`, `service` and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="19d8f-119">すべての gRPC サービスメソッドは `Task` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="19d8f-120">下記のメモをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19d8f-120">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="19d8f-121">一方向の gRPC メソッドは、`Empty` の結果を返すか、クライアントストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="19d8f-122">下記のメモをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19d8f-122">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="19d8f-123">GRPC では、SOAP 関連の意味はありません。</span><span class="sxs-lookup"><span data-stu-id="19d8f-123">SOAP-related, no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="19d8f-124">メッセージの暗号化なし。ネットワーク暗号化は、トランスポート層 (TLS over HTTP/2) で処理されます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-124">No message encryption; network encryption handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="19d8f-125">GRPC では、SOAP 関連の意味はありません。</span><span class="sxs-lookup"><span data-stu-id="19d8f-125">SOAP-related, no meaning in gRPC.</span></span> |

<span data-ttu-id="19d8f-126">`IsInitiating` プロパティを使用すると、 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)内のメソッドをセッションの一部として呼び出す最初のメソッドにすることができないことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-126">The `IsInitiating` property lets you indicate that a method within a [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="19d8f-127">`IsTerminating` プロパティを使用すると、操作が呼び出された後 (またはクライアントがコールバッククライアントで使用されている場合)、サーバーはセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="19d8f-127">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if used on a callback client).</span></span> <span data-ttu-id="19d8f-128">GRPC では、1つのメソッドによってストリームが作成され、明示的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="19d8f-128">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="19d8f-129">「 [Grpc streaming](rpc-types.md#grpc-streaming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d8f-129">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="19d8f-130">GRPC のセキュリティと暗号化の詳細については、[第6章](security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d8f-130">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="19d8f-131">[前へ](wcf-services-to-grpc-comparison.md)
>[次へ](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="19d8f-131">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
