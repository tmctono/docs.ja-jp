---
title: '方法: WSE 3.0 へのアクセス、WCF クライアントとサービス'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 83507a95dbc4bc7499b94a516f569703f21a2726
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855128"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a><span data-ttu-id="a0965-102">方法: WSE 3.0 へのアクセス、WCF クライアントとサービス</span><span class="sxs-lookup"><span data-stu-id="a0965-102">How to: Access a WSE 3.0 Service with a WCF Client</span></span>
<span data-ttu-id="a0965-103">Windows Communication Foundation (WCF) クライアントは、Ws-addressing 仕様の 2004 年 8 月バージョンを使用する WCF クライアントが構成されている場合、Microsoft .NET services のワイヤレベルの互換性のある Web Services Enhancements (WSE) 3.0 が。</span><span class="sxs-lookup"><span data-stu-id="a0965-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements (WSE) 3.0 for Microsoft .NET services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span> <span data-ttu-id="a0965-104">ただし、WSE 3.0 サービスは、メタデータ交換 (MEX) プロトコルをサポートしないので使用すると、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WCF クライアント クラスを作成するセキュリティ設定は適用されませんを生成されました。WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="a0965-104">However, WSE 3.0 services do not support the metadata exchange (MEX) protocol, so when you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client class, the security settings are not applied to the generated WCF client.</span></span> <span data-ttu-id="a0965-105">そのため、セキュリティの設定を指定する必要があります、WCF クライアントが生成された後に、WSE 3.0 サービスが必要であります。</span><span class="sxs-lookup"><span data-stu-id="a0965-105">Therefore, you must specify the security settings that the WSE 3.0 service requires after the WCF client is generated.</span></span>  
  
 <span data-ttu-id="a0965-106">これらのセキュリティ設定を適用するには、カスタム バインドを使用して、WSE 3.0 サービスの要件と WSE 3.0 サービスと WCF クライアントの間の相互運用可能な要件を考慮します。</span><span class="sxs-lookup"><span data-stu-id="a0965-106">You can apply these security settings by using a custom binding to take into account the WSE 3.0 service's requirements and the interoperable requirements between a WSE 3.0 service and a WCF client.</span></span> <span data-ttu-id="a0965-107">これらの相互運用性要件には、前述の 2004 年 8 月版 WS-Addressing 仕様の使用と、WSE 3.0 の既定のメッセージ保護が <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> であることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0965-107">These interoperability requirements include the aforementioned use of the August 2004 WS-Addressing specification and the  WSE 3.0default message protection of <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span> <span data-ttu-id="a0965-108">WCF の既定のメッセージ保護は<xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>します。</span><span class="sxs-lookup"><span data-stu-id="a0965-108">The default message protection for WCF is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="a0965-109">このトピックでは、WSE 3.0 サービスと相互運用する WCF バインドを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0965-109">This topic details how to create a WCF binding that interoperates with a WSE 3.0 service.</span></span> <span data-ttu-id="a0965-110">WCF には、このバインディングが組み込まれているサンプルも用意されています。</span><span class="sxs-lookup"><span data-stu-id="a0965-110">WCF also provides a sample that incorporates this binding.</span></span> <span data-ttu-id="a0965-111">このサンプルの詳細については、次を参照してください。 [ASMX Web サービスとの相互運用](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="a0965-111">For more information about this sample, see [Interoperating with ASMX Web Services](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).</span></span>  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a><span data-ttu-id="a0965-112">WCF クライアントで WSE 3.0 サービスにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="a0965-112">To access a WSE 3.0 Web service with a WCF client</span></span>  
  
