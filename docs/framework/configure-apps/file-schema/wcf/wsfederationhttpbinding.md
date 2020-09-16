---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: a57b5ff0b4a8186ffc4c01b5e0824100f265551c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557282"
---
# \<wsFederationHttpBinding>

<span data-ttu-id="7d3a6-101">WS-Federation をサポートするバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-101">Defines a binding that supports WS-Federation.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a><span data-ttu-id="7d3a6-102">構文</span><span class="sxs-lookup"><span data-stu-id="7d3a6-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7d3a6-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d3a6-103">Attributes and Elements</span></span>

<span data-ttu-id="7d3a6-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d3a6-105">属性</span><span class="sxs-lookup"><span data-stu-id="7d3a6-105">Attributes</span></span>

|<span data-ttu-id="7d3a6-106">属性</span><span class="sxs-lookup"><span data-stu-id="7d3a6-106">Attribute</span></span>|<span data-ttu-id="7d3a6-107">説明</span><span class="sxs-lookup"><span data-stu-id="7d3a6-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7d3a6-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="7d3a6-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="7d3a6-109">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="7d3a6-110">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-110">The default is `false`.</span></span>|
|<span data-ttu-id="7d3a6-111">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="7d3a6-111">closeTimeout</span></span>|<span data-ttu-id="7d3a6-112">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7d3a6-113">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d3a6-114">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-114">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7d3a6-115">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="7d3a6-115">hostnameComparisonMode</span></span>|<span data-ttu-id="7d3a6-116">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-116">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="7d3a6-117">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-117">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="7d3a6-118">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-118">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="7d3a6-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="7d3a6-119">maxBufferPoolSize</span></span>|<span data-ttu-id="7d3a6-120">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="7d3a6-121">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="7d3a6-122">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="7d3a6-123">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="7d3a6-124">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="7d3a6-125">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="7d3a6-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="7d3a6-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="7d3a6-127">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="7d3a6-128">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="7d3a6-129">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="7d3a6-130">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-130">The default is 65536.</span></span>|
|<span data-ttu-id="7d3a6-131">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="7d3a6-131">messageEncoding</span></span>|<span data-ttu-id="7d3a6-132">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-132">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="7d3a6-133">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7d3a6-134">-Text: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-134">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="7d3a6-135">-Mtom: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-135">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="7d3a6-136">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-136">The default is Text.</span></span><br /><br /> <span data-ttu-id="7d3a6-137">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-137">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="7d3a6-138">name</span><span class="sxs-lookup"><span data-stu-id="7d3a6-138">name</span></span>|<span data-ttu-id="7d3a6-139">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7d3a6-140">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7d3a6-141">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7d3a6-142">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="7d3a6-143">openTimeout</span><span class="sxs-lookup"><span data-stu-id="7d3a6-143">openTimeout</span></span>|<span data-ttu-id="7d3a6-144">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7d3a6-145">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d3a6-146">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-146">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7d3a6-147">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="7d3a6-147">privacyNoticeAt</span></span>|<span data-ttu-id="7d3a6-148">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-148">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="7d3a6-149">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="7d3a6-149">privacyNoticeVersion</span></span>|<span data-ttu-id="7d3a6-150">現在のプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-150">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="7d3a6-151">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="7d3a6-151">proxyAddress</span></span>|<span data-ttu-id="7d3a6-152">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-152">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="7d3a6-153">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-153">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="7d3a6-154">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-154">The default is `null`.</span></span>|
|<span data-ttu-id="7d3a6-155">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7d3a6-155">receiveTimeout</span></span>|<span data-ttu-id="7d3a6-156">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7d3a6-157">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d3a6-158">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-158">The default is 00:10:00.</span></span>|
|<span data-ttu-id="7d3a6-159">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="7d3a6-159">sendTimeout</span></span>|<span data-ttu-id="7d3a6-160">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7d3a6-161">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d3a6-162">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-162">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7d3a6-163">textEncoding</span><span class="sxs-lookup"><span data-stu-id="7d3a6-163">textEncoding</span></span>|<span data-ttu-id="7d3a6-164">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-164">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="7d3a6-165">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-165">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7d3a6-166">-BigEndianUnicode: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-166">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="7d3a6-167">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-167">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="7d3a6-168">-UTF8: 8 ビットエンコーディング</span><span class="sxs-lookup"><span data-stu-id="7d3a6-168">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="7d3a6-169">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-169">The default is UTF8.</span></span> <span data-ttu-id="7d3a6-170">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-170">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="7d3a6-171">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="7d3a6-171">transactionFlow</span></span>|<span data-ttu-id="7d3a6-172">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-172">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="7d3a6-173">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-173">The default is `false`.</span></span>|
|<span data-ttu-id="7d3a6-174">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="7d3a6-174">useDefaultWebProxy</span></span>|<span data-ttu-id="7d3a6-175">システムの自動設定 HTTP プロキシを使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-175">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="7d3a6-176">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-176">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="7d3a6-177">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-177">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7d3a6-178">子要素</span><span class="sxs-lookup"><span data-stu-id="7d3a6-178">Child Elements</span></span>

