---
title: WCF クライアントの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: b314b61584e45ac5e80a248e639bdac427ba4a57
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "82021725"
---
# <a name="wcf-client-overview"></a><span data-ttu-id="a6f88-102">WCF クライアントの概要</span><span class="sxs-lookup"><span data-stu-id="a6f88-102">WCF client overview</span></span>

<span data-ttu-id="a6f88-103">このセクションでは、クライアント アプリケーションの動作、Windows 通信基盤 (WCF) クライアントの構成、作成、および使用方法、およびクライアント アプリケーションをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-103">This section describes what client applications do, how to configure, create, and use a Windows Communication Foundation (WCF) client, and how to secure client applications.</span></span>  
  
## <a name="using-wcf-client-objects"></a><span data-ttu-id="a6f88-104">WCF クライアント オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="a6f88-104">Using WCF Client Objects</span></span>  
 <span data-ttu-id="a6f88-105">クライアント アプリケーションは、WCF クライアントを使用して別のアプリケーションと通信するマネージ アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a6f88-105">A client application is a managed application that uses a WCF client to communicate with another application.</span></span> <span data-ttu-id="a6f88-106">WCF サービスのクライアント アプリケーションを作成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-106">Creating a client application for a WCF service requires the following steps:</span></span>  
  
1. <span data-ttu-id="a6f88-107">サービス エンドポイントのサービス コントラクト、バインディング、およびアドレス情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-107">Obtain the service contract, bindings, and address information for a service endpoint.</span></span>  
  
2. <span data-ttu-id="a6f88-108">その情報を使用して WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-108">Create a WCF client using that information.</span></span>  
  
3. <span data-ttu-id="a6f88-109">操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-109">Call operations.</span></span>  
  
4. <span data-ttu-id="a6f88-110">WCF クライアント オブジェクトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-110">Close the WCF client object.</span></span>  
  
<span data-ttu-id="a6f88-111">この後の各セクションでは、これらの手順について詳しく説明します。また、次の内容についても簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-111">The following sections discuss these steps and provide brief introductions to the following issues:</span></span>  
  
- <span data-ttu-id="a6f88-112">エラーの処理</span><span class="sxs-lookup"><span data-stu-id="a6f88-112">Handling errors.</span></span>  
  
- <span data-ttu-id="a6f88-113">クライアントの構成とセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a6f88-113">Configuring and securing clients.</span></span>  
  
- <span data-ttu-id="a6f88-114">双方向サービスのコールバック オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a6f88-114">Creating callback objects for duplex services.</span></span>  
  
- <span data-ttu-id="a6f88-115">サービスの非同期呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f88-115">Calling services asynchronously.</span></span>  
  
