---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: ca1f680e2de67984dfcec49b3d262799000a2625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673330"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="652eb-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="652eb-101">\<channelPoolSettings></span></span>
<span data-ttu-id="652eb-102">カスタム バインディングのチャネル プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="652eb-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="652eb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="652eb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="652eb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="652eb-104">\<bindings></span></span>  
<span data-ttu-id="652eb-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="652eb-105">\<customBinding></span></span>  
<span data-ttu-id="652eb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="652eb-106">\<binding></span></span>  
<span data-ttu-id="652eb-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="652eb-107">\<oneWay></span></span>  
<span data-ttu-id="652eb-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="652eb-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="652eb-109">構文</span><span class="sxs-lookup"><span data-stu-id="652eb-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="652eb-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="652eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="652eb-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="652eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="652eb-112">属性</span><span class="sxs-lookup"><span data-stu-id="652eb-112">Attributes</span></span>  
  
|<span data-ttu-id="652eb-113">属性</span><span class="sxs-lookup"><span data-stu-id="652eb-113">Attribute</span></span>|<span data-ttu-id="652eb-114">説明</span><span class="sxs-lookup"><span data-stu-id="652eb-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="652eb-115">プール内のチャネルの接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="652eb-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="652eb-116">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="652eb-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="652eb-117">プールに返されたチャネルが閉じられるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="652eb-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="652eb-118">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="652eb-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="652eb-119">各リモート エンドポイントのプール内に格納できるチャネルの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="652eb-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="652eb-120">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="652eb-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="652eb-121">子要素</span><span class="sxs-lookup"><span data-stu-id="652eb-121">Child Elements</span></span>  
 <span data-ttu-id="652eb-122">なし。</span><span class="sxs-lookup"><span data-stu-id="652eb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="652eb-123">親要素</span><span class="sxs-lookup"><span data-stu-id="652eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="652eb-124">要素</span><span class="sxs-lookup"><span data-stu-id="652eb-124">Element</span></span>|<span data-ttu-id="652eb-125">説明</span><span class="sxs-lookup"><span data-stu-id="652eb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="652eb-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="652eb-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="652eb-127">カスタム バインドでパケット ルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="652eb-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="652eb-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="652eb-128">Remarks</span></span>  
 <span data-ttu-id="652eb-129">クォータは、リソースの過剰な消費を防ぐためのポリシー メカニズムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="652eb-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="652eb-130">クォータは、悪質な、または意図的でないサービス拒否 (DOS) 攻撃を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="652eb-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="652eb-131">カスタム チャネルにチャネル クォータを設定するには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="652eb-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="652eb-132">`ChannelPoolSettings` では、次の 3 つのクォータを指定します。</span><span class="sxs-lookup"><span data-stu-id="652eb-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="652eb-133">`idleTimeout` クォータは、サーバーでは、長時間リソースを停滞させることによるサービス拒否 (DOS) 攻撃を軽減するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="652eb-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="652eb-134">クライアントでは、適切な値を設定することで、サービスとの接続の信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="652eb-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="652eb-135">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="652eb-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="652eb-136">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="652eb-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="652eb-137">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652eb-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="652eb-138">`leaseTimeout` クォータは、負荷分散機能との統合、および信頼性の向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="652eb-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="652eb-139">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="652eb-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="652eb-140">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="652eb-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="652eb-141">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652eb-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="652eb-142">`maxOutboundChannelsPerEndpoint` クォータは、サーバーとクライアントの両方に対するキャッシュ制限を設定し、信頼性向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="652eb-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="652eb-143">既定値ではリソースが控えめに割り当てられており、開発環境および小規模なインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="652eb-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="652eb-144">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652eb-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652eb-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="652eb-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="652eb-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="652eb-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="652eb-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="652eb-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="652eb-148">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="652eb-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="652eb-149">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="652eb-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="652eb-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="652eb-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
