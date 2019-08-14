---
title: '方法: 双方向フェデレーション バインディングを作成する'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972056"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="bdac4-102">方法: 双方向フェデレーション バインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="bdac4-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="bdac4-103"><xref:System.ServiceModel.WSFederationHttpBinding> はデータグラムと要求/応答メッセージの交換コントラクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bdac4-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="bdac4-104">双方向メッセージ交換コントラクトを使用するには、カスタム バインディングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdac4-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="bdac4-105">次の手順は、構成の中でそれを行う方法を説明します。HTTP と TCP トランスポートにはメッセージ モード セキュリティを、TCP トランスポートには混合モード セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="bdac4-106">このトピックの最後に 3 つのバインディングすべてのサンプル コードがあります。</span><span class="sxs-lookup"><span data-stu-id="bdac4-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="bdac4-107">バインディングはコード内でも作成できます。</span><span class="sxs-lookup"><span data-stu-id="bdac4-107">You can also create the binding in code.</span></span> <span data-ttu-id="bdac4-108">作成するバインド要素スタックの説明については、 [「方法:の設定を使用してカスタム](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="bdac4-109">HTTP で双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="bdac4-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="bdac4-110">構成ファイルの  [バインド>ノードで、customBinding>要素を作成します。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="bdac4-111">CustomBinding > `name` `FederationDuplexHttpMessageSecurityBinding`要素内で、属性がに設定された[バインド > 要素を作成します。 \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="bdac4-112">バインド > `authenticationMode` `SecureConversation`要素内で、属性がに設定された[セキュリティ > 要素を作成します。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="bdac4-113">`authenticationMode` `IssuedTokenForCertificate` [ Security>\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素内で、属性をまたは`IssuedTokenForSslNegotiated`に設定して、secureConversationBootstrap > 要素を作成します。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="bdac4-114">[ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素の後に、空[ \<の compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="bdac4-115">[ \<CompositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)要素の後に、空[ \<の oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="bdac4-116">[ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)要素の後に、空[ \<の httptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="bdac4-117">TCP メッセージ セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="bdac4-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="bdac4-118">構成ファイルの  [バインド>ノードで、customBinding>要素を作成します。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="bdac4-119">CustomBinding > `name` `FederationDuplexTcpMessageSecurityBinding`要素内で、属性がに設定された[バインド > 要素を作成します。 \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="bdac4-120">バインド > `authenticationMode` `SecureConversation`要素内で、属性がに設定された[セキュリティ > 要素を作成します。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="bdac4-121">`authenticationMode` `IssuedTokenForCertificate` [ Security>\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素内で、属性をまたは`IssuedTokenForSslNegotiated`に設定して、secureConversationBootstrap > 要素を作成します。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="bdac4-122">[ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素の後に、空[ \<の tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="bdac4-123">TCP 混合セキュリティ モードで双方向カスタム フェデレーション バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="bdac4-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="bdac4-124">構成ファイルの  [バインド>ノードで、customBinding>要素を作成します。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="bdac4-125">CustomBinding > `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`要素内で、属性がに設定された[バインド > 要素を作成します。 \<](../../../../docs/framework/misc/binding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="bdac4-126">バインド > `authenticationMode` `SecureConversation`要素内で、属性がに設定された[セキュリティ > 要素を作成します。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="bdac4-127">`authenticationMode` `IssuedTokenForCertificate` [ Security>\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素内で、属性をまたは`IssuedTokenForSslNegotiated`に設定して、secureConversationBootstrap > 要素を作成します。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="bdac4-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="bdac4-128">[ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)要素の後に、空[ \<の sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="bdac4-129">[ \<Sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)要素の後に、空[ \<の tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="bdac4-130">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="bdac4-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="bdac4-131">3 つのバインディングの例</span><span class="sxs-lookup"><span data-stu-id="bdac4-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="bdac4-132">次のコードを構成ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="bdac4-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="bdac4-133">例</span><span class="sxs-lookup"><span data-stu-id="bdac4-133">Example</span></span>

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
