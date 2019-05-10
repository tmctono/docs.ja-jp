---
title: エンドポイント:アドレス、バインディング、およびコントラクト
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3d345cfa3169e22e7c5e85cd1c7d11c2feef4f5f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665959"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="31df2-102">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="31df2-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="31df2-103">を介して Windows Communication Foundation (WCF) サービスとすべての通信が行われます、*エンドポイント*サービス。</span><span class="sxs-lookup"><span data-stu-id="31df2-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="31df2-104">エンドポイントは、WCF サービスによって提供される機能へのアクセスをクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="31df2-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="31df2-105">各エンドポイントは、次の 4 つのプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="31df2-105">Each endpoint consists of four properties:</span></span>  
  
- <span data-ttu-id="31df2-106">そのエンドポイントの場所を示すアドレス。</span><span class="sxs-lookup"><span data-stu-id="31df2-106">An address that indicates where the endpoint can be found.</span></span>  
  
- <span data-ttu-id="31df2-107">クライアントがエンドポイントと通信する方法を指定するバインディング。</span><span class="sxs-lookup"><span data-stu-id="31df2-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="31df2-108">利用可能な操作を識別するためのコントラクト。</span><span class="sxs-lookup"><span data-stu-id="31df2-108">A contract that identifies the operations available.</span></span>  
  
- <span data-ttu-id="31df2-109">エンドポイントのローカル実装の詳細を指定する一連の動作。</span><span class="sxs-lookup"><span data-stu-id="31df2-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="31df2-110">このトピックでは、エンドポイントの構造について説明し、WCF オブジェクト モデルでの表現方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="31df2-111">エンドポイントの構造</span><span class="sxs-lookup"><span data-stu-id="31df2-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="31df2-112">各エンドポイントの構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31df2-112">Each endpoint consists of the following:</span></span>  
  
- <span data-ttu-id="31df2-113">アドレス:アドレスは一意にエンドポイントを識別し、潜在的な指示があるサービスのコンシューマーです。</span><span class="sxs-lookup"><span data-stu-id="31df2-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="31df2-114">WCF オブジェクト モデルで表されます、<xref:System.ServiceModel.EndpointAddress>クラス。</span><span class="sxs-lookup"><span data-stu-id="31df2-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="31df2-115"><xref:System.ServiceModel.EndpointAddress> クラスには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31df2-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    - <span data-ttu-id="31df2-116"><xref:System.ServiceModel.EndpointAddress.Uri%2A> プロパティは、サービスのアドレスを表します。</span><span class="sxs-lookup"><span data-stu-id="31df2-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    - <span data-ttu-id="31df2-117"><xref:System.ServiceModel.EndpointAddress.Identity%2A> プロパティは、サービスのセキュリティ ID とオプションのメッセージ ヘッダーのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="31df2-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="31df2-118">オプションのメッセージ ヘッダーは、エンドポイントの識別またはエンドポイントとの対話のための、より詳細なアドレス指定情報を追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="31df2-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="31df2-119">詳細については、次を参照してください。[エンドポイント アドレスを指定する](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
- <span data-ttu-id="31df2-120">バインディング:バインディングはエンドポイントとの通信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="31df2-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="31df2-121">バインディングには、以下の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31df2-121">This includes:</span></span>  
  
    - <span data-ttu-id="31df2-122">使用するトランスポート プロトコル (例 : TCP や HTTP)。</span><span class="sxs-lookup"><span data-stu-id="31df2-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    - <span data-ttu-id="31df2-123">メッセージに使用するエンコーディング (例 : テキストやバイナリ)。</span><span class="sxs-lookup"><span data-stu-id="31df2-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    - <span data-ttu-id="31df2-124">必要なセキュリティ要件 (例 : SSL メッセージ セキュリティや SOAP メッセージ セキュリティ)。</span><span class="sxs-lookup"><span data-stu-id="31df2-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="31df2-125">詳細については、次を参照してください。 [WCF のバインディングの概要](../../../../docs/framework/wcf/bindings-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="31df2-126">バインディングは抽象基本クラスで WCF オブジェクト モデルで表される<xref:System.ServiceModel.Channels.Binding>します。</span><span class="sxs-lookup"><span data-stu-id="31df2-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="31df2-127">ほとんどのシナリオでは、システム指定のバインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="31df2-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="31df2-128">詳細については、次を参照してください。 [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
