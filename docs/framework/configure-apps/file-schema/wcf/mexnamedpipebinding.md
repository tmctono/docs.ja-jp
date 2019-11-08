---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: be538274636b519600d87b1d3be2faaa2e161cd0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738916"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="d4af9-101">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="d4af9-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="d4af9-102">名前付きパイプを経由する WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4af9-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="d4af9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4af9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4af9-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="d4af9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d4af9-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d4af9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d4af9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mexNamedPipeBinding >**</span><span class="sxs-lookup"><span data-stu-id="d4af9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4af9-107">構文</span><span class="sxs-lookup"><span data-stu-id="d4af9-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4af9-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4af9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d4af9-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4af9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4af9-110">属性</span><span class="sxs-lookup"><span data-stu-id="d4af9-110">Attributes</span></span>  
  
|<span data-ttu-id="d4af9-111">属性</span><span class="sxs-lookup"><span data-stu-id="d4af9-111">Attribute</span></span>|<span data-ttu-id="d4af9-112">説明</span><span class="sxs-lookup"><span data-stu-id="d4af9-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d4af9-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="d4af9-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d4af9-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4af9-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d4af9-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d4af9-116">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d4af9-117">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4af9-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d4af9-118">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4af9-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d4af9-119">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d4af9-120">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4af9-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d4af9-121">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4af9-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d4af9-122">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d4af9-123">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4af9-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d4af9-124">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d4af9-125">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d4af9-126">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4af9-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d4af9-127">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d4af9-128">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d4af9-129">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4af9-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d4af9-130">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="d4af9-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4af9-131">子要素</span><span class="sxs-lookup"><span data-stu-id="d4af9-131">Child Elements</span></span>  
 <span data-ttu-id="d4af9-132">なし。</span><span class="sxs-lookup"><span data-stu-id="d4af9-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4af9-133">親要素</span><span class="sxs-lookup"><span data-stu-id="d4af9-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d4af9-134">要素</span><span class="sxs-lookup"><span data-stu-id="d4af9-134">Element</span></span>|<span data-ttu-id="d4af9-135">説明</span><span class="sxs-lookup"><span data-stu-id="d4af9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4af9-136">\< バインド ></span><span class="sxs-lookup"><span data-stu-id="d4af9-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="d4af9-137">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="d4af9-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4af9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4af9-138">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="d4af9-139">方法 : 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="d4af9-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d4af9-140">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="d4af9-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d4af9-141">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d4af9-141">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="d4af9-142">バインディング</span><span class="sxs-lookup"><span data-stu-id="d4af9-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d4af9-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="d4af9-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d4af9-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="d4af9-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d4af9-145">\<binding ></span><span class="sxs-lookup"><span data-stu-id="d4af9-145">\<binding></span></span>](bindings.md)
