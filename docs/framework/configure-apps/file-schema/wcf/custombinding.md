---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 60ce3cdfd7c78d152c71cdd652532cc96a6be296
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59481120"
---
# <a name="custombinding"></a><span data-ttu-id="79769-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="79769-101">\<customBinding></span></span>

<span data-ttu-id="79769-102">ユーザーのメッセージ スタックを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="79769-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="79769-103">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="79769-103">\<system.serviceModel>\\</span></span>
<span data-ttu-id="79769-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="79769-104">\<bindings>\\</span></span>
<span data-ttu-id="79769-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="79769-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="79769-106">構文</span><span class="sxs-lookup"><span data-stu-id="79769-106">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="79769-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="79769-107">Attributes and Elements</span></span>

<span data-ttu-id="79769-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="79769-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="79769-109">属性</span><span class="sxs-lookup"><span data-stu-id="79769-109">Attributes</span></span>

|<span data-ttu-id="79769-110">属性</span><span class="sxs-lookup"><span data-stu-id="79769-110">Attribute</span></span>|<span data-ttu-id="79769-111">説明</span><span class="sxs-lookup"><span data-stu-id="79769-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="79769-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="79769-112">closeTimeout</span></span>|<span data-ttu-id="79769-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="79769-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="79769-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79769-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="79769-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="79769-116">name</span><span class="sxs-lookup"><span data-stu-id="79769-116">name</span></span>|<span data-ttu-id="79769-117">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="79769-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="79769-118">この値は、カスタム バインディングの識別文字列として機能するユーザー定義文字列です。</span><span class="sxs-lookup"><span data-stu-id="79769-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="79769-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="79769-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="79769-120">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79769-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="79769-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="79769-121">openTimeout</span></span>|<span data-ttu-id="79769-122">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="79769-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="79769-123">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79769-124">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="79769-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="79769-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="79769-125">receiveTimeout</span></span>|<span data-ttu-id="79769-126">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="79769-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="79769-127">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79769-128">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="79769-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="79769-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="79769-129">sendTimeout</span></span>|<span data-ttu-id="79769-130">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="79769-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="79769-131">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79769-132">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="79769-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="79769-133">子要素</span><span class="sxs-lookup"><span data-stu-id="79769-133">Child Elements</span></span>

|<span data-ttu-id="79769-134">要素</span><span class="sxs-lookup"><span data-stu-id="79769-134">Element</span></span>|<span data-ttu-id="79769-135">説明</span><span class="sxs-lookup"><span data-stu-id="79769-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79769-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="79769-136">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="79769-137">カスタム バインドの双方向のメッセージングを指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="79769-138">たとえば HTTP のように、ネイティブでの二重通信を許可しないトランスポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="79769-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="79769-139">これとは対照的に、TCP では、二重通信がネイティブで許可されているので、クライアントにメッセージを返信するためにこのバインディング要素をサービスで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="79769-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="79769-140">クライアントは、サービスのアドレスを公開して、アクセスおよび接続の確立ができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="79769-141">このクライアント アドレスは、`ClientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="79769-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="79769-142">この要素は <xref:System.ServiceModel.Configuration.CompositeDuplexElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="79769-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="79769-143">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="79769-144">PNRP (Peer Name Resolution Protocol) ピア名リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="79769-145">この要素は <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="79769-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="79769-146">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="79769-147">WS-ReliableMessaging の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="79769-148">この要素がカスタム バインドに追加される場合、その結果となるチャネルにより、正確に 1 回の配信保証をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="79769-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="79769-149">この要素は <xref:System.ServiceModel.Configuration.ReliableSessionElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="79769-150">\<security></span><span class="sxs-lookup"><span data-stu-id="79769-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="79769-151">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="79769-152">この要素は <xref:System.ServiceModel.Configuration.SecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="79769-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="79769-153">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="79769-154">SSL ストリーム バインディングのセキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="79769-155">この要素は <xref:System.ServiceModel.Configuration.SslStreamSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="79769-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="79769-156">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="79769-157">バインディングがトランザクション フローをサポートし、プロトコルが `transactionProtocol` 属性によって使用される必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="79769-158">この要素は <xref:System.ServiceModel.Configuration.TransactionFlowElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="79769-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="79769-159">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="79769-160">カスタム バインドのストリーミング セキュリティのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="79769-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="79769-161">この要素は <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="79769-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="79769-162">親要素</span><span class="sxs-lookup"><span data-stu-id="79769-162">Parent Elements</span></span>