- <span data-ttu-id="31df2-129">コントラクト:コントラクトでは、クライアントに公開するエンドポイント機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="31df2-130">コントラクトは、以下の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="31df2-130">A contract specifies:</span></span>  
  
    - <span data-ttu-id="31df2-131">クライアントから呼び出すことができる操作。</span><span class="sxs-lookup"><span data-stu-id="31df2-131">What operations can be called by a client.</span></span>  
  
    - <span data-ttu-id="31df2-132">メッセージの形式。</span><span class="sxs-lookup"><span data-stu-id="31df2-132">The form of the message.</span></span>  
  
    - <span data-ttu-id="31df2-133">操作を呼び出すために必要な入力パラメーターまたはデータの型。</span><span class="sxs-lookup"><span data-stu-id="31df2-133">The type of input parameters or data required to call the operation.</span></span>  
  
    - <span data-ttu-id="31df2-134">クライアントが予期できる処理メッセージまたは応答メッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="31df2-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="31df2-135">コントラクトを定義する詳細については、次を参照してください。 [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
- <span data-ttu-id="31df2-136">動作:エンドポイントの動作を使用して、サービス エンドポイントのローカル動作をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="31df2-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="31df2-137">エンドポイントの動作は、WCFruntime の作成プロセスで参加することでこれを実現します。</span><span class="sxs-lookup"><span data-stu-id="31df2-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="31df2-138">エンドポイントの動作の一例は、<xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> プロパティです。このプロパティにより、SOAP アドレスまたは Web サービス記述言語 (WSDL) アドレスとは異なるリッスン アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="31df2-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="31df2-139">詳細については、次を参照してください。 [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="31df2-140">エンドポイントの定義</span><span class="sxs-lookup"><span data-stu-id="31df2-140">Defining Endpoints</span></span>  
 <span data-ttu-id="31df2-141">サービスのエンドポイントは、コードを使用して強制的に指定するか、構成を介して宣言として指定することができます。</span><span class="sxs-lookup"><span data-stu-id="31df2-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="31df2-142">詳細については、「[方法 :サービス エンドポイントの構成で作成](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)と[方法。コードでサービス エンドポイントを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31df2-143">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="31df2-143">In This Section</span></span>  
 <span data-ttu-id="31df2-144">このセクションでは、バインディング、エンドポイント、およびアドレスの目的を説明し、バインディングとエンドポイントの構成方法および `ClientVia` 動作と `ListenUri` プロパティの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31df2-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="31df2-145">アドレス</span><span class="sxs-lookup"><span data-stu-id="31df2-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="31df2-146">Wcf エンドポイントのアドレス指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="31df2-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="31df2-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="31df2-148">バインディングを使用して、クライアントとサービスが相互に通信するために必要なトランスポート、エンコーディング、およびプロトコルの詳細を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="31df2-149">コントラクト</span><span class="sxs-lookup"><span data-stu-id="31df2-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="31df2-150">コントラクトでサービスのメソッドが定義されるしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="31df2-151">方法: 構成でサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="31df2-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="31df2-152">構成にサービス エンドポイントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="31df2-153">方法: コードでサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="31df2-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="31df2-154">コード内にサービス エンドポイントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31df2-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="31df2-155">方法: Svcutil.exe を使用して、コンパイル済みサービス コードを検証するには</span><span class="sxs-lookup"><span data-stu-id="31df2-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="31df2-156">使用してサービスをホストせず、サービス実装と構成でエラーを検出する方法について説明します、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="31df2-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31df2-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="31df2-157">See also</span></span>

- [<span data-ttu-id="31df2-158">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="31df2-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="31df2-159">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="31df2-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
