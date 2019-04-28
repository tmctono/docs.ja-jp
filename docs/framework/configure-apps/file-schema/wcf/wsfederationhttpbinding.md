---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 8ed8f62f9415ed556a61ca53f27442a9355d8d7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698851"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="23500-101">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="23500-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="23500-102">WS-Federation をサポートするバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="23500-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="23500-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="23500-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="23500-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="23500-104">\<bindings>\\</span></span>
<span data-ttu-id="23500-105">wsFederationBinding 要素</span><span class="sxs-lookup"><span data-stu-id="23500-105">wsFederationBinding element</span></span>

## <a name="syntax"></a><span data-ttu-id="23500-106">構文</span><span class="sxs-lookup"><span data-stu-id="23500-106">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="23500-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="23500-107">Attributes and Elements</span></span>

<span data-ttu-id="23500-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="23500-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="23500-109">属性</span><span class="sxs-lookup"><span data-stu-id="23500-109">Attributes</span></span>

|<span data-ttu-id="23500-110">属性</span><span class="sxs-lookup"><span data-stu-id="23500-110">Attribute</span></span>|<span data-ttu-id="23500-111">説明</span><span class="sxs-lookup"><span data-stu-id="23500-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="23500-112">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="23500-112">bypassProxyOnLocal</span></span>|<span data-ttu-id="23500-113">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="23500-113">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="23500-114">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="23500-114">The default is `false`.</span></span>|
|<span data-ttu-id="23500-115">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="23500-115">closeTimeout</span></span>|<span data-ttu-id="23500-116">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="23500-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="23500-117">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="23500-118">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="23500-118">The default is 00:01:00.</span></span>|
|<span data-ttu-id="23500-119">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="23500-119">hostnameComparisonMode</span></span>|<span data-ttu-id="23500-120">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="23500-120">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="23500-121">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="23500-121">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="23500-122">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="23500-122">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="23500-123">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="23500-123">maxBufferPoolSize</span></span>|<span data-ttu-id="23500-124">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="23500-124">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="23500-125">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="23500-125">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="23500-126">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="23500-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="23500-127">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="23500-127">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="23500-128">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="23500-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="23500-129">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="23500-129">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="23500-130">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="23500-130">maxReceivedMessageSize</span></span>|<span data-ttu-id="23500-131">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="23500-131">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="23500-132">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="23500-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="23500-133">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="23500-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="23500-134">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="23500-134">The default is 65536.</span></span>|
|<span data-ttu-id="23500-135">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="23500-135">messageEncoding</span></span>|<span data-ttu-id="23500-136">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="23500-136">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="23500-137">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="23500-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23500-138">テキスト:テキスト メッセージ エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="23500-138">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="23500-139">Mtom:Message Transmission 組織 Mechanism 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="23500-139">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="23500-140">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="23500-140">The default is Text.</span></span><br /><br /> <span data-ttu-id="23500-141">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="23500-141">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="23500-142">name</span><span class="sxs-lookup"><span data-stu-id="23500-142">name</span></span>|<span data-ttu-id="23500-143">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="23500-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="23500-144">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="23500-145">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="23500-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="23500-146">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23500-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="23500-147">openTimeout</span><span class="sxs-lookup"><span data-stu-id="23500-147">openTimeout</span></span>|<span data-ttu-id="23500-148">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="23500-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="23500-149">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="23500-150">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="23500-150">The default is 00:01:00.</span></span>|
|<span data-ttu-id="23500-151">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="23500-151">privacyNoticeAt</span></span>|<span data-ttu-id="23500-152">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="23500-152">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="23500-153">PrivacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="23500-153">privacyNoticeVersion</span></span>|<span data-ttu-id="23500-154">現在のプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="23500-154">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="23500-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="23500-155">proxyAddress</span></span>|<span data-ttu-id="23500-156">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="23500-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="23500-157">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-157">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="23500-158">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="23500-158">The default is `null`.</span></span>|
|<span data-ttu-id="23500-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="23500-159">receiveTimeout</span></span>|<span data-ttu-id="23500-160">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="23500-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="23500-161">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="23500-162">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="23500-162">The default is 00:10:00.</span></span>|
|<span data-ttu-id="23500-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="23500-163">sendTimeout</span></span>|<span data-ttu-id="23500-164">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="23500-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="23500-165">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="23500-166">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="23500-166">The default is 00:01:00.</span></span>|
|<span data-ttu-id="23500-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="23500-167">textEncoding</span></span>|<span data-ttu-id="23500-168">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="23500-168">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="23500-169">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="23500-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23500-170">-BigEndianUnicode:Unicode BigEndian エンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="23500-170">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="23500-171">Unicode:16 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="23500-171">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="23500-172">UTF8:8 ビット エンコード</span><span class="sxs-lookup"><span data-stu-id="23500-172">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="23500-173">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="23500-173">The default is UTF8.</span></span> <span data-ttu-id="23500-174">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="23500-174">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="23500-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="23500-175">transactionFlow</span></span>|<span data-ttu-id="23500-176">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="23500-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="23500-177">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="23500-177">The default is `false`.</span></span>|
|<span data-ttu-id="23500-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="23500-178">useDefaultWebProxy</span></span>|<span data-ttu-id="23500-179">システムの自動設定 HTTP プロキシを使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="23500-179">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="23500-180">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-180">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="23500-181">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="23500-181">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="23500-182">子要素</span><span class="sxs-lookup"><span data-stu-id="23500-182">Child Elements</span></span>

