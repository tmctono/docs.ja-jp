---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 77b1383c1fcd3e867e6cef0ae5507b3a2ff8a80d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371386"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="9e5aa-101">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9e5aa-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="9e5aa-102">派生したセキュリティで保護された相互運用可能なバインディング[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)フェデレーション セキュリティをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>

<span data-ttu-id="9e5aa-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="9e5aa-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="9e5aa-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="9e5aa-104">\<bindings>\\</span></span>
<span data-ttu-id="9e5aa-105">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9e5aa-105">\<ws2007FederationHttpBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="9e5aa-106">構文</span><span class="sxs-lookup"><span data-stu-id="9e5aa-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9e5aa-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9e5aa-107">Attributes and Elements</span></span>

<span data-ttu-id="9e5aa-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e5aa-109">属性</span><span class="sxs-lookup"><span data-stu-id="9e5aa-109">Attributes</span></span>

|<span data-ttu-id="9e5aa-110">属性</span><span class="sxs-lookup"><span data-stu-id="9e5aa-110">Attribute</span></span>|<span data-ttu-id="9e5aa-111">説明</span><span class="sxs-lookup"><span data-stu-id="9e5aa-111">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="9e5aa-112">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="9e5aa-113">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-113">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="9e5aa-114">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9e5aa-115">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e5aa-116">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-116">The default is 00:01:00.</span></span>|
|`hostnameComparisonMode`|<span data-ttu-id="9e5aa-117">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="9e5aa-118">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="9e5aa-119">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="9e5aa-120">このバインドに使用するバッファー プールの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9e5aa-121">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="9e5aa-122">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="9e5aa-123">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="9e5aa-124">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="9e5aa-125">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="9e5aa-126">チャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) が、このバインドを使用してバイト単位で設定されました。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-126">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="9e5aa-127">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-127">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="9e5aa-128">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9e5aa-129">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-129">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="9e5aa-130">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="9e5aa-131">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9e5aa-132">テキスト:テキスト メッセージ エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-132">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="9e5aa-133">Mtom:Message Transmission 組織 Mechanism 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-133">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="9e5aa-134">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-134">The default is Text.</span></span><br /><br /> <span data-ttu-id="9e5aa-135">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="9e5aa-136">バインドの構成名。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-136">The configuration name of the binding.</span></span> <span data-ttu-id="9e5aa-137">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9e5aa-138">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-138">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9e5aa-139">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="9e5aa-140">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9e5aa-141">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e5aa-142">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-142">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="9e5aa-143">プライバシーに関する声明の場所を示す URI。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-143">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="9e5aa-144">現在のプライバシーに関する声明のバージョン。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-144">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="9e5aa-145">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-145">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="9e5aa-146">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-146">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="9e5aa-147">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-147">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="9e5aa-148">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9e5aa-149">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e5aa-150">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-150">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="9e5aa-151">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9e5aa-152">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e5aa-153">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-153">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="9e5aa-154">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-154">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9e5aa-155">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-155">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9e5aa-156">-BigEndianUnicode:Unicode ビッグ エンディアン エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-156">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="9e5aa-157">Unicode:16 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-157">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="9e5aa-158">UTF8:8 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-158">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="9e5aa-159">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-159">The default is UTF8.</span></span> <span data-ttu-id="9e5aa-160">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-160">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="9e5aa-161">バインドが WS-Transactions のフローをサポートするかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-161">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="9e5aa-162">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-162">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="9e5aa-163">システムの自動設定 HTTP プロキシを使用するかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-163">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="9e5aa-164">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-164">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="9e5aa-165">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-165">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9e5aa-166">子要素</span><span class="sxs-lookup"><span data-stu-id="9e5aa-166">Child Elements</span></span>

|<span data-ttu-id="9e5aa-167">要素</span><span class="sxs-lookup"><span data-stu-id="9e5aa-167">Element</span></span>|<span data-ttu-id="9e5aa-168">説明</span><span class="sxs-lookup"><span data-stu-id="9e5aa-168">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e5aa-169">\<security></span><span class="sxs-lookup"><span data-stu-id="9e5aa-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="9e5aa-170">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-170">Defines the security settings for the message.</span></span> <span data-ttu-id="9e5aa-171">この要素は <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-171">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="9e5aa-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9e5aa-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="9e5aa-173">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-173">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9e5aa-174">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-174">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="9e5aa-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9e5aa-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="9e5aa-176">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-176">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9e5aa-177">親要素</span><span class="sxs-lookup"><span data-stu-id="9e5aa-177">Parent Elements</span></span>

|<span data-ttu-id="9e5aa-178">要素</span><span class="sxs-lookup"><span data-stu-id="9e5aa-178">Element</span></span>|<span data-ttu-id="9e5aa-179">説明</span><span class="sxs-lookup"><span data-stu-id="9e5aa-179">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e5aa-180">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9e5aa-180">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="9e5aa-181">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-181">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e5aa-182">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e5aa-182">Remarks</span></span>

<span data-ttu-id="9e5aa-183">フェデレーションは、複数の企業または信頼するドメインで認証と承認用の ID を共有する機能です。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-183">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="9e5aa-184">フェデレーションは、WS-Trust プロトコルを使用して、ID 形式を、ある信頼するドメインから別の信頼するドメインにマップします。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-184">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="9e5aa-185">フェデレーション HTTP バインドは、SOAP セキュリティと混合モード セキュリティをサポートしますが、トランスポート セキュリティの単独使用はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-185">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="9e5aa-186">このバインディングで構成されたサービスは、HTTP トランスポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-186">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="9e5aa-187">詳細については、次を参照してください。 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="9e5aa-187">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e5aa-188">例</span><span class="sxs-lookup"><span data-stu-id="9e5aa-188">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9e5aa-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e5aa-189">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="9e5aa-190">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9e5aa-190">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="9e5aa-191">バインディング</span><span class="sxs-lookup"><span data-stu-id="9e5aa-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9e5aa-192">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9e5aa-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9e5aa-193">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9e5aa-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9e5aa-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="9e5aa-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