1. <span data-ttu-id="a0965-113">実行、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSE 3.0 Web サービスの WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0965-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="a0965-114">WSE 3.0 Web サービスの場合、WCF クライアントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0965-114">For a WSE 3.0 Web service, a WCF client is created.</span></span> <span data-ttu-id="a0965-115">WSE 3.0 は MEX プロトコルをサポートしていないため、このツールを使用して Web サービスのセキュリティ要件を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0965-115">Because WSE 3.0 does not support the MEX protocol, you cannot use the tool to retrieve the security requirements for the Web service.</span></span> <span data-ttu-id="a0965-116">アプリケーション開発者は、クライアントのセキュリティ設定を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0965-116">The application developer must add the security settings for the client.</span></span>  
  
     <span data-ttu-id="a0965-117">WCF クライアントを作成する方法の詳細については、次を参照してください。、[方法。クライアントを作成する](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)します。</span><span class="sxs-lookup"><span data-stu-id="a0965-117">For more information about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="a0965-118">WSE 3.0 Web サービスと通信できるバインディングを表すクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0965-118">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="a0965-119">次のクラスの一部である、 [WSE との相互運用](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)サンプル。</span><span class="sxs-lookup"><span data-stu-id="a0965-119">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample:</span></span>  
  
    1.  <span data-ttu-id="a0965-120"><xref:System.ServiceModel.Channels.Binding> クラスから派生するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0965-120">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="a0965-121">`WseHttpBinding` クラスから派生する、<xref:System.ServiceModel.Channels.Binding> という名前のクラスを作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="a0965-121">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="a0965-122">WSE サービスで使用する WSE 設定不要アサーション、派生キーが必要かどうか、セキュリティで保護されたセッションを使用するかどうか、署名の確認が必要かどうか、およびメッセージ保護設定を指定するプロパティを、このクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0965-122">Add properties to the class that specify the WSE turnkey assertion used by the WSE service, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span> <span data-ttu-id="a0965-123">WSE 3.0 では、設定不要アサーションは、クライアントまたは Web サービスのセキュリティ要件を指定します: WCF のバインドの認証モードと似ています。</span><span class="sxs-lookup"><span data-stu-id="a0965-123">In WSE 3.0, a turnkey assertion specifies the security requirements for a client or Web service—similar to the authentication mode of a binding in WCF.</span></span>  
  
         <span data-ttu-id="a0965-124">WSE 設定不要アサーション、派生キーが必要かどうか、セキュリティで保護されたセッションを使用するかどうか、署名の確認が必要かどうか、およびメッセージ保護設定をそれぞれ指定する、`SecurityAssertion`、`RequireDerivedKeys`、`EstablishSecurityContext`、および `MessageProtectionOrder` の各プロパティを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0965-124">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="a0965-125"><xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> メソッドをオーバーライドして、バインディング プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0965-125">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="a0965-126">`SecurityAssertion` プロパティと `MessageProtectionOrder` プロパティの値を取得することで、トランスポート、メッセージ エンコーディング、メッセージ保護設定を指定するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0965-126">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="a0965-127">クライアントのアプリケーション コードでは、コードを追加してバインディングのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0965-127">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="a0965-128">次のコード例では、ことは、WSE 3.0 で定義されていると、WCF クライアントにそのメッセージの保護と認証の設定が使用する必要がありますを指定します`AnonymousForCertificate`設定不要のセキュリティ アサーション。</span><span class="sxs-lookup"><span data-stu-id="a0965-128">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="a0965-129">また、セキュリティで保護されたセッションと派生キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0965-129">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a0965-130">例</span><span class="sxs-lookup"><span data-stu-id="a0965-130">Example</span></span>  
 <span data-ttu-id="a0965-131">WSE 3.0 の設定不要のセキュリティ アサーションのプロパティに対応するプロパティを公開するカスタムのバインディングを定義するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0965-131">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="a0965-132">という名前のカスタムのバインディング、 `WseHttpBinding`、使用して、WSSecurityAnonymous WSE 3.0 QuickStart サンプルと通信する WCF クライアントのバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0965-132">That custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client that communicates with the WSSecurityAnonymous WSE 3.0 QuickStart sample.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a0965-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0965-133">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="a0965-134">WSE との相互運用</span><span class="sxs-lookup"><span data-stu-id="a0965-134">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