|<span data-ttu-id="23500-183">要素</span><span class="sxs-lookup"><span data-stu-id="23500-183">Element</span></span>|<span data-ttu-id="23500-184">説明</span><span class="sxs-lookup"><span data-stu-id="23500-184">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23500-185">\<security></span><span class="sxs-lookup"><span data-stu-id="23500-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="23500-186">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="23500-186">Defines the security settings for the message.</span></span> <span data-ttu-id="23500-187">この要素は <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="23500-187">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="23500-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="23500-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="23500-189">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="23500-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="23500-190">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="23500-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="23500-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="23500-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="23500-192">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="23500-192">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="23500-193">親要素</span><span class="sxs-lookup"><span data-stu-id="23500-193">Parent Elements</span></span>

|<span data-ttu-id="23500-194">要素</span><span class="sxs-lookup"><span data-stu-id="23500-194">Element</span></span>|<span data-ttu-id="23500-195">説明</span><span class="sxs-lookup"><span data-stu-id="23500-195">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23500-196">\<bindings></span><span class="sxs-lookup"><span data-stu-id="23500-196">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="23500-197">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="23500-197">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="23500-198">Remarks</span><span class="sxs-lookup"><span data-stu-id="23500-198">Remarks</span></span>

<span data-ttu-id="23500-199">フェデレーションは、複数のシステム間で認証と承認用の ID を共有する機能です。</span><span class="sxs-lookup"><span data-stu-id="23500-199">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="23500-200">これらの ID は、ユーザーまたはコンピューターを参照できます。</span><span class="sxs-lookup"><span data-stu-id="23500-200">These identities can refer to users or to machines.</span></span> <span data-ttu-id="23500-201">フェデレーション HTTP は、SOAP セキュリティと混合モード セキュリティをサポートしますが、トランスポート セキュリティの単独使用はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="23500-201">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="23500-202">このバインディングでは、Ws-federation プロトコルの Windows Communication Foundation (WCF) のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="23500-202">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="23500-203">このバインディングで構成されたサービスは、HTTP トランスポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-203">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="23500-204">バインドは、バインド要素のスタックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="23500-204">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="23500-205">内の要素のバインディングのスタック</span><span class="sxs-lookup"><span data-stu-id="23500-205">The stack of binding elements in</span></span>

<span data-ttu-id="23500-206">`wsFederationHttpBinding` のバインディング要素のスタックは、`wsHttpBinding` に含まれる</span><span class="sxs-lookup"><span data-stu-id="23500-206">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="23500-207">ときに[\<セキュリティ >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)の既定値に設定されている<xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>します。</span><span class="sxs-lookup"><span data-stu-id="23500-207">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="23500-208">`wsFederationHttpBinding`でメッセージ セキュリティ設定の詳細を制御[\<メッセージ >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="23500-208">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="23500-209">なお、 [\<セキュリティ >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)要素では、get アクセスのみ、バインドが作成されると、バインディングによって使用されるセキュリティを変更ことはできません。</span><span class="sxs-lookup"><span data-stu-id="23500-209">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="23500-210">`wsFederationHttpBinding`も設定し、プライバシーに関する声明が存在する場所の URI を取得する privacyNoticeAt 属性を提供します。</span><span class="sxs-lookup"><span data-stu-id="23500-210">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="23500-211">ポリシーをセキュリティで保護することが、フェデレーション シナリオでは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="23500-211">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="23500-212">ポリシーを悪意のあるユーザーから保護するには、HTTPS などのセキュリティ形式の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23500-212">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="23500-213">フェデレーション シナリオでこのバインディングを使用する場合は、発行済み (SAML) トークンの暗号化に使用するキー、トークンに入れるクレームの種類などの重要情報がサービス ポリシーに含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23500-213">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="23500-214">これが改ざんされると、攻撃者は発行済みトークンのキーを発見してさらに改ざんを行ったり、情報を暴露したりなどの悪意ある行動を取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23500-214">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="23500-215">このような行為を防ぐには、(HTTPS などを使用して) ポリシーをセキュリティで保護し、サービスから安全に取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23500-215">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="23500-216">このバインディングの詳細については、次を参照してください。[方法。WSFederationHttpBinding を作成](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)です。</span><span class="sxs-lookup"><span data-stu-id="23500-216">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="23500-217">例</span><span class="sxs-lookup"><span data-stu-id="23500-217">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="23500-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="23500-218">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="23500-219">方法: WSFederationHttpBinding を作成します。</span><span class="sxs-lookup"><span data-stu-id="23500-219">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="23500-220">バインディング</span><span class="sxs-lookup"><span data-stu-id="23500-220">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="23500-221">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="23500-221">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="23500-222">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="23500-222">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="23500-223">\<binding></span><span class="sxs-lookup"><span data-stu-id="23500-223">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
