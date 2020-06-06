---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139315"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="51ef5-101">から派生し、フェデレーションセキュリティをサポートする、セキュリティで保護された相互運用可能なバインディング [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="51ef5-101">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="51ef5-102">構文</span><span class="sxs-lookup"><span data-stu-id="51ef5-102">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
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
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
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
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51ef5-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="51ef5-103">Attributes and Elements</span></span>

<span data-ttu-id="51ef5-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="51ef5-105">属性</span><span class="sxs-lookup"><span data-stu-id="51ef5-105">Attributes</span></span>

|<span data-ttu-id="51ef5-106">属性</span><span class="sxs-lookup"><span data-stu-id="51ef5-106">Attribute</span></span>|<span data-ttu-id="51ef5-107">説明</span><span class="sxs-lookup"><span data-stu-id="51ef5-107">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="51ef5-108">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="51ef5-108">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="51ef5-109">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-109">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="51ef5-110">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="51ef5-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="51ef5-111">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51ef5-112">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-112">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="51ef5-113">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-113">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="51ef5-114">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-114">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="51ef5-115">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-115">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="51ef5-116">このバインドに使用するバッファー プールの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="51ef5-116">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="51ef5-117">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="51ef5-118">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="51ef5-119">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="51ef5-120">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="51ef5-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="51ef5-121">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="51ef5-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="51ef5-122">チャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) が、このバインドを使用してバイト単位で設定されました。</span><span class="sxs-lookup"><span data-stu-id="51ef5-122">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="51ef5-123">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-123">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="51ef5-124">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="51ef5-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="51ef5-125">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-125">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="51ef5-126">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-126">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="51ef5-127">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51ef5-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="51ef5-128">-Text: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-128">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="51ef5-129">-Mtom: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-129">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="51ef5-130">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-130">The default is Text.</span></span><br /><br /> <span data-ttu-id="51ef5-131">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-131">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="51ef5-132">バインドの構成名。</span><span class="sxs-lookup"><span data-stu-id="51ef5-132">The configuration name of the binding.</span></span> <span data-ttu-id="51ef5-133">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="51ef5-134">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51ef5-134">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="51ef5-135">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ef5-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="51ef5-136">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="51ef5-137">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51ef5-138">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-138">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="51ef5-139">プライバシーに関する声明の場所を示す URI。</span><span class="sxs-lookup"><span data-stu-id="51ef5-139">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="51ef5-140">現在のプライバシーに関する声明のバージョン。</span><span class="sxs-lookup"><span data-stu-id="51ef5-140">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="51ef5-141">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="51ef5-141">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="51ef5-142">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-142">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="51ef5-143">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-143">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="51ef5-144">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="51ef5-145">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51ef5-146">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-146">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="51ef5-147">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="51ef5-148">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51ef5-149">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-149">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="51ef5-150">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-150">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="51ef5-151">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51ef5-151">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="51ef5-152">-BigEndianUnicode: Unicode ビッグエンディアンエンコーディング。</span><span class="sxs-lookup"><span data-stu-id="51ef5-152">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="51ef5-153">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="51ef5-153">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="51ef5-154">-UTF8: 8 ビットエンコーディング。</span><span class="sxs-lookup"><span data-stu-id="51ef5-154">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="51ef5-155">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-155">The default is UTF8.</span></span> <span data-ttu-id="51ef5-156">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-156">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="51ef5-157">バインドが WS-Transactions のフローをサポートするかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="51ef5-157">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="51ef5-158">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-158">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="51ef5-159">システムの自動設定 HTTP プロキシを使用するかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="51ef5-159">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="51ef5-160">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-160">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="51ef5-161">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-161">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="51ef5-162">子要素</span><span class="sxs-lookup"><span data-stu-id="51ef5-162">Child Elements</span></span>

|<span data-ttu-id="51ef5-163">要素</span><span class="sxs-lookup"><span data-stu-id="51ef5-163">Element</span></span>|<span data-ttu-id="51ef5-164">Description</span><span class="sxs-lookup"><span data-stu-id="51ef5-164">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="51ef5-165">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-165">Defines the security settings for the message.</span></span> <span data-ttu-id="51ef5-166">この要素は <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-166">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="51ef5-167">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-167">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="51ef5-168">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-168">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="51ef5-169">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="51ef5-169">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="51ef5-170">親要素</span><span class="sxs-lookup"><span data-stu-id="51ef5-170">Parent Elements</span></span>

|<span data-ttu-id="51ef5-171">要素</span><span class="sxs-lookup"><span data-stu-id="51ef5-171">Element</span></span>|<span data-ttu-id="51ef5-172">Description</span><span class="sxs-lookup"><span data-stu-id="51ef5-172">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="51ef5-173">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="51ef5-173">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="51ef5-174">解説</span><span class="sxs-lookup"><span data-stu-id="51ef5-174">Remarks</span></span>

<span data-ttu-id="51ef5-175">フェデレーションは、複数の企業または信頼するドメインで認証と承認用の ID を共有する機能です。</span><span class="sxs-lookup"><span data-stu-id="51ef5-175">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="51ef5-176">フェデレーションは、WS-Trust プロトコルを使用して、ID 形式を、ある信頼するドメインから別の信頼するドメインにマップします。</span><span class="sxs-lookup"><span data-stu-id="51ef5-176">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="51ef5-177">フェデレーション HTTP バインドは、SOAP セキュリティと混合モード セキュリティをサポートしますが、トランスポート セキュリティの単独使用はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="51ef5-177">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="51ef5-178">このバインディングで構成されたサービスは、HTTP トランスポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ef5-178">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="51ef5-179">詳細については、「[\<wsFederationHttpBinding>](wsfederationhttpbinding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ef5-179">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="51ef5-180">例</span><span class="sxs-lookup"><span data-stu-id="51ef5-180">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="51ef5-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="51ef5-181">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="51ef5-182">バインド</span><span class="sxs-lookup"><span data-stu-id="51ef5-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="51ef5-183">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="51ef5-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="51ef5-184">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="51ef5-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
