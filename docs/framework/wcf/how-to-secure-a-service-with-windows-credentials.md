---
title: '方法: Windows 資格情報でサービスをセキュリティで保護する'
description: Windows ドメイン内に存在し、同じドメイン内のクライアントによって呼び出される WCF サービスでトランスポートセキュリティを有効にする方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 8ef164e1475bfd5f047a99426a2bed43a7aa7353
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244634"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="ca2f0-103">方法: Windows 資格情報でサービスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="ca2f0-103">How to: Secure a Service with Windows Credentials</span></span>

<span data-ttu-id="ca2f0-104">このトピックでは、Windows ドメインに存在し、同じドメイン内のクライアントによって呼び出される Windows Communication Foundation (WCF) サービスでトランスポートセキュリティを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-104">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="ca2f0-105">このシナリオの詳細については、「 [Windows 認証を使用したトランスポートセキュリティ](./feature-details/transport-security-with-windows-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-105">For more information about this scenario, see [Transport Security with Windows Authentication](./feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="ca2f0-106">サンプルアプリケーションについては、 [WSHttpBinding](./samples/wshttpbinding.md)サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-106">For a sample application, see the [WSHttpBinding](./samples/wshttpbinding.md) sample.</span></span>

<span data-ttu-id="ca2f0-107">このトピックでは、定義済みのコントラクト インターフェイスと実装が既に存在するものとして、それに機能を追加していきます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-107">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="ca2f0-108">既存のサービスとクライアントを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-108">You can also modify an existing service and client.</span></span>

<span data-ttu-id="ca2f0-109">Windows 資格情報によるサービスのセキュリティ保護は、完全にコードで実現できます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-109">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="ca2f0-110">または、構成ファイルを使用して、一部のコードを省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-110">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="ca2f0-111">このトピックでは両方の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-111">This topic shows both ways.</span></span> <span data-ttu-id="ca2f0-112">ただし、どちらか 1 つの方法だけを使うようにして、両方は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-112">Be sure you only use one of the ways, not both.</span></span>

<span data-ttu-id="ca2f0-113">最初の 3 つの手順は、コードを使用してサービスをセキュリティで保護する方法について示しています。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-113">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="ca2f0-114">4 番目と 5 番目の手順は、構成ファイルを使用して同様の操作を行う方法について示しています。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-114">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>

## <a name="using-code"></a><span data-ttu-id="ca2f0-115">コードの使用</span><span class="sxs-lookup"><span data-stu-id="ca2f0-115">Using Code</span></span>

<span data-ttu-id="ca2f0-116">サービスとクライアントの完全なコードは、このトピックの最後にある「使用例」のセクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-116">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>

<span data-ttu-id="ca2f0-117">最初の手順では、コードで <xref:System.ServiceModel.WSHttpBinding> クラスを作成および構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-117">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="ca2f0-118">バインディングでは HTTP トランスポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-118">The binding uses the HTTP transport.</span></span> <span data-ttu-id="ca2f0-119">同じバインディングがクライアント上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-119">The same binding is used on the client.</span></span>

#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="ca2f0-120">Windows 資格情報とメッセージ セキュリティを使用する WSHttpBinding を作成するには</span><span class="sxs-lookup"><span data-stu-id="ca2f0-120">To create a WSHttpBinding that uses Windows credentials and message security</span></span>

1. <span data-ttu-id="ca2f0-121">この手順のコードは、「使用例」のセクションに記載されたサービス コードの `Run` クラスの `Test` メソッドの先頭に挿入されています。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-121">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>

2. <span data-ttu-id="ca2f0-122"><xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-122">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

3. <span data-ttu-id="ca2f0-123"><xref:System.ServiceModel.WSHttpSecurity.Mode%2A> クラスの <xref:System.ServiceModel.WSHttpSecurity> プロパティを <xref:System.ServiceModel.SecurityMode.Message> に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-123">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>

4. <span data-ttu-id="ca2f0-124"><xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> クラスの <xref:System.ServiceModel.MessageSecurityOverHttp> プロパティを <xref:System.ServiceModel.MessageCredentialType.Windows> に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-124">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>

5. <span data-ttu-id="ca2f0-125">この手順で使用するコードは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-125">The code for this procedure is as follows:</span></span>

    [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
    [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]

### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="ca2f0-126">サービスでのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ca2f0-126">Using the Binding in a Service</span></span>

<span data-ttu-id="ca2f0-127">この 2 番目の手順では、自己ホスト型サービスでバインディングを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-127">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="ca2f0-128">ホスティングサービスの詳細については、「[ホスティングサービス](hosting-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-128">For more information about hosting services see [Hosting Services](hosting-services.md).</span></span>

##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="ca2f0-129">サービスでバインディングを使用するには</span><span class="sxs-lookup"><span data-stu-id="ca2f0-129">To use a binding in a service</span></span>

1. <span data-ttu-id="ca2f0-130">前の手順のコードの後に、この手順のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-130">Insert this procedure's code after the code from the preceding procedure.</span></span>

2. <span data-ttu-id="ca2f0-131"><xref:System.Type> という名前の `contractType` 変数を作成し、その変数にインターフェイスの型 (`ICalculator`) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-131">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="ca2f0-132">Visual Basic を使用する場合は、演算子を使用します `GetType` 。 C# を使用する場合は、キーワードを使用し `typeof` ます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-132">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>

3. <span data-ttu-id="ca2f0-133"><xref:System.Type> という名前の 2 つ目の `serviceType` 変数を作成し、その変数に実装されたコントラクトの型 (`Calculator`) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-133">Create a second <xref:System.Type> variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>

4. <span data-ttu-id="ca2f0-134"><xref:System.Uri> という名前で、サービスのベース アドレスが指定された `baseAddress` クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-134">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="ca2f0-135">ベース アドレスには、トランスポートに一致するスキームを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-135">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="ca2f0-136">この場合、トランスポートスキームは HTTP であり、アドレスには、特別な Uniform Resource Identifier (URI) "localhost" とポート番号 (8036)、およびベースエンドポイントアドレス ("serviceModelSamples/") が含まれます `http://localhost:8036/serviceModelSamples/` 。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-136">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/`.</span></span>

5. <span data-ttu-id="ca2f0-137"><xref:System.ServiceModel.ServiceHost> 変数と `serviceType` 変数を指定して、`baseAddress` クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-137">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>

6. <span data-ttu-id="ca2f0-138">`contractType`、バインディング、およびエンドポイント名 (secureCalculator) を使用して、サービスにエンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-138">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="ca2f0-139">クライアントは、サービスへの呼び出しを開始するときに、ベース アドレスとエンドポイント名を連結する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-139">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>

7. <span data-ttu-id="ca2f0-140"><xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> メソッドを呼び出してサービスを起動します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-140">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="ca2f0-141">この手順で使用するコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-141">The code for this procedure is shown here:</span></span>

    [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
    [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]

### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="ca2f0-142">クライアントでのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ca2f0-142">Using the Binding in a Client</span></span>

<span data-ttu-id="ca2f0-143">この手順では、サービスと通信するプロキシの生成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-143">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="ca2f0-144">プロキシは、サービスメタデータを使用してプロキシを作成する[ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)で生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-144">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>

<span data-ttu-id="ca2f0-145">この手順では、サービスと通信するための <xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスも作成され、サービスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-145">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>

<span data-ttu-id="ca2f0-146">この例では、コードだけを使用してクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-146">This example uses only code to create the client.</span></span> <span data-ttu-id="ca2f0-147">この手順の後のセクションに示す構成ファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-147">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>

#### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="ca2f0-148">コードによってクライアントでバインディングを使用するには</span><span class="sxs-lookup"><span data-stu-id="ca2f0-148">To use a binding in a client with code</span></span>

1. <span data-ttu-id="ca2f0-149">SvcUtil.exe ツールを使用して、サービスのメタデータからプロキシ コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-149">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="ca2f0-150">詳細については、「[方法: クライアントを作成](how-to-create-a-wcf-client.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-150">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="ca2f0-151">生成されたプロキシコードはクラスを継承します <xref:System.ServiceModel.ClientBase%601> 。これにより、すべてのクライアントに、WCF サービスと通信するために必要なコンストラクター、メソッド、およびプロパティが確実に与えられます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-151">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="ca2f0-152">この例では、生成されたコードに、`CalculatorClient` インターフェイスを実装した `ICalculator` クラスが追加されるので、サービス コードとの互換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-152">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>

2. <span data-ttu-id="ca2f0-153">この手順のコードは、クライアント プログラムの `Main` メソッドの先頭に挿入します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-153">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>

3. <span data-ttu-id="ca2f0-154"><xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成し、そのセキュリティ モードを `Message` に、そのクライアント資格情報の種類を `Windows` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-154">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="ca2f0-155">この例では、変数に `clientBinding` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-155">The example names the variable `clientBinding`.</span></span>

4. <span data-ttu-id="ca2f0-156"><xref:System.ServiceModel.EndpointAddress> という名前の `serviceAddress` クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-156">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="ca2f0-157">エンドポイント名が連結されたベース アドレスでインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-157">Initialize the instance with the base address concatenated with the endpoint name.</span></span>

5. <span data-ttu-id="ca2f0-158">`serviceAddress` 変数と `clientBinding` 変数を指定して、生成されたクライアント クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-158">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>

6. <span data-ttu-id="ca2f0-159">次のコードに示すように、<xref:System.ServiceModel.ClientBase%601.Open%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-159">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>

7. <span data-ttu-id="ca2f0-160">サービスを呼び出し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-160">Call the service and display the results.</span></span>

    [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
    [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]

## <a name="using-the-configuration-file"></a><span data-ttu-id="ca2f0-161">構成ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="ca2f0-161">Using the Configuration File</span></span>

<span data-ttu-id="ca2f0-162">手順コードを使用してバインディングを作成する代わりに、構成ファイルのバインディング セクションに次のコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-162">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>

<span data-ttu-id="ca2f0-163">サービスがまだ定義されていない場合は、「[サービスの設計と実装](designing-and-implementing-services.md)」および「[サービスの構成](configuring-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-163">If you do not already have a service defined, see [Designing and Implementing Services](designing-and-implementing-services.md), and [Configuring Services](configuring-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ca2f0-164">この構成コードは、サービスとクライアントの両方の構成ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-164">This configuration code is used in both the service and client configuration files.</span></span>

#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="ca2f0-165">構成を使用して Windows ドメインのサービスで転送セキュリティを有効にするには</span><span class="sxs-lookup"><span data-stu-id="ca2f0-165">To enable transfer security on a service in a Windows domain using configuration</span></span>

1. <span data-ttu-id="ca2f0-166">[\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) 構成ファイルの要素セクションに要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-166">Add a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>

2. <span data-ttu-id="ca2f0-167">`binding`<> 要素に <> 要素を追加 `WSHttpBinding` し、属性を `configurationName` アプリケーションに適した値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-167">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>

3. <span data-ttu-id="ca2f0-168"><`security`> 要素を追加し、 `mode` 属性を Message に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-168">Add a <`security`> element and set the `mode` attribute to Message.</span></span>

4. <span data-ttu-id="ca2f0-169"><`message`> 要素を追加し、属性を `clientCredentialType` Windows に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-169">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>

5. <span data-ttu-id="ca2f0-170">サービスの構成ファイルで、`<bindings>` セクションを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-170">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="ca2f0-171">サービス構成ファイルがまだない場合は、「Using binding [To Configure service and](using-bindings-to-configure-services-and-clients.md)client」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-171">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](using-bindings-to-configure-services-and-clients.md).</span></span>

    ```xml
    <bindings>
      <wsHttpBinding>
       <binding name = "wsHttpBinding_Calculator">
         <security mode="Message">
           <message clientCredentialType="Windows"/>
         </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="ca2f0-172">クライアントでのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ca2f0-172">Using the Binding in a Client</span></span>

<span data-ttu-id="ca2f0-173">この手順では、サービスと通信するプロキシと構成ファイルの 2 つのファイルの生成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-173">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="ca2f0-174">また、クライアント上で使用される 3 つ目のファイルであるクライアント プログラムへの変更点についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-174">It also describes changes to the client program, which is the third file used on the client.</span></span>

#### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="ca2f0-175">構成によってクライアントでバインディングを使用するには</span><span class="sxs-lookup"><span data-stu-id="ca2f0-175">To use a binding in a client with configuration</span></span>

1. <span data-ttu-id="ca2f0-176">SvcUtil.exe ツールを使用して、サービスのメタデータからプロキシ コードと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-176">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="ca2f0-177">詳細については、「[方法: クライアントを作成](how-to-create-a-wcf-client.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-177">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

2. <span data-ttu-id="ca2f0-178">[\<bindings>](../configure-apps/file-schema/wcf/bindings.md)生成された構成ファイルのセクションを、前のセクションの構成コードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-178">Replace the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>

3. <span data-ttu-id="ca2f0-179">手順コードは、クライアント プログラムの `Main` メソッドの先頭に挿入します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-179">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>

4. <span data-ttu-id="ca2f0-180">生成されたクライアント クラスのインスタンスを作成します。このとき、構成ファイルのバインディングの名前を入力パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-180">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>

5. <span data-ttu-id="ca2f0-181">次のコードに示すように、<xref:System.ServiceModel.ClientBase%601.Open%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-181">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>

6. <span data-ttu-id="ca2f0-182">サービスを呼び出し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ca2f0-182">Call the service and display the results.</span></span>

    [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]

## <a name="example"></a><span data-ttu-id="ca2f0-183">例</span><span class="sxs-lookup"><span data-stu-id="ca2f0-183">Example</span></span>

[!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]

[!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
[!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]

## <a name="see-also"></a><span data-ttu-id="ca2f0-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca2f0-184">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- [<span data-ttu-id="ca2f0-185">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="ca2f0-185">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="ca2f0-186">方法: クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="ca2f0-186">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="ca2f0-187">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ca2f0-187">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="ca2f0-188">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="ca2f0-188">Security Overview</span></span>](./feature-details/security-overview.md)
