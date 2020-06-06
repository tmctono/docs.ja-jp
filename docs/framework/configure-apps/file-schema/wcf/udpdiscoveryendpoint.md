---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: 1729255c68c75f824b8cd8c87f106a4a9b3550f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854893"
---
# \<udpDiscoveryEndpoint>
<span data-ttu-id="98c43-101">この構成要素は、UDP マルチキャスト バインディングを使用した探索操作用に事前に構成される標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="98c43-101">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="98c43-102">このエンドポイントには固定コントラクトがあり、WS-Discovery プロトコルの 2 つのバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="98c43-102">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="98c43-103">また、WS-Discovery の仕様 (WS-Discovery April 2005 または WS-Discovery V1.1) に規定された固定 UDP バインディングと既定のアドレスも備えています。</span><span class="sxs-lookup"><span data-stu-id="98c43-103">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpDiscoveryEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="98c43-104">構文</span><span class="sxs-lookup"><span data-stu-id="98c43-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98c43-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="98c43-105">Attributes and Elements</span></span>  
 <span data-ttu-id="98c43-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="98c43-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98c43-107">属性</span><span class="sxs-lookup"><span data-stu-id="98c43-107">Attributes</span></span>  
  
|<span data-ttu-id="98c43-108">属性</span><span class="sxs-lookup"><span data-stu-id="98c43-108">Attribute</span></span>|<span data-ttu-id="98c43-109">説明</span><span class="sxs-lookup"><span data-stu-id="98c43-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98c43-110">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="98c43-110">discoveryMode</span></span>|<span data-ttu-id="98c43-111">探索プロトコルのモードを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="98c43-111">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="98c43-112">有効な値は "アドホック" および "マネージ" です。</span><span class="sxs-lookup"><span data-stu-id="98c43-112">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="98c43-113">マネージド モードでは、プロトコルは Discoverable サービスのリポジトリとして機能する Discovery Proxy に依存します。</span><span class="sxs-lookup"><span data-stu-id="98c43-113">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="98c43-114">アドホック モードでは、プロトコルは UDP マルチキャスト メカニズムを使用して利用可能なサービスを探索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c43-114">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="98c43-115">この値は、<xref:System.ServiceModel.Discovery.ServiceDiscoveryMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="98c43-115">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="98c43-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="98c43-116">discoveryVersion</span></span>|<span data-ttu-id="98c43-117">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="98c43-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="98c43-118">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="98c43-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="98c43-119">この値は、<xref:System.ServiceModel.Discovery.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="98c43-119">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="98c43-120">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="98c43-120">maxResponseDelay</span></span>|<span data-ttu-id="98c43-121">Discovery プロトコルが Probe Match や Resolve Match などのメッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="98c43-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="98c43-122">すべての ProbeMatch が同時に送信されると、ネットワーク ストームが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="98c43-122">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="98c43-123">これを防ぐために、各 ProbeMatch はランダムな時間だけ待機して送信されます。</span><span class="sxs-lookup"><span data-stu-id="98c43-123">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="98c43-124">ランダムな待機時間は、0 からこの属性に設定された値の範囲内で設定されます。</span><span class="sxs-lookup"><span data-stu-id="98c43-124">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="98c43-125">この属性を 0 に設定すると、ProbeMatch メッセージは待機せずに短いループで送信されます。</span><span class="sxs-lookup"><span data-stu-id="98c43-125">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="98c43-126">それ以外の場合は、ProbeMatch メッセージはランダムな時間だけ待機して送信されます。すべての ProbeMatch メッセージの送信にかかる合計時間が maxResponseDelay を超えることはありません。</span><span class="sxs-lookup"><span data-stu-id="98c43-126">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="98c43-127">この値はサービスのみに関連するもので、クライアントが使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="98c43-127">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="98c43-128">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="98c43-128">multicastAddress</span></span>|<span data-ttu-id="98c43-129">探索メッセージの送受信に使用するマルチキャスト アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="98c43-129">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="98c43-130">既定値は、プロトコル仕様に準じたマルチキャスト アドレスです。</span><span class="sxs-lookup"><span data-stu-id="98c43-130">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="98c43-131">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="98c43-131">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="98c43-132">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="98c43-132">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98c43-133">子要素</span><span class="sxs-lookup"><span data-stu-id="98c43-133">Child Elements</span></span>  
  
|<span data-ttu-id="98c43-134">要素</span><span class="sxs-lookup"><span data-stu-id="98c43-134">Element</span></span>|<span data-ttu-id="98c43-135">Description</span><span class="sxs-lookup"><span data-stu-id="98c43-135">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="98c43-136">UDP エンドポイントの UDP トランスポートを構成できる設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="98c43-136">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98c43-137">親要素</span><span class="sxs-lookup"><span data-stu-id="98c43-137">Parent Elements</span></span>  
  
|<span data-ttu-id="98c43-138">要素</span><span class="sxs-lookup"><span data-stu-id="98c43-138">Element</span></span>|<span data-ttu-id="98c43-139">Description</span><span class="sxs-lookup"><span data-stu-id="98c43-139">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="98c43-140">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="98c43-140">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98c43-141">例</span><span class="sxs-lookup"><span data-stu-id="98c43-141">Example</span></span>  
 <span data-ttu-id="98c43-142">UDP マルチキャスト トランスポート経由で探索メッセージをリッスンするサービスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="98c43-142">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="98c43-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="98c43-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