- <span data-ttu-id="a6f88-116">クライアント チャネルを使用したサービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f88-116">Calling services using client channels.</span></span>  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a><span data-ttu-id="a6f88-117">サービス コントラクト、バインディング、およびアドレスを取得する</span><span class="sxs-lookup"><span data-stu-id="a6f88-117">Obtain the Service Contract, Bindings, and Addresses</span></span>  
 <span data-ttu-id="a6f88-118">WCF では、サービスとクライアントは、マネージ属性、インターフェイス、およびメソッドを使用してコントラクトをモデル化します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-118">In WCF, services and clients model contracts using managed attributes, interfaces, and methods.</span></span> <span data-ttu-id="a6f88-119">クライアント アプリケーションからサービスに接続するには、そのサービス コントラクトの型情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-119">To connect to a service in a client application, you need to obtain the type information for the service contract.</span></span> <span data-ttu-id="a6f88-120">通常は、サービス コントラクトの型情報を取得するには、[サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-120">Typically, you obtain type information for the service contract by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="a6f88-121">このユーティリティは、サービスからメタデータをダウンロードし、選択した言語でマネージ ソース コード ファイルに変換し、WCF クライアント オブジェクトの構成に使用できるクライアント アプリケーション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-121">The utility downloads metadata from the service, converts it to a managed source code file in the language of your choice, and creates a client application configuration file that you can use to configure your WCF client object.</span></span> <span data-ttu-id="a6f88-122">たとえば、`MyCalculatorService`を呼び出す WCF クライアント オブジェクトを作成する場合、そのサービスのメタデータが で`http://computerName/MyCalculatorService/Service.svc?wsdl`公開されている場合、次のコード例は、マネージ コードでサービス コントラクトを含む`ClientCode.vb`ファイルを取得するために Svcutil.exe を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f88-122">For example, if you are going to create a WCF client object to invoke a `MyCalculatorService`, and you know that the metadata for that service is published at `http://computerName/MyCalculatorService/Service.svc?wsdl`, then the following code example shows how to use Svcutil.exe to obtain a `ClientCode.vb` file that contains the service contract in managed code.</span></span>  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 <span data-ttu-id="a6f88-123">このコントラクト コードをクライアント アプリケーションにコンパイルするか、クライアント アプリケーションが WCF クライアント オブジェクトを作成するために使用できる別のアセンブリにコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-123">You can either compile this contract code into the client application or into another assembly that the client application can then use to create a WCF client object.</span></span> <span data-ttu-id="a6f88-124">構成ファイルを使用してサービスに正しく接続するクライアント オブジェクトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-124">You can use the configuration file to configure the client object to properly connect to the service .</span></span>  
  
 <span data-ttu-id="a6f88-125">このプロセスの例については、「[方法 : クライアントを作成する](how-to-create-a-wcf-client.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-125">For an example of this process, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="a6f88-126">契約の詳細については、[契約](./feature-details/contracts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-126">For more complete information about contracts, see [Contracts](./feature-details/contracts.md).</span></span>  
  
## <a name="create-a-wcf-client-object"></a><span data-ttu-id="a6f88-127">WCF クライアント オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a6f88-127">Create a WCF Client Object</span></span>  
 <span data-ttu-id="a6f88-128">WCF クライアントは、クライアントがリモート サービスと通信するために使用できる形式で WCF サービスを表すローカル オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a6f88-128">A WCF client is a local object that represents a WCF service in a form that the client can use to communicate with the remote service.</span></span> <span data-ttu-id="a6f88-129">WCF クライアント型は、ターゲット サービス コントラクトを実装するため、1 つを作成して構成するときに、クライアント オブジェクトを直接使用してサービス操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-129">WCF client types implement the target service contract, so when you create one and configure it, you can then use the client object directly to invoke service operations.</span></span> <span data-ttu-id="a6f88-130">WCF ランタイムは、メソッドの呼び出しをメッセージに変換し、サービスに送信し、応答をリッスンし、返り値または`out``ref`パラメーターとして WCF クライアント オブジェクトにそれらの値を返します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-130">The WCF run time converts the method calls into messages, sends them to the service, listens for the reply, and returns those values to the WCF client object as return values or `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="a6f88-131">WCF クライアント チャネル オブジェクトを使用して、サービスに接続して使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-131">You can also use WCF client channel objects to connect with and use services.</span></span> <span data-ttu-id="a6f88-132">詳細については、「 [WCF クライアント アーキテクチャ](./feature-details/client-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-132">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
#### <a name="creating-a-new-wcf-object"></a><span data-ttu-id="a6f88-133">新しい WCF オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a6f88-133">Creating a New WCF Object</span></span>  
 <span data-ttu-id="a6f88-134">サービスアプリケーションから次の簡単なサービス コントラクトが生成されていることを前提に、<xref:System.ServiceModel.ClientBase%601> クラスの使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-134">To illustrate the use of a <xref:System.ServiceModel.ClientBase%601> class, assume the following simple service contract has been generated from a service application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6f88-135">Visual Studio を使用して WCF クライアントを作成している場合、プロジェクトにサービス参照を追加すると、オブジェクトが自動的にオブジェクト ブラウザーに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-135">If you are using Visual Studio to create your WCF client, objects are loaded automatically into the object browser when you add a service reference to your project.</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 <span data-ttu-id="a6f88-136">Visual Studio を使用していない場合は、生成されたコントラクト コードを調べて、<xref:System.ServiceModel.ClientBase%601>拡張する型とサービス`ISampleService`コントラクト インターフェイスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-136">If you are not using Visual Studio, examine the generated contract code to find the type that extends <xref:System.ServiceModel.ClientBase%601> and the service contract interface `ISampleService`.</span></span> <span data-ttu-id="a6f88-137">この場合、この型は次のようなコードになります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-137">In this case, that type looks like the following code:</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 <span data-ttu-id="a6f88-138">このクラスを、コンストラクターの 1 つを使用してローカル オブジェクトとして作成し、構成して、型 `ISampleService` のサービスへの接続に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-138">This class can be created as a local object using one of the constructors, configured, and then used to connect to a service of the type `ISampleService`.</span></span>  
  
 <span data-ttu-id="a6f88-139">最初に WCF クライアント オブジェクトを作成してから使用し、単一の try/catch ブロック内で閉じてお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6f88-139">It is recommended that you create your WCF client object first, and then use it and close it inside a single try/catch block.</span></span> <span data-ttu-id="a6f88-140">特定のエラー モード`using`で例外`Using`をマスクできるため、Visual Basic ではステートメントを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-140">Don't use the `using` statement (`Using` in Visual Basic) because it can mask exceptions in certain failure modes.</span></span> <span data-ttu-id="a6f88-141">詳細については、次のセクションを参照してくださいと[WCF クライアント リソースを解放するのには、閉じると中止を使用](./samples/use-close-abort-release-wcf-client-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-141">For more information, see the following sections as well as [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
### <a name="contracts-bindings-and-addresses"></a><span data-ttu-id="a6f88-142">コントラクト、バインディング、およびアドレス</span><span class="sxs-lookup"><span data-stu-id="a6f88-142">Contracts, Bindings, and Addresses</span></span>  
 <span data-ttu-id="a6f88-143">WCF クライアント オブジェクトを作成する前に、クライアント オブジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-143">Before you can create a WCF client object, you must configure the client object.</span></span> <span data-ttu-id="a6f88-144">具体的には、使用するサービス*エンドポイント*が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6f88-144">Specifically, it must have a service *endpoint* to use.</span></span> <span data-ttu-id="a6f88-145">エンドポイントは、サービス コントラクト、バインディング、およびアドレスの組み合わせです </span><span class="sxs-lookup"><span data-stu-id="a6f88-145">An endpoint is the combination of a service contract, a binding, and an address.</span></span> <span data-ttu-id="a6f88-146">(エンドポイントの詳細については、「[エンドポイント: アドレス、バインディング、およびコントラクト](./feature-details/endpoints-addresses-bindings-and-contracts.md)」を参照してください。通常、この情報は、Svcutil.exe ツールが生成する構成ファイルなどのクライアント アプリケーション構成ファイルの[\<エンドポイント>](../configure-apps/file-schema/wcf/endpoint-of-client.md)要素に配置され、クライアント オブジェクトを作成すると自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-146">(For more information about endpoints, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).) Typically, this information is located in the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-of-client.md) element in a client application configuration file, such as the one the Svcutil.exe tool generates, and is loaded automatically when you create your client object.</span></span> <span data-ttu-id="a6f88-147">また、両方の WCF クライアントの種類には、プログラムでこの情報を指定できるオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-147">Both WCF client types also have overloads that enable you to programmatically specify this information.</span></span>  
  
 <span data-ttu-id="a6f88-148">たとえば、上記の例で使用した `ISampleService` 用に生成された構成ファイルには、次のエンドポイント情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-148">For example, a generated configuration file for an `ISampleService` used in the preceding examples contains the following endpoint information.</span></span>  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 <span data-ttu-id="a6f88-149">この構成ファイルの `<client>` 要素には、ターゲット エンドポイントが指定されます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-149">This configuration file specifies a target endpoint in the `<client>` element.</span></span> <span data-ttu-id="a6f88-150">複数のターゲット エンドポイントの使用の詳細については、「<xref:System.ServiceModel.ClientBase%601.%23ctor%2A>または<xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A>コンストラクター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-150">For more information about using multiple target endpoints, see the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> or the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> constructors.</span></span>  
  
## <a name="calling-operations"></a><span data-ttu-id="a6f88-151">操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f88-151">Calling Operations</span></span>  
 <span data-ttu-id="a6f88-152">クライアント オブジェクトを作成して構成したら、try/catch ブロックを作成し、オブジェクトがローカルである場合と同じ方法で操作を呼び出し、WCF クライアント オブジェクトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-152">Once you have a client object created and configured, create a try/catch block, call operations in the same way that you would if the object were local, and close the WCF client object.</span></span> <span data-ttu-id="a6f88-153">クライアント アプリケーションが最初の操作を呼び出すと、WCF は基になるチャネルを自動的に開き、オブジェクトがリサイクルされるときに基になるチャネルが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-153">When the client application calls the first operation, WCF automatically opens the underlying channel, and the underlying channel is closed when the object is recycled.</span></span> <span data-ttu-id="a6f88-154">(また、他の操作を呼び出す前後にチャネルを明示的に開いたり閉じたりすることもできます)。</span><span class="sxs-lookup"><span data-stu-id="a6f88-154">(Alternatively, you can also explicitly open and close the channel prior to or subsequent to calling other operations.)</span></span>  
  
 <span data-ttu-id="a6f88-155">たとえば、次のようなサービス コントラクトを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-155">For example, if you have the following service contract:</span></span>  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _
   Public Interface ICalculator  
        <OperationContract> _
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 <span data-ttu-id="a6f88-156">次のコード例に示すように、WCF クライアント オブジェクトを作成し、そのメソッドを呼び出すことによって操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-156">You can call operations by creating a WCF client object and calling its methods, as the following code example demonstrates.</span></span> <span data-ttu-id="a6f88-157">WCF クライアント オブジェクトの開始、呼び出し、および終了は、単一の try/catch ブロック内で発生します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-157">The opening, calling, and closing of the WCF client object occurs within a single try/catch block.</span></span> <span data-ttu-id="a6f88-158">詳細については、「 [WCF クライアントを使用したサービスへのアクセス](./feature-details/accessing-services-using-a-client.md)」および[「CLOSE と Abort を使用して WCF クライアント リソースを解放する](./samples/use-close-abort-release-wcf-client-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-158">For more information, see [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md) and [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a><span data-ttu-id="a6f88-159">エラーの処理</span><span class="sxs-lookup"><span data-stu-id="a6f88-159">Handling Errors</span></span>  
 <span data-ttu-id="a6f88-160">基になるクライアント チャネルを開いたとき (明示的に開いた場合、または操作を呼び出すことによって自動的に開いた場合)、クライアントまたはチャネル オブジェクトを使用して操作を呼び出したとき、基になるクライアント チャネルを閉じたときときに、クライアント アプリケーションで例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-160">Exceptions can occur in a client application when opening the underlying client channel (whether explicitly or automatically by calling an operation), using the client or channel object to call operations, or when closing the underlying client channel.</span></span> <span data-ttu-id="a6f88-161">少なくともアプリケーションでは、操作から返される SOAP エラーの結果としてスローされる <xref:System.TimeoutException?displayProperty=nameWithType> オブジェクトに加え、可能性のある <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 例外と <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 例外を処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6f88-161">It is recommended at a minimum that applications expect to handle possible <xref:System.TimeoutException?displayProperty=nameWithType> and <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> exceptions in addition to any <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objects thrown as a result of SOAP faults returned by operations.</span></span> <span data-ttu-id="a6f88-162">操作コントラクトで指定されている SOAP エラーは、<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> としてクライアント アプリケーションに送信されます。ここで、型パラメーターは SOAP エラーの詳細な型です。</span><span class="sxs-lookup"><span data-stu-id="a6f88-162">SOAP faults specified in the operation contract are raised to client applications as a <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the type parameter is the detail type of the SOAP fault.</span></span> <span data-ttu-id="a6f88-163">クライアント アプリケーションでのエラー状態の処理の詳細については、「[エラーの送受信」](sending-and-receiving-faults.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-163">For more information about handling error conditions in a client application, see [Sending and Receiving Faults](sending-and-receiving-faults.md).</span></span> <span data-ttu-id="a6f88-164">完全なサンプルでは、クライアントでのエラーの処理方法[を示しています](./samples/expected-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f88-164">For a complete sample the shows how to handle errors in a client, see [Expected Exceptions](./samples/expected-exceptions.md).</span></span>  
  
## <a name="configuring-and-securing-clients"></a><span data-ttu-id="a6f88-165">クライアントの構成とセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a6f88-165">Configuring and Securing Clients</span></span>  
 <span data-ttu-id="a6f88-166">クライアントを構成するには、まず、そのクライアントまたはチャネル オブジェクトに必要なターゲット エンドポイント情報を読み込みます。通常は構成ファイルから読み込みますが、クライアント コンストラクターとプロパティを使用してプログラムで読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-166">Configuring a client starts with the required loading of target endpoint information for the client or channel object, usually from a configuration file, although you can also load this information programmatically using the client constructors and properties.</span></span> <span data-ttu-id="a6f88-167">ただし、特定のクライアントの動作を有効にし、多くのセキュリティ シナリオに対応するには、追加の構成手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6f88-167">However, additional configuration steps are required to enable certain client behavior and for many security scenarios.</span></span>  
  
 <span data-ttu-id="a6f88-168">たとえば、サービス コントラクトのセキュリティ要件はサービス コントラクト インターフェイスに宣言します。Svcutil.exe で構成ファイルを作成した場合、通常そのファイルにはサービスのセキュリティ要件に対応できるバインディングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6f88-168">For example, security requirements for service contracts are declared in the service contract interface, and if Svcutil.exe created a configuration file, that file usually contains a binding that is capable of supporting the security requirements of the service.</span></span> <span data-ttu-id="a6f88-169">ただし、クライアント資格情報の構成など、さらに多くのセキュリティ構成が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-169">In some cases, however, more security configuration may be required, such as configuring client credentials.</span></span> <span data-ttu-id="a6f88-170">WCF クライアントのセキュリティの構成の詳細については、「クライアントの[セキュリティ保護](securing-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-170">For complete information about the configuration of security for WCF clients, see [Securing Clients](securing-clients.md).</span></span>  
  
 <span data-ttu-id="a6f88-171">また、カスタム ランタイム動作など、クライアント アプリケーションでいくつかのカスタム変更を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-171">In addition, some custom modifications can be enabled in client applications, such as custom run-time behaviors.</span></span> <span data-ttu-id="a6f88-172">カスタム クライアント動作を構成する方法の詳細については、「[クライアント動作の構成」](configuring-client-behaviors.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-172">For more information about how to configure a custom client behavior, see [Configuring Client Behaviors](configuring-client-behaviors.md).</span></span>  
  
## <a name="creating-callback-objects-for-duplex-services"></a><span data-ttu-id="a6f88-173">双方向サービスのコールバック オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a6f88-173">Creating Callback Objects for Duplex Services</span></span>  
 <span data-ttu-id="a6f88-174">双方向サービスには、コントラクトの要件に従って呼び出すサービスのコールバック オブジェクトを提供するために、クライアント アプリケーションが実装する必要のあるコールバック コントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-174">Duplex services specify a callback contract that the client application must implement in order to provide a callback object for the service to call according to the requirements of the contract.</span></span> <span data-ttu-id="a6f88-175">コールバック オブジェクトは完全なサービスではありません (たとえば、コールバック オブジェクトを使用してチャネルを初期化できません) が、実装と構成という目的においては、一種のサービスとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-175">Although callback objects are not full services (for example, you cannot initiate a channel with a callback object), for the purposes of implementation and configuration they can be thought of as a kind of service.</span></span>  
  
 <span data-ttu-id="a6f88-176">双方向サービスのクライアントでは、以下の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f88-176">Clients of duplex services must:</span></span>  
  
- <span data-ttu-id="a6f88-177">コールバック コントラクト クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-177">Implement a callback contract class.</span></span>  
  
- <span data-ttu-id="a6f88-178">コールバック コントラクト実装クラスのインスタンスを作成し、それを使用して、WCF クライアント コンストラクターに渡す<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-178">Create an instance of the callback contract implementation class and use it to create the <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> object that you pass to the WCF client constructor.</span></span>  
  
- <span data-ttu-id="a6f88-179">操作を呼び出し、操作のコールバックを処理します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-179">Invoke operations and handle operation callbacks.</span></span>  
  
 <span data-ttu-id="a6f88-180">双方向 WCF クライアント オブジェクトは、コールバック サービスの構成など、コールバックをサポートするために必要な機能を公開する例外を除いて、非両面印刷対応オブジェクトと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-180">Duplex WCF client objects function like their nonduplex counterparts, with the exception that they expose the functionality necessary to support callbacks, including the configuration of the callback service.</span></span>  
  
 <span data-ttu-id="a6f88-181">たとえば、コールバック クラスの <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 属性のプロパティを使用して、コールバック オブジェクトの実行時の動作のさまざまな局面を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-181">For example, you can control various aspects of callback object runtime behavior by using properties of the <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> attribute on the callback class.</span></span> <span data-ttu-id="a6f88-182">また、別の例として、<xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> クラスを使用して、例外情報をコールバック オブジェクトを呼び出したサービスに返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-182">Another example is the use of the <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> class to enable the return of exception information to services that call the callback object.</span></span> <span data-ttu-id="a6f88-183">詳細については、「[双方向サービス](./feature-details/duplex-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-183">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span> <span data-ttu-id="a6f88-184">完全なサンプルについては、[両面印刷](./samples/duplex.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-184">For a complete sample, see [Duplex](./samples/duplex.md).</span></span>  
  
 <span data-ttu-id="a6f88-185">インターネット インフォメーション サービス (IIS) 5.1 を実行する Windows XP コンピューターの場合、双方向クライアントでは <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> クラスを使用してクライアントのベース アドレスを指定する必要があります。そうしない場合は例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-185">On Windows XP computers running Internet Information Services (IIS) 5.1, duplex clients must specify a client base address using the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> class or an exception is thrown.</span></span> <span data-ttu-id="a6f88-186">次のコード例は、コードでこれを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-186">The following code example shows how to do this in code.</span></span>  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 <span data-ttu-id="a6f88-187">次のコードは、構成ファイルでこれを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-187">The following code shows how to do this in a configuration file</span></span>  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a><span data-ttu-id="a6f88-188">サービスの非同期呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f88-188">Calling Services Asynchronously</span></span>  
 <span data-ttu-id="a6f88-189">操作の呼び出し方法は、クライアント開発者に完全に依存します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-189">How operations are called is entirely up to the client developer.</span></span> <span data-ttu-id="a6f88-190">これは、操作を構成するメッセージは、マネージド コードで表現するときに同期メソッドまたは非同期メソッドのどちらかにマップできるためです。</span><span class="sxs-lookup"><span data-stu-id="a6f88-190">This is because the messages that make up an operation can be mapped to either synchronous or asynchronous methods when expressed in managed code.</span></span> <span data-ttu-id="a6f88-191">したがって、操作を非同期に呼び出すクライアントを作成する場合、Svcutil.exe の `/async` オプションを使用して非同期クライアント コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-191">Therefore, if you want to build a client that calls operations asynchronously, you can use Svcutil.exe to generate asynchronous client code using the `/async` option.</span></span> <span data-ttu-id="a6f88-192">詳細については、「[方法 : サービス操作を非同期に呼び出す](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-192">For more information, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
## <a name="calling-services-using-wcf-client-channels"></a><span data-ttu-id="a6f88-193">WCF クライアント チャネルを使用したサービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f88-193">Calling Services Using WCF Client Channels</span></span>  
 <span data-ttu-id="a6f88-194">WCF クライアント型<xref:System.ServiceModel.ClientBase%601>は、基になるチャネル<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>システムを公開するインターフェイスから派生する拡張します。</span><span class="sxs-lookup"><span data-stu-id="a6f88-194">WCF client types extend <xref:System.ServiceModel.ClientBase%601>, which itself derives from <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interface to expose the underlying channel system.</span></span> <span data-ttu-id="a6f88-195">ターゲットのサービス コントラクトと <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> クラスを使用して、サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f88-195">You can invoke services by using the target service contract with the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a6f88-196">詳細については、「 [WCF クライアント アーキテクチャ](./feature-details/client-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f88-196">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f88-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6f88-197">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
