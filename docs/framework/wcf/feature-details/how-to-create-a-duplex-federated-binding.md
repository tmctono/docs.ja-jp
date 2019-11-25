---
title: '方法 : 双方向フェデレーション バインディングを作成する'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141718"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="8e935-102">方法 : 双方向フェデレーション バインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="8e935-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="8e935-103"><xref:System.ServiceModel.WSFederationHttpBinding> はデータグラムと要求/応答メッセージの交換コントラクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8e935-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="8e935-104">双方向メッセージ交換コントラクトを使用するには、カスタム バインディングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e935-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="8e935-105">次の手順は、構成の中でそれを行う方法を説明します。HTTP と TCP トランスポートにはメッセージ モード セキュリティを、TCP トランスポートには混合モード セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e935-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="8e935-106">このトピックの最後に 3 つのバインディングすべてのサンプル コードがあります。</span><span class="sxs-lookup"><span data-stu-id="8e935-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="8e935-107">バインディングはコード内でも作成できます。</span><span class="sxs-lookup"><span data-stu-id="8e935-107">You can also create the binding in code.</span></span> <span data-ttu-id="8e935-108">作成するバインド要素スタックの説明については、「[方法: カスタムバインディングを使用してカスタムバインディングを作成](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e935-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="8e935-109">HTTP で双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="8e935-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="8e935-110">構成ファイルの[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)ノードで、 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="8e935-111">[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素内に、`name` 属性が `FederationDuplexHttpMessageSecurityBinding`に設定された[\<バインド >](../../configure-apps/file-schema/wcf/bindings.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="8e935-112">[\<binding >](../../configure-apps/file-schema/wcf/bindings.md)要素内で、`authenticationMode` 属性が `SecureConversation`に設定された[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="8e935-113">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素内で、`authenticationMode` 属性を `IssuedTokenForCertificate` または `IssuedTokenForSslNegotiated`に設定して、 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="8e935-114">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素の後に、空の[\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="8e935-115">[\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素の後に、空の[\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="8e935-116">[\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素の後に、空の[\<httptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="8e935-117">TCP メッセージ セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="8e935-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="8e935-118">構成ファイルの[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)ノードで、 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="8e935-119">[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素内に、`name` 属性が `FederationDuplexTcpMessageSecurityBinding`に設定された[\<バインド >](../../configure-apps/file-schema/wcf/bindings.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="8e935-120">[\<binding >](../../configure-apps/file-schema/wcf/bindings.md)要素内で、`authenticationMode` 属性が `SecureConversation`に設定された[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="8e935-121">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素内で、`authenticationMode` 属性を `IssuedTokenForCertificate` または `IssuedTokenForSslNegotiated`に設定して、 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="8e935-122">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素に従って、空の[\<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="8e935-123">TCP 混合セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="8e935-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="8e935-124">構成ファイルの[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)ノードで、 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="8e935-125">[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)要素内に、`name` 属性が `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`に設定された[\<バインド >](../../configure-apps/file-schema/wcf/bindings.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="8e935-126">[\<binding >](../../configure-apps/file-schema/wcf/bindings.md)要素内で、`authenticationMode` 属性が `SecureConversation`に設定された[\<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="8e935-127">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素内で、`authenticationMode` 属性を `IssuedTokenForCertificate` または `IssuedTokenForSslNegotiated`に設定して、 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="8e935-128">[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素の後に、空の[\<sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="8e935-129">[\<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素に従って、空の[\<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e935-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8e935-130">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="8e935-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="8e935-131">3 つのバインディングの例</span><span class="sxs-lookup"><span data-stu-id="8e935-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="8e935-132">次のコードを構成ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8e935-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="8e935-133">例</span><span class="sxs-lookup"><span data-stu-id="8e935-133">Example</span></span>

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
