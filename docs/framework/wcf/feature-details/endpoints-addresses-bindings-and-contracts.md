---
title: エンドポイント:アドレス、バインディング、およびコントラクト
description: WCF サービスとのすべての通信がサービスエンドポイントを介してどのように行われるかについて説明します。これにより、クライアントがサービスによって提供される機能にアクセスできるようになります。
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247313"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="bca29-103">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="bca29-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="bca29-104">Windows Communication Foundation (WCF) サービスとの通信はすべて、サービスの*エンドポイント*を介して行われます。</span><span class="sxs-lookup"><span data-stu-id="bca29-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="bca29-105">エンドポイントは、クライアントが WCF サービスによって提供される機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="bca29-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="bca29-106">各エンドポイントは、次の 4 つのプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bca29-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="bca29-107">そのエンドポイントの場所を示すアドレス。</span><span class="sxs-lookup"><span data-stu-id="bca29-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="bca29-108">クライアントがエンドポイントと通信する方法を指定するバインディング。</span><span class="sxs-lookup"><span data-stu-id="bca29-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="bca29-109">利用可能な操作を識別するためのコントラクト。</span><span class="sxs-lookup"><span data-stu-id="bca29-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="bca29-110">エンドポイントのローカル実装の詳細を指定する一連の動作。</span><span class="sxs-lookup"><span data-stu-id="bca29-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="bca29-111">このトピックでは、このエンドポイント構造について説明し、WCF オブジェクトモデルでの表現方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="bca29-112">エンドポイントの構造</span><span class="sxs-lookup"><span data-stu-id="bca29-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="bca29-113">各エンドポイントの構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bca29-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="bca29-114">アドレス : アドレスは、エンドポイントを一意に識別し、サービスの潜在的ユーザーにそのエンドポイントの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="bca29-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="bca29-115">これは、WCF オブジェクトモデルでクラスによって表され <xref:System.ServiceModel.EndpointAddress> ます。</span><span class="sxs-lookup"><span data-stu-id="bca29-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="bca29-116"><xref:System.ServiceModel.EndpointAddress> クラスには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bca29-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="bca29-117"><xref:System.ServiceModel.EndpointAddress.Uri%2A> プロパティは、サービスのアドレスを表します。</span><span class="sxs-lookup"><span data-stu-id="bca29-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="bca29-118"><xref:System.ServiceModel.EndpointAddress.Identity%2A> プロパティは、サービスのセキュリティ ID とオプションのメッセージ ヘッダーのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="bca29-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="bca29-119">オプションのメッセージ ヘッダーは、エンドポイントの識別またはエンドポイントとの対話のための、より詳細なアドレス指定情報を追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bca29-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="bca29-120">詳細については、「[エンドポイントアドレスの指定](../specifying-an-endpoint-address.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="bca29-121">バインディング : バインディングは、エンドポイントとの通信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="bca29-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="bca29-122">これには次のものが含まれます</span><span class="sxs-lookup"><span data-stu-id="bca29-122">This includes:</span></span>

  - <span data-ttu-id="bca29-123">使用するトランスポート プロトコル (例 : TCP や HTTP)。</span><span class="sxs-lookup"><span data-stu-id="bca29-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="bca29-124">メッセージに使用するエンコーディング (例 : テキストやバイナリ)。</span><span class="sxs-lookup"><span data-stu-id="bca29-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="bca29-125">必要なセキュリティ要件 (例 : SSL メッセージ セキュリティや SOAP メッセージ セキュリティ)。</span><span class="sxs-lookup"><span data-stu-id="bca29-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="bca29-126">詳細については、「 [WCF バインディングの概要](../bindings-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="bca29-127">バインドは、WCF オブジェクトモデルで抽象基本クラスによって表され <xref:System.ServiceModel.Channels.Binding> ます。</span><span class="sxs-lookup"><span data-stu-id="bca29-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="bca29-128">ほとんどのシナリオでは、システム指定のバインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bca29-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="bca29-129">詳細については、「[システム指定のバインディング](../system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="bca29-130">コントラクト : コントラクトは、エンドポイントがクライアントに公開する機能を示します。</span><span class="sxs-lookup"><span data-stu-id="bca29-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="bca29-131">コントラクトは、以下の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="bca29-131">A contract specifies:</span></span>

  - <span data-ttu-id="bca29-132">クライアントから呼び出すことができる操作。</span><span class="sxs-lookup"><span data-stu-id="bca29-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="bca29-133">メッセージの形式。</span><span class="sxs-lookup"><span data-stu-id="bca29-133">The form of the message.</span></span>

  - <span data-ttu-id="bca29-134">操作を呼び出すために必要な入力パラメーターまたはデータの型。</span><span class="sxs-lookup"><span data-stu-id="bca29-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="bca29-135">クライアントが予期できる処理メッセージまたは応答メッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="bca29-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="bca29-136">コントラクトを定義する方法の詳細については、「[サービスコントラクトの設計](../designing-service-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="bca29-137">動作 : エンドポイントの動作を使用すると、サービス エンドポイントのローカル動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bca29-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="bca29-138">エンドポイント動作では、WCF ランタイムの構築プロセスに参加することによってこれを実現します。</span><span class="sxs-lookup"><span data-stu-id="bca29-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="bca29-139">エンドポイントの動作の一例は、<xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> プロパティです。このプロパティにより、SOAP アドレスまたは Web サービス記述言語 (WSDL) アドレスとは異なるリッスン アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bca29-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="bca29-140">詳細については、「 [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="bca29-141">エンドポイントの定義</span><span class="sxs-lookup"><span data-stu-id="bca29-141">Defining Endpoints</span></span>

<span data-ttu-id="bca29-142">サービスのエンドポイントは、コードを使用して強制的に指定するか、構成を介して宣言として指定することができます。</span><span class="sxs-lookup"><span data-stu-id="bca29-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="bca29-143">詳細については、「[方法: 構成でサービスエンドポイントを作成](how-to-create-a-service-endpoint-in-configuration.md)する」および「[方法: コードでサービスエンドポイントを作成する](how-to-create-a-service-endpoint-in-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bca29-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bca29-144">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bca29-144">In This Section</span></span>

<span data-ttu-id="bca29-145">このセクションでは、バインディング、エンドポイント、およびアドレスの目的を説明し、バインディングとエンドポイントの構成方法および `ClientVia` 動作と `ListenUri` プロパティの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bca29-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="bca29-146">[扱い](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="bca29-147">WCF でのエンドポイントのアドレス指定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="bca29-148">[現存](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="bca29-149">バインディングを使用して、クライアントとサービスが相互に通信するために必要なトランスポート、エンコーディング、およびプロトコルの詳細を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="bca29-150">[関する](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="bca29-151">コントラクトでサービスのメソッドが定義されるしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="bca29-152">[方法: 構成にサービスエンドポイントを作成する](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="bca29-153">構成にサービス エンドポイントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="bca29-154">[方法: コードでサービスエンドポイントを作成する](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="bca29-155">コード内にサービス エンドポイントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="bca29-156">[方法: Svcutil.exe を使用してコンパイル済みサービスコードを検証する](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="bca29-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="bca29-157">[ServiceModel メタデータユーティリティツール (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)を使用してサービスをホストせずにサービスの実装と構成でエラーを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca29-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bca29-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="bca29-158">See also</span></span>

- [<span data-ttu-id="bca29-159">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="bca29-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="bca29-160">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="bca29-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
