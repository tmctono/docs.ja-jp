---
title: '方法: セキュリティで保護されたセッションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: 4464100012fe9b3e1f0e8743707b1dc9a477c3d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205889"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="e20a2-102">方法: セキュリティで保護されたセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="e20a2-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="e20a2-103">例外として、 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)バインドするには、システム指定のバインディングでは、Windows Communication Foundation (WCF) に自動的を使用して、メッセージ セキュリティが有効な場合、セキュリティで保護されたセッションです。</span><span class="sxs-lookup"><span data-stu-id="e20a2-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="e20a2-104">既定では、セキュリティで保護されたセッションは、再利用される Web サーバーで存続します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="e20a2-105">セキュリティで保護されたセッションが確立されると、クライアントとサービスが、セキュリティで保護されたセッションに関連付けられているキーをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="e20a2-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="e20a2-106">メッセージを交換するときは、キャッシュされたキーの識別子のみが交換されます。</span><span class="sxs-lookup"><span data-stu-id="e20a2-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="e20a2-107">Web サーバーが再利用される場合は、Web サーバーが識別子のキャッシュされたキーを取得できないようにキャッシュも再利用されます。</span><span class="sxs-lookup"><span data-stu-id="e20a2-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="e20a2-108">これが発生した場合、例外がクライアントにスローされます。</span><span class="sxs-lookup"><span data-stu-id="e20a2-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="e20a2-109">ステートフルなセキュリティ コンテキスト トークン (SCT: Security Context Token) を使用するセキュリティで保護されたセッションは、再利用される Web サーバーで存続することができます。</span><span class="sxs-lookup"><span data-stu-id="e20a2-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="e20a2-110">詳細については、セキュリティで保護されたセッションでステートフルな SCT を使用して、次を参照してください。[方法。セキュリティ コンテキストを作成、セキュリティで保護されたセッションのトークン](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="e20a2-111">サービスが、システム提供のバインディングの 1 つを使用して、セキュリティで保護されたセッションを使用するように指定するには</span><span class="sxs-lookup"><span data-stu-id="e20a2-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="e20a2-112">メッセージ セキュリティをサポートするシステム提供のバインディングを使用するようにサービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="e20a2-113">例外として、 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)セキュリティで保護されたセッションを使用して WCF メッセージ セキュリティを自動的に使用するシステム指定のバインディングを構成するときに、バインドします。</span><span class="sxs-lookup"><span data-stu-id="e20a2-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="e20a2-114">次の表は、メッセージ セキュリティをサポートするシステム提供のバインディングを示し、そのバインディングでメッセージ セキュリティが既定のセキュリティ機構であるかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="e20a2-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="e20a2-115">システム提供のバインディング</span><span class="sxs-lookup"><span data-stu-id="e20a2-115">System-provided binding</span></span>|<span data-ttu-id="e20a2-116">構成要素</span><span class="sxs-lookup"><span data-stu-id="e20a2-116">Configuration element</span></span>|<span data-ttu-id="e20a2-117">既定でメッセージ セキュリティが有効</span><span class="sxs-lookup"><span data-stu-id="e20a2-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="e20a2-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="e20a2-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="e20a2-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="e20a2-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="e20a2-121">はい</span><span class="sxs-lookup"><span data-stu-id="e20a2-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="e20a2-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="e20a2-123">はい</span><span class="sxs-lookup"><span data-stu-id="e20a2-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="e20a2-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="e20a2-125">はい</span><span class="sxs-lookup"><span data-stu-id="e20a2-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="e20a2-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="e20a2-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="e20a2-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="e20a2-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="e20a2-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="e20a2-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="e20a2-129">No</span></span>|  
  
     <span data-ttu-id="e20a2-130">次のコード例は、という名前のバインドを指定する構成を使用して`wsHttpBinding_Calculator`を使用して、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、メッセージ セキュリティ、およびセキュリティで保護されたセッションです。</span><span class="sxs-lookup"><span data-stu-id="e20a2-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="e20a2-131">次のコード例では、ことを指定します、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、メッセージ セキュリティ、およびセキュリティで保護されたセッションをセキュリティで保護する使用、`secureCalculator`サービス。</span><span class="sxs-lookup"><span data-stu-id="e20a2-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e20a2-132">セキュリティで保護されたセッションをオフにすることができます、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)を設定して、`establishSecurityContext`属性を`false`します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-132">Secure sessions can be turned off for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="e20a2-133">他のシステム提供のバインディングについては、カスタム バインドを作成することでのみ、セキュリティで保護されたセッションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e20a2-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="e20a2-134">カスタム バインドを使用して、サービスでセキュリティで保護されたセッションが使用されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="e20a2-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="e20a2-135">セキュリティで保護されたセッションで SOAP メッセージが保護されるように指定したカスタム バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="e20a2-136">カスタム バインドを作成する方法の詳細については、次を参照してください。[方法。システム指定のバインディングをカスタマイズ](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="e20a2-137">次のコード例で使用されている構成では、セキュリティで保護されたセッションを使用して SOAP メッセージを保護するカスタム バインドを指定しています。</span><span class="sxs-lookup"><span data-stu-id="e20a2-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="e20a2-138">セキュリティで保護されたセッションをブートストラップするための <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 認証モードを使用する、カスタム バインドを作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e20a2-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e20a2-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e20a2-139">See also</span></span>

- [<span data-ttu-id="e20a2-140">WCF のバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="e20a2-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