|<span data-ttu-id="7d3a6-179">要素</span><span class="sxs-lookup"><span data-stu-id="7d3a6-179">Element</span></span>|<span data-ttu-id="7d3a6-180">説明</span><span class="sxs-lookup"><span data-stu-id="7d3a6-180">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="7d3a6-181">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-181">Defines the security settings for the message.</span></span> <span data-ttu-id="7d3a6-182">この要素は <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-182">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="7d3a6-183">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-183">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="7d3a6-184">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-184">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="7d3a6-185">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-185">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7d3a6-186">親要素</span><span class="sxs-lookup"><span data-stu-id="7d3a6-186">Parent Elements</span></span>

|<span data-ttu-id="7d3a6-187">要素</span><span class="sxs-lookup"><span data-stu-id="7d3a6-187">Element</span></span>|<span data-ttu-id="7d3a6-188">説明</span><span class="sxs-lookup"><span data-stu-id="7d3a6-188">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="7d3a6-189">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-189">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7d3a6-190">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d3a6-190">Remarks</span></span>

<span data-ttu-id="7d3a6-191">フェデレーションは、複数のシステム間で認証と承認用の ID を共有する機能です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-191">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="7d3a6-192">これらの ID は、ユーザーまたはコンピューターを参照できます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-192">These identities can refer to users or to machines.</span></span> <span data-ttu-id="7d3a6-193">フェデレーション HTTP は、SOAP セキュリティと混合モード セキュリティをサポートしますが、トランスポート セキュリティの単独使用はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-193">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="7d3a6-194">このバインディングは、WS-FEDERATION プロトコルに対して Windows Communication Foundation (WCF) のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-194">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="7d3a6-195">このバインディングで構成されたサービスは、HTTP トランスポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-195">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="7d3a6-196">バインドは、バインド要素のスタックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-196">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="7d3a6-197">内のバインド要素のスタック</span><span class="sxs-lookup"><span data-stu-id="7d3a6-197">The stack of binding elements in</span></span>

<span data-ttu-id="7d3a6-198">`wsFederationHttpBinding` のバインディング要素のスタックは、`wsHttpBinding` に含まれる</span><span class="sxs-lookup"><span data-stu-id="7d3a6-198">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="7d3a6-199">[\<security>](security-of-wsfederationhttpbinding.md)がの既定値に設定されている場合 <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> 。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-199">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="7d3a6-200">は、の `wsFederationHttpBinding` メッセージセキュリティ設定の詳細を制御し [\<message>](message-element-of-wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-200">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="7d3a6-201">バインディング [\<security>](security-of-wsfederationhttpbinding.md) によって使用されるセキュリティは、バインディングの作成後に変更できないので、要素は get アクセスのみを提供することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-201">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="7d3a6-202">また、には、プライバシーに関する `wsFederationHttpBinding` 声明が存在する場所の URI を設定および取得するための privacyNoticeAt 属性も用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-202">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="7d3a6-203">ポリシーをセキュリティで保護することが、フェデレーション シナリオでは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-203">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="7d3a6-204">ポリシーを悪意のあるユーザーから保護するには、HTTPS などのセキュリティ形式の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-204">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="7d3a6-205">フェデレーション シナリオでこのバインディングを使用する場合は、発行済み (SAML) トークンの暗号化に使用するキー、トークンに入れるクレームの種類などの重要情報がサービス ポリシーに含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-205">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="7d3a6-206">これが改ざんされると、攻撃者は発行済みトークンのキーを発見してさらに改ざんを行ったり、情報を暴露したりなどの悪意ある行動を取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-206">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="7d3a6-207">このような行為を防ぐには、(HTTPS などを使用して) ポリシーをセキュリティで保護し、サービスから安全に取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-207">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="7d3a6-208">このバインディングの詳細については、「 [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d3a6-208">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="7d3a6-209">例</span><span class="sxs-lookup"><span data-stu-id="7d3a6-209">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7d3a6-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d3a6-210">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="7d3a6-211">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="7d3a6-211">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="7d3a6-212">バインド</span><span class="sxs-lookup"><span data-stu-id="7d3a6-212">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7d3a6-213">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="7d3a6-213">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7d3a6-214">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="7d3a6-214">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
