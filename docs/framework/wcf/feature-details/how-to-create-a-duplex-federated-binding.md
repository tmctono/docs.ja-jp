---
title: '方法: 双方向フェデレーション バインディングを作成する'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696211"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="69a39-102">方法: 双方向フェデレーション バインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="69a39-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="69a39-103"><xref:System.ServiceModel.WSFederationHttpBinding> はデータグラムと要求/応答メッセージの交換コントラクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="69a39-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="69a39-104">双方向メッセージ交換コントラクトを使用するには、カスタム バインディングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a39-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="69a39-105">次の手順は、構成の中でそれを行う方法を説明します。HTTP と TCP トランスポートにはメッセージ モード セキュリティを、TCP トランスポートには混合モード セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="69a39-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="69a39-106">このトピックの最後に 3 つのバインディングすべてのサンプル コードがあります。</span><span class="sxs-lookup"><span data-stu-id="69a39-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="69a39-107">バインディングはコード内でも作成できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-107">You can also create the binding in code.</span></span> <span data-ttu-id="69a39-108">作成するバインド要素スタックの説明は、次を参照してください。[方法。SecurityBindingElement を使用してカスタム バインディングを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)します。</span><span class="sxs-lookup"><span data-stu-id="69a39-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="69a39-109">HTTP で双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="69a39-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="69a39-110">[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 、構成ファイルのノードを作成、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="69a39-111">内で、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成、 [\<バインド >](../../../../docs/framework/misc/binding.md)を持つ要素、`name`属性に設定`FederationDuplexHttpMessageSecurityBinding`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="69a39-112">内で、 [\<バインド >](../../../../docs/framework/misc/binding.md)要素を作成、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)を持つ要素、`authenticationMode`属性に設定`SecureConversation`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="69a39-113">内で、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成、 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)を持つ要素、`authenticationMode`属性に設定`IssuedTokenForCertificate`または`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="69a39-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="69a39-114">次の[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素は空の作成[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="69a39-115">次の[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素は空の作成[ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="69a39-116">次の[ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素は空の作成[ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="69a39-117">TCP メッセージ セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="69a39-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="69a39-118">[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 、構成ファイルのノードを作成、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="69a39-119">内で、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成、 [\<バインド >](../../../../docs/framework/misc/binding.md)を持つ要素、`name`属性に設定`FederationDuplexTcpMessageSecurityBinding`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="69a39-120">内で、 [\<バインド >](../../../../docs/framework/misc/binding.md)要素を作成、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)を持つ要素、`authenticationMode`属性に設定`SecureConversation`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="69a39-121">内で、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成、 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)を持つ要素、`authenticationMode`属性に設定`IssuedTokenForCertificate`または`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="69a39-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="69a39-122">次の[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素は空の作成[ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="69a39-123">TCP 混合セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="69a39-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="69a39-124">[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 、構成ファイルのノードを作成、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="69a39-125">内で、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成、 [\<バインド >](../../../../docs/framework/misc/binding.md)を持つ要素、`name`属性に設定`FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="69a39-126">内で、 [\<バインド >](../../../../docs/framework/misc/binding.md)要素を作成、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)を持つ要素、`authenticationMode`属性に設定`SecureConversation`します。</span><span class="sxs-lookup"><span data-stu-id="69a39-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="69a39-127">内で、 [\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成、 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)を持つ要素、`authenticationMode`属性に設定`IssuedTokenForCertificate`または`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="69a39-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="69a39-128">次の[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素は空の作成[ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="69a39-129">次の[ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素は空の作成[ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素。</span><span class="sxs-lookup"><span data-stu-id="69a39-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="69a39-130">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="69a39-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="69a39-131">3 つのバインディングの例</span><span class="sxs-lookup"><span data-stu-id="69a39-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="69a39-132">次のコードを構成ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="69a39-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a39-133">例</span><span class="sxs-lookup"><span data-stu-id="69a39-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