|<span data-ttu-id="79769-163">要素</span><span class="sxs-lookup"><span data-stu-id="79769-163">Element</span></span>|<span data-ttu-id="79769-164">説明</span><span class="sxs-lookup"><span data-stu-id="79769-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="79769-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="79769-165">bindings</span></span>|<span data-ttu-id="79769-166">Windows Communication Foundation アプリケーションのすべてのバインディングを含みます。</span><span class="sxs-lookup"><span data-stu-id="79769-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="79769-167">Remarks</span><span class="sxs-lookup"><span data-stu-id="79769-167">Remarks</span></span>

<span data-ttu-id="79769-168">カスタム バインディングを使用すると、WCF メッセージ スタックのフル コントロールが可能になります。</span><span class="sxs-lookup"><span data-stu-id="79769-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="79769-169">特定のエンティティの構成要素を追加した、特別にカスタマイズされたバインディングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79769-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="79769-170">たとえば、ユーザーは `httpsTransport` セクション、`reliableSession` セクション、および `security` セクションを組み合わせて、信頼できるセキュリティで保護された HTTPS ベースのバインディングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79769-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="79769-171">個別のバインディングは、メッセージ スタックを、スタック要素の構成要素をスタックに出現する順序で指定することにより定義します。</span><span class="sxs-lookup"><span data-stu-id="79769-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="79769-172">各要素は、スタック内の 1 つの要素を定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="79769-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="79769-173">各カスタム バインディング内のトランスポート要素は 1 つだけにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79769-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="79769-174">この要素がない場合、メッセージ スタックは不完全です。</span><span class="sxs-lookup"><span data-stu-id="79769-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="79769-175">要素がスタックに出現する順序は重要です。それは、その順序で操作がメッセージに適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="79769-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="79769-176">スタック要素で推奨される順序を次に示します。</span><span class="sxs-lookup"><span data-stu-id="79769-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="79769-177">トランザクション (省略可能)</span><span class="sxs-lookup"><span data-stu-id="79769-177">Transactions (optional)</span></span>

2. <span data-ttu-id="79769-178">リライアブル メッセージ機能 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="79769-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="79769-179">セキュリティ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="79769-179">Security (optional)</span></span>

4. <span data-ttu-id="79769-180">Transport</span><span class="sxs-lookup"><span data-stu-id="79769-180">Transport</span></span>

5. <span data-ttu-id="79769-181">エンコーダー (省略可能)</span><span class="sxs-lookup"><span data-stu-id="79769-181">Encoder (optional)</span></span>

