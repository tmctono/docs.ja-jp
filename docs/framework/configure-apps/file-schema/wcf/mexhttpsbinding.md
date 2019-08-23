---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 30d1aa27ce29b6aa4091c3e7be05746ad462102a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931265"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="9b681-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="9b681-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="9b681-102">HTTPS 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b681-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="9b681-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9b681-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b681-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9b681-104">\<bindings></span></span>  
<span data-ttu-id="9b681-105">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="9b681-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b681-106">構文</span><span class="sxs-lookup"><span data-stu-id="9b681-106">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b681-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b681-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9b681-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b681-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b681-109">属性</span><span class="sxs-lookup"><span data-stu-id="9b681-109">Attributes</span></span>  
  
|<span data-ttu-id="9b681-110">属性</span><span class="sxs-lookup"><span data-stu-id="9b681-110">Attribute</span></span>|<span data-ttu-id="9b681-111">説明</span><span class="sxs-lookup"><span data-stu-id="9b681-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9b681-112">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="9b681-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9b681-113">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b681-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9b681-114">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9b681-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="9b681-115">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="9b681-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9b681-116">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b681-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9b681-117">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b681-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="9b681-118">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="9b681-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="9b681-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9b681-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9b681-120">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b681-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9b681-121">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9b681-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9b681-122">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b681-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9b681-123">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9b681-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9b681-124">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9b681-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9b681-125">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b681-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9b681-126">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="9b681-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9b681-127">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9b681-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9b681-128">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b681-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9b681-129">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9b681-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b681-130">子要素</span><span class="sxs-lookup"><span data-stu-id="9b681-130">Child Elements</span></span>  
 <span data-ttu-id="9b681-131">なし。</span><span class="sxs-lookup"><span data-stu-id="9b681-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b681-132">親要素</span><span class="sxs-lookup"><span data-stu-id="9b681-132">Parent Elements</span></span>  
  
|<span data-ttu-id="9b681-133">要素</span><span class="sxs-lookup"><span data-stu-id="9b681-133">Element</span></span>|<span data-ttu-id="9b681-134">説明</span><span class="sxs-lookup"><span data-stu-id="9b681-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b681-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9b681-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="9b681-136">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="9b681-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b681-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b681-137">Remarks</span></span>  
 <span data-ttu-id="9b681-138">このバインディングは、基本的には証明書を使用してトランスポート レベルのセキュリティをサポートする `WSHttpBinding` バインディングです。</span><span class="sxs-lookup"><span data-stu-id="9b681-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="9b681-139">このようなメタデータエンドポイントの構成と使用の詳細[については、「」を参照してください。カスタムの ws-metadata Exchange バインディング](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md) [を構成する方法:MEX 以外のバインディング](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)を介してメタデータを取得し、サンプルのカスタムの[セキュリティで保護されたメタデータエンドポイント](../../../wcf/samples/custom-secure-metadata-endpoint.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b681-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b681-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b681-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="9b681-141">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="9b681-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="9b681-142">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="9b681-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="9b681-143">方法: カスタムの WS-METADATA Exchange バインディングを構成する</span><span class="sxs-lookup"><span data-stu-id="9b681-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="9b681-144">方法: MEX 以外のバインディングを介したメタデータの取得</span><span class="sxs-lookup"><span data-stu-id="9b681-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="9b681-145">カスタム セキュア メタデータ エンドポイント</span><span class="sxs-lookup"><span data-stu-id="9b681-145">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="9b681-146">メタデータ</span><span class="sxs-lookup"><span data-stu-id="9b681-146">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="9b681-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="9b681-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9b681-148">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9b681-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9b681-149">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9b681-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9b681-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="9b681-150">\<binding></span></span>](../../../misc/binding.md)
