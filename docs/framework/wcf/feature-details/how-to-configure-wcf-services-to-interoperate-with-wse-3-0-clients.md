---
title: '方法: WCF サービスと WSE 3.0 クライアントを相互運用するために構成する'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 600b9c28d92f9e2b6e4d586b052cc5762d591521
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599062"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="6cca6-102">方法: WCF サービスと WSE 3.0 クライアントを相互運用するために構成する</span><span class="sxs-lookup"><span data-stu-id="6cca6-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="6cca6-103">Windows Communication Foundation (WCF) サービスは、WCF サービスが WS-ADDRESSING 仕様の8月2004バージョンを使用するように構成されている場合に、Web サービス拡張 Microsoft .NET 3.0 (WSE) クライアントとのワイヤレベルの互換性があります。</span><span class="sxs-lookup"><span data-stu-id="6cca6-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="6cca6-104">WCF サービスを WSE 3.0 クライアントと相互運用できるようにするには</span><span class="sxs-lookup"><span data-stu-id="6cca6-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="6cca6-105">WCF サービスのカスタムバインドを定義します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-105">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="6cca6-106">メッセージ エンコーディングに 2004 年 8 月版の WS-Addressing 仕様が使用されるように指定するには、カスタム バインディングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cca6-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="6cca6-107">[\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) サービスの構成ファイルのに子を追加します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-107">Add a child [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="6cca6-108">にを追加し、属性を設定することにより、バインディングの名前を指定し [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) `name` ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-108">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="6cca6-109">に子を追加することによって、WSE 3.0 と互換性のあるメッセージをセキュリティで保護するために使用する認証モードと WS-SECURITY 仕様のバージョンを指定し [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="6cca6-110">認証モードを設定するには、 `authenticationMode` の属性を設定し [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-110">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="6cca6-111">認証モードは、WSE 3.0 の設定不要のセキュリティ アサーションとほぼ同等です。</span><span class="sxs-lookup"><span data-stu-id="6cca6-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="6cca6-112">次の表では、WCF の認証モードを WSE 3.0 のターンキーセキュリティアサーションにマップします。</span><span class="sxs-lookup"><span data-stu-id="6cca6-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="6cca6-113">WCF 認証モード</span><span class="sxs-lookup"><span data-stu-id="6cca6-113">WCF Authentication Mode</span></span>|<span data-ttu-id="6cca6-114">WSE 3.0 の設定不要のセキュリティ アサーション</span><span class="sxs-lookup"><span data-stu-id="6cca6-114">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="6cca6-115">\*とターンキーのセキュリティアサーションの主な違いの1つ `mutualCertificate10Security` `mutualCertificate11Security` は、WSE が SOAP メッセージをセキュリティで保護するために使用する ws-security 仕様のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="6cca6-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="6cca6-116">`mutualCertificate10Security` では WS-Security 1.0 が使用され、`mutualCertificate11Security` では WS-Security 1.1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="6cca6-117">WCF では、の属性で、WS-SECURITY 仕様のバージョンを指定し `messageSecurityVersion` [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="6cca6-118">SOAP メッセージのセキュリティ保護に使用する WS-SECURITY 仕様のバージョンを設定するには、 `messageSecurityVersion` の属性を設定し [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="6cca6-119">WSE 3.0 と相互運用するには、`messageSecurityVersion` 属性の値を <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="6cca6-120">を追加し、を [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) その値に設定することによって、WCF で ws-addressing 仕様の8月2004バージョンが使用されるように指定し `messageVersion` <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6cca6-121">SOAP 1.2 の使用時には、`messageVersion` 属性を <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="6cca6-122">サービスがカスタム バインドを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-122">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="6cca6-123">`binding`要素の属性 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) をに設定 `customBinding` します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-123">Set the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="6cca6-124">`bindingConfiguration`要素の属性 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) を `name` 、カスタムバインドのの属性で指定された値に設定し [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="6cca6-125">例</span><span class="sxs-lookup"><span data-stu-id="6cca6-125">Example</span></span>

<span data-ttu-id="6cca6-126">次のコード例では、`Service.HelloWorldService` が WSE 3.0 クライアントと相互運用するためにカスタム バインドを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6cca6-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="6cca6-127">カスタム バインドには 2004 年 8 月版の WS-Addressing が指定され、WS-Security 1.1 の一連の仕様が、交換されるメッセージのエンコードに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="6cca6-128">メッセージは、<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 認証モードを使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="6cca6-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <services>
      <service
        behaviorConfiguration="ServiceBehavior"
        name="Service.HelloWorldService">
        <endpoint binding="customBinding" address=""
          bindingConfiguration="ServiceBinding"
          contract="Service.IHelloWorld"></endpoint>
      </service>
    </services>

    <bindings>
      <customBinding>
        <binding name="ServiceBinding">
          <security authenticationMode="AnonymousForCertificate"
                  messageProtectionOrder="SignBeforeEncrypt"
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"
                  requireDerivedKeys="false">
          </security>
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>
          <httpTransport/>
        </binding>
      </customBinding>
    </bindings>
    <behaviors>
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">
        <serviceCredentials>
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>
        </serviceCredentials>
      </behavior>
    </behaviors>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6cca6-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cca6-129">See also</span></span>

- [<span data-ttu-id="6cca6-130">方法: システム指定のバインディングをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6cca6-130">How to: Customize a System-Provided Binding</span></span>](../extending/how-to-customize-a-system-provided-binding.md)
