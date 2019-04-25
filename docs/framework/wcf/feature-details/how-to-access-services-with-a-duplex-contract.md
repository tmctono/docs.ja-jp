---
title: '方法: Access services と双方向コントラクト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 366fd9d6aa220bcbec1ee8fb2a04d1b84755800a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855141"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="d8180-102">方法: Access services と双方向コントラクト</span><span class="sxs-lookup"><span data-stu-id="d8180-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="d8180-103">Windows Communication Foundation (WCF) の機能の 1 つは、双方向メッセージング パターンを使用してサービスを作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="d8180-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="d8180-104">双方向のメッセージング パターンを使用するサービスは、コールバックを通じてクライアントと通信できます。</span><span class="sxs-lookup"><span data-stu-id="d8180-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="d8180-105">このトピックでは、コールバック インターフェイスを実装するクライアント クラスで WCF クライアントを作成する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="d8180-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="d8180-106">二重バインディングでは、クライアントの IP アドレスをサービスに公開します。</span><span class="sxs-lookup"><span data-stu-id="d8180-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="d8180-107">クライアントは、セキュリティを使用して信頼するサービスだけに接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8180-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="d8180-108">基本的な WCF サービスとクライアントの作成に関するチュートリアルについては、次を参照してください。[チュートリアル入門](../../../../docs/framework/wcf/getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8180-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="d8180-109">双方向サービスにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="d8180-109">To access a duplex service</span></span>

1. <span data-ttu-id="d8180-110">2 つのインターフェイスを含むサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8180-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="d8180-111">1 つ目のインターフェイスはサービスに使用し、2 つ目のインターフェイスはコールバックに使用します。</span><span class="sxs-lookup"><span data-stu-id="d8180-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="d8180-112">双方向サービスの作成の詳細については、次を参照してください。[方法。双方向コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8180-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="d8180-113">サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8180-113">Run the service.</span></span>

3. <span data-ttu-id="d8180-114">使用して、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)クライアントのコントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="d8180-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="d8180-115">これを行う方法については、次を参照してください。[方法。クライアントを作成する](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8180-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="d8180-116">次の例に示すように、クライアント クラスにコールバック インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d8180-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="d8180-117"><xref:System.ServiceModel.InstanceContext> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8180-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="d8180-118">コンストラクターには、クライアント クラスのインスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8180-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="d8180-119">必要とするコンス トラクターを使用して、WCF クライアントのインスタンスを作成、<xref:System.ServiceModel.InstanceContext>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d8180-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="d8180-120">コンストラクターの 2 番目のパラメーターは、構成ファイルに含まれるエンドポイントの名前です。</span><span class="sxs-lookup"><span data-stu-id="d8180-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="d8180-121">必要に応じて、WCF クライアントのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8180-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="d8180-122">例</span><span class="sxs-lookup"><span data-stu-id="d8180-122">Example</span></span>

<span data-ttu-id="d8180-123">双方向コントラクトにアクセスするクライアント クラスを作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="d8180-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d8180-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8180-124">See also</span></span>

- [<span data-ttu-id="d8180-125">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="d8180-125">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="d8180-126">方法: 双方向コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8180-126">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="d8180-127">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d8180-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="d8180-128">方法: クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8180-128">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="d8180-129">方法: ChannelFactory を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8180-129">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
