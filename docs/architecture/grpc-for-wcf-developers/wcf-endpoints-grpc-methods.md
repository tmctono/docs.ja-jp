---
title: WCF エンドポイントと gRPC メソッド-WCF 開発者向け gRPC
description: ServiceContract および OperationContract 属性で宣言された WCF エンドポイントと、Protobuf で宣言されている gRPC メソッドの比較
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503428"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="af7f5-103">WCF エンドポイントと gRPC メソッド</span><span class="sxs-lookup"><span data-stu-id="af7f5-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="af7f5-104">Windows Communication Foundation (WCF) では、アプリケーションコードを記述するときに、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="af7f5-105">クラスにアプリケーションコードを記述し、 [Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性を使用してメソッドを装飾します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="af7f5-106">サービスのインターフェイスを宣言し、 [Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性をインターフェイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="af7f5-107">たとえば、WCF の `greet.proto` Greeter service に相当するものは、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="af7f5-108">第3章では、Protobuf メッセージ定義を使用してデータクラスを生成する方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="af7f5-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="af7f5-109">サービスとメソッドの宣言は、サービスを実装するために継承する基本クラスを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="af7f5-110">`.proto` ファイルに実装するメソッドを宣言するだけで、コンパイラは、オーバーライドする必要がある仮想メソッドを含む基本クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="af7f5-111">OperationContract プロパティ</span><span class="sxs-lookup"><span data-stu-id="af7f5-111">OperationContract properties</span></span>

<span data-ttu-id="af7f5-112">[Operationcontract](xref:System.ServiceModel.OperationContractAttribute)属性には、その動作を制御または調整するためのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="af7f5-113">gRPC メソッドでは、この種のコントロールは提供されません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="af7f5-114">次の表は、これらの `OperationContract` のプロパティを示し、gRPC で処理される機能 (または) を示しています。</span><span class="sxs-lookup"><span data-stu-id="af7f5-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="af7f5-115">`OperationContract` プロパティ</span><span class="sxs-lookup"><span data-stu-id="af7f5-115">`OperationContract` property</span></span> | <span data-ttu-id="af7f5-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="af7f5-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="af7f5-117">URI は、操作を識別します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-117">A URI identifies the operation.</span></span> <span data-ttu-id="af7f5-118">gRPC は、`.proto` ファイルの `package`、`service`、および `rpc` の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="af7f5-119">すべての gRPC サービスメソッドは `Task` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="af7f5-120">この表の後にある段落を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af7f5-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="af7f5-121">一方向の gRPC メソッドは、`Empty` の結果を返すか、クライアントストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="af7f5-122">この表の後にある段落を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af7f5-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="af7f5-123">このプロパティは SOAP に関連し、gRPC では意味がありません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="af7f5-124">メッセージ暗号化はありません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-124">There's no message encryption.</span></span> <span data-ttu-id="af7f5-125">ネットワーク暗号化は、トランスポート層 (TLS over HTTP/2) で処理されます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="af7f5-126">このプロパティは SOAP に関連し、gRPC では意味がありません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="af7f5-127">`IsInitiating` プロパティを使用すると、 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)内のメソッドを、セッションの一部として呼び出される最初のメソッドにすることができないことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="af7f5-128">`IsTerminating` プロパティを使用すると、操作が呼び出された後 (または、コールバッククライアントでプロパティが使用されている場合はクライアント)、サーバーによってセッションが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="af7f5-129">GRPC では、1つのメソッドによってストリームが作成され、明示的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="af7f5-130">「 [Grpc streaming](rpc-types.md#grpc-streaming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af7f5-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="af7f5-131">GRPC のセキュリティと暗号化の詳細については、[第6章](security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af7f5-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="af7f5-132">[前へ](wcf-services-to-grpc-comparison.md)
>[次へ](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="af7f5-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