<span data-ttu-id="79769-182">システムが提供するバインディングの中にサービスの要件を満たすものがない場合は、カスタム バインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="79769-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="79769-183">たとえば、カスタム バインドを使用すると、サービス エンドポイントで新しいトランスポートや新しいエンコーダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="79769-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="79769-184">カスタム バインドは、特定の順序で "積み重ねられている" バインド要素のコレクションから <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> の 1 つを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="79769-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="79769-185">最上位にあるのは、トランザクションのフローを可能にするオプションの <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> です。</span><span class="sxs-lookup"><span data-stu-id="79769-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="79769-186">その次にあるのは、WS-ReliableMessaging 仕様で定義されているセッションおよび順序指定のメカニズムを提供するオプションの <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> です。</span><span class="sxs-lookup"><span data-stu-id="79769-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="79769-187">このセッションの概念は、SOAP およびトランスポート中継局を通過できます。</span><span class="sxs-lookup"><span data-stu-id="79769-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="79769-188">その次にあるのは、承認、認証、保護、機密性などのセキュリティ機能を提供するオプションのセキュリティ バインド要素です。</span><span class="sxs-lookup"><span data-stu-id="79769-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="79769-189">次のセキュリティ バインド要素は、Windows Communication Foundation (WCF) によって用意されています。</span><span class="sxs-lookup"><span data-stu-id="79769-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="79769-190">その次にあるのは、バインド要素によって指定されるオプションのメッセージ パターンです。</span><span class="sxs-lookup"><span data-stu-id="79769-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="79769-191">その次にあるのは、オプションのトランスポート アップグレード/ヘルパー バインド要素です。</span><span class="sxs-lookup"><span data-stu-id="79769-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="79769-192">その次にあるのは、必須のメッセージ エンコード バインド要素です。</span><span class="sxs-lookup"><span data-stu-id="79769-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="79769-193">独自のトランスポートを使用することも、以下のメッセージ エンコード バインドのいずれかを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="79769-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="79769-194">最下位には、必須のトランスポート要素があります。</span><span class="sxs-lookup"><span data-stu-id="79769-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="79769-195">独自のトランスポートを使用して、または Windows Communication Foundation (WCF) によって提供される要素のバインディングのトランスポートのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="79769-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="79769-196">各層のオプションの概要を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="79769-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="79769-197">レイヤー</span><span class="sxs-lookup"><span data-stu-id="79769-197">Layer</span></span>|<span data-ttu-id="79769-198">オプション</span><span class="sxs-lookup"><span data-stu-id="79769-198">Options</span></span>|<span data-ttu-id="79769-199">必須</span><span class="sxs-lookup"><span data-stu-id="79769-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="79769-200">トランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="79769-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="79769-201">Ｘ</span><span class="sxs-lookup"><span data-stu-id="79769-201">No</span></span>|
|<span data-ttu-id="79769-202">信頼性</span><span class="sxs-lookup"><span data-stu-id="79769-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="79769-203">Ｘ</span><span class="sxs-lookup"><span data-stu-id="79769-203">No</span></span>|
|<span data-ttu-id="79769-204">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="79769-204">Security</span></span>|<span data-ttu-id="79769-205">同期、非同期、トランスポート レベル</span><span class="sxs-lookup"><span data-stu-id="79769-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="79769-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="79769-206">No</span></span>|
|<span data-ttu-id="79769-207">形状の変更</span><span class="sxs-lookup"><span data-stu-id="79769-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="79769-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="79769-208">No</span></span>|
|<span data-ttu-id="79769-209">トランスポートのアップグレード</span><span class="sxs-lookup"><span data-stu-id="79769-209">Transport Upgrades</span></span>|<span data-ttu-id="79769-210">SSL ストリーム、Windows ストリーム、ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="79769-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="79769-211">いいえ</span><span class="sxs-lookup"><span data-stu-id="79769-211">No</span></span>|
|<span data-ttu-id="79769-212">エンコーディング</span><span class="sxs-lookup"><span data-stu-id="79769-212">Encoding</span></span>|<span data-ttu-id="79769-213">テキスト、バイナリ、MTOM、カスタム</span><span class="sxs-lookup"><span data-stu-id="79769-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="79769-214">[はい]</span><span class="sxs-lookup"><span data-stu-id="79769-214">Yes</span></span>|
|<span data-ttu-id="79769-215">Transport</span><span class="sxs-lookup"><span data-stu-id="79769-215">Transport</span></span>|<span data-ttu-id="79769-216">TCP、名前付きパイプ、HTTP、HTTPS、MSMQ のフレーバー、カスタム</span><span class="sxs-lookup"><span data-stu-id="79769-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="79769-217">はい</span><span class="sxs-lookup"><span data-stu-id="79769-217">Yes</span></span>|

<span data-ttu-id="79769-218">さらに、独自のバインド要素を定義し、それを定義済みの層のいずれかの間に挿入できます。</span><span class="sxs-lookup"><span data-stu-id="79769-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="79769-219">カスタム システム指定のバインディングを変更するバインドを使用する方法の詳細については、次を参照してください。[方法。システム指定のバインディングをカスタマイズ](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)します。</span><span class="sxs-lookup"><span data-stu-id="79769-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79769-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="79769-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="79769-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="79769-221">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="79769-222">バインディング</span><span class="sxs-lookup"><span data-stu-id="79769-222">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="79769-223">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="79769-223">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="79769-224">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="79769-224">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="79769-225">customBinding 要素</span><span class="sxs-lookup"><span data-stu-id="79769-225">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="79769-226">バインディング</span><span class="sxs-lookup"><span data-stu-id="79769-226">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="79769-227">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="79769-227">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="79769-228">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="79769-228">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
