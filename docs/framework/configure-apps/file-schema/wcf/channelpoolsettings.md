---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 70f7452a22ae08d6eccd7d3644bdc8df45087ae0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423183"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="c831f-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c831f-101">\<channelPoolSettings></span></span>
<span data-ttu-id="c831f-102">カスタム バインディングのチャネル プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c831f-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="c831f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c831f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c831f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c831f-104">\<bindings></span></span>  
<span data-ttu-id="c831f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c831f-105">\<customBinding></span></span>  
<span data-ttu-id="c831f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c831f-106">\<binding></span></span>  
<span data-ttu-id="c831f-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c831f-107">\<oneWay></span></span>  
<span data-ttu-id="c831f-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c831f-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c831f-109">構文</span><span class="sxs-lookup"><span data-stu-id="c831f-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c831f-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c831f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c831f-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c831f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c831f-112">属性</span><span class="sxs-lookup"><span data-stu-id="c831f-112">Attributes</span></span>  
  
|<span data-ttu-id="c831f-113">属性</span><span class="sxs-lookup"><span data-stu-id="c831f-113">Attribute</span></span>|<span data-ttu-id="c831f-114">説明</span><span class="sxs-lookup"><span data-stu-id="c831f-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="c831f-115">プール内のチャネルの接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="c831f-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="c831f-116">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="c831f-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="c831f-117">プールに返されたチャネルが閉じられるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="c831f-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="c831f-118">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="c831f-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="c831f-119">各リモート エンドポイントのプール内に格納できるチャネルの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="c831f-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="c831f-120">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="c831f-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c831f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c831f-121">Child Elements</span></span>  
 <span data-ttu-id="c831f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c831f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c831f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c831f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c831f-124">要素</span><span class="sxs-lookup"><span data-stu-id="c831f-124">Element</span></span>|<span data-ttu-id="c831f-125">説明</span><span class="sxs-lookup"><span data-stu-id="c831f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c831f-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c831f-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="c831f-127">カスタム バインドでパケット ルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c831f-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c831f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="c831f-128">Remarks</span></span>  
 <span data-ttu-id="c831f-129">クォータは、リソースの過剰な消費を防ぐためのポリシー メカニズムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c831f-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="c831f-130">クォータは、悪質な、または意図的でないサービス拒否 (DOS) 攻撃を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="c831f-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="c831f-131">カスタム チャネルにチャネル クォータを設定するには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="c831f-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="c831f-132">`ChannelPoolSettings` では、次の 3 つのクォータを指定します。</span><span class="sxs-lookup"><span data-stu-id="c831f-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="c831f-133">`idleTimeout` クォータは、サーバーでは、長時間リソースを停滞させることによるサービス拒否 (DOS) 攻撃を軽減するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c831f-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="c831f-134">クライアントでは、適切な値を設定することで、サービスとの接続の信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="c831f-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="c831f-135">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c831f-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="c831f-136">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="c831f-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c831f-137">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c831f-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="c831f-138">`leaseTimeout` クォータは、負荷分散機能との統合、および信頼性の向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c831f-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="c831f-139">既定値では、リソースが控えめに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c831f-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="c831f-140">開発環境、および小規模のインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="c831f-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c831f-141">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c831f-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="c831f-142">`maxOutboundChannelsPerEndpoint` クォータは、サーバーとクライアントの両方に対するキャッシュ制限を設定し、信頼性向上のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c831f-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="c831f-143">既定値ではリソースが控えめに割り当てられており、開発環境および小規模なインストール シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="c831f-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c831f-144">インストールでリソースが不足している場合、または追加リソースが使用可能であるにもかかわらず接続が制限されている場合、サービス管理者は値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c831f-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c831f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="c831f-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c831f-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c831f-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="c831f-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="c831f-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c831f-148">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="c831f-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c831f-149">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c831f-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c831f-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c831f-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
