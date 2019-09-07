---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: c6ff5b2cfee1d55b9399b97f3b3397e6bbf8eca2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400240"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="b654b-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b654b-101">\<mexHttpBinding></span></span>
<span data-ttu-id="b654b-102">HTTP 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b654b-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="b654b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b654b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b654b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b654b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b654b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b654b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b654b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="b654b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b654b-107">構文</span><span class="sxs-lookup"><span data-stu-id="b654b-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b654b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b654b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b654b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b654b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b654b-110">属性</span><span class="sxs-lookup"><span data-stu-id="b654b-110">Attributes</span></span>  
  
|<span data-ttu-id="b654b-111">属性</span><span class="sxs-lookup"><span data-stu-id="b654b-111">Attribute</span></span>|<span data-ttu-id="b654b-112">説明</span><span class="sxs-lookup"><span data-stu-id="b654b-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b654b-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="b654b-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b654b-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b654b-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b654b-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b654b-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="b654b-116">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="b654b-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b654b-117">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b654b-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b654b-118">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b654b-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b654b-119">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="b654b-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b654b-120">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b654b-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b654b-121">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b654b-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="b654b-122">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b654b-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b654b-123">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b654b-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b654b-124">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b654b-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b654b-125">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b654b-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b654b-126">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b654b-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b654b-127">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="b654b-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b654b-128">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b654b-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b654b-129">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b654b-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b654b-130">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b654b-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b654b-131">子要素</span><span class="sxs-lookup"><span data-stu-id="b654b-131">Child Elements</span></span>  
 <span data-ttu-id="b654b-132">なし。</span><span class="sxs-lookup"><span data-stu-id="b654b-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b654b-133">親要素</span><span class="sxs-lookup"><span data-stu-id="b654b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b654b-134">要素</span><span class="sxs-lookup"><span data-stu-id="b654b-134">Element</span></span>|<span data-ttu-id="b654b-135">説明</span><span class="sxs-lookup"><span data-stu-id="b654b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b654b-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b654b-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="b654b-137">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b654b-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b654b-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="b654b-138">Remarks</span></span>  
 <span data-ttu-id="b654b-139">このバインディングは、基本的にはセキュリティを無効にした `WSHttpBinding` バインディングです。</span><span class="sxs-lookup"><span data-stu-id="b654b-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="b654b-140">ほとんどのメタデータ要求に対応します。</span><span class="sxs-lookup"><span data-stu-id="b654b-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b654b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="b654b-141">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="b654b-142">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="b654b-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="b654b-143">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="b654b-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="b654b-144">メタデータ</span><span class="sxs-lookup"><span data-stu-id="b654b-144">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="b654b-145">バインディング</span><span class="sxs-lookup"><span data-stu-id="b654b-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b654b-146">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="b654b-146">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b654b-147">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="b654b-147">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b654b-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="b654b-148">\<binding></span></span>](../../../misc/binding.md)
