---
title: '方法: コード内でクライアント バインディングを指定する'
description: WCF クライアントのバインディングをコードで強制的に指定する方法について説明します。 この例では、クライアントがサービスにアクセスします。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: e5e1dff98121985a598579d83043de838e21e5f1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244505"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="062b5-104">方法: コード内でクライアント バインディングを指定する</span><span class="sxs-lookup"><span data-stu-id="062b5-104">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="062b5-105">この例では、電卓サービスを使用するためのクライアントを作成し、そのクライアントのバインディングを強制的にコードで指定します。</span><span class="sxs-lookup"><span data-stu-id="062b5-105">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="062b5-106">クライアントは `CalculatorService` にアクセスします。これにより、`ICalculator` インターフェイスが実装され、サービスとクライアントの両方で <xref:System.ServiceModel.BasicHttpBinding> クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="062b5-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="062b5-107">ここで説明する手順では、電卓サービスが実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="062b5-107">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="062b5-108">サービスの構築の詳細については、「[方法: 構成でサービスバインディングを指定](how-to-specify-a-service-binding-in-configuration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="062b5-108">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="062b5-109">また、 [ServiceModel メタデータユーティリティツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)WINDOWS COMMUNICATION FOUNDATION (WCF) を使用して、クライアントコンポーネントを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="062b5-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="062b5-110">このツールでは、サービスにアクセスするためのクライアント コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="062b5-110">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="062b5-111">クライアントは 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="062b5-111">The client is built in two parts.</span></span> <span data-ttu-id="062b5-112">Svcutil.exe によって、`ClientCalculator` インターフェイスを実装する `ICalculator` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="062b5-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="062b5-113">次に、`ClientCalculator` のインスタンスを作成し、サービスのバインディングとアドレスをコードで指定して、このクライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="062b5-113">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="062b5-114">この例のソースコピーについては、 [Basicbinding](./samples/basicbinding.md)サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="062b5-114">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="062b5-115">コード内でカスタム バインドを指定するには</span><span class="sxs-lookup"><span data-stu-id="062b5-115">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="062b5-116">コマンド ラインから Svcutil.exe を実行して、サービス メタデータからコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="062b5-116">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="062b5-117">生成されたクライアントには、クライアントの実装時に満たされなければならないサービス コントラクトを定義する `ICalculator` インターフェイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="062b5-117">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="062b5-118">生成されたクライアントは `ClientCalculator` も実装します。</span><span class="sxs-lookup"><span data-stu-id="062b5-118">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="062b5-119">クライアント アプリケーション内で `ClientCalculator` クラスを使用する <xref:System.ServiceModel.BasicHttpBinding> のインスタンスを作成し、指定したアドレスのサービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="062b5-119">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="062b5-120">クライアントをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="062b5-120">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062b5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="062b5-121">See also</span></span>

- [<span data-ttu-id="062b5-122">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="062b5-122">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
