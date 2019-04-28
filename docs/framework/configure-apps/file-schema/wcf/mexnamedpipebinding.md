---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 9ac2b967e33571cbe0b4ad5ee81e13b009ffddd3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772464"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="685de-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="685de-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="685de-102">名前付きパイプを経由する WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="685de-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="685de-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="685de-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="685de-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="685de-104">\<bindings></span></span>  
<span data-ttu-id="685de-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="685de-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685de-106">構文</span><span class="sxs-lookup"><span data-stu-id="685de-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="685de-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="685de-107">Attributes and Elements</span></span>  
 <span data-ttu-id="685de-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="685de-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="685de-109">属性</span><span class="sxs-lookup"><span data-stu-id="685de-109">Attributes</span></span>  
  
|<span data-ttu-id="685de-110">属性</span><span class="sxs-lookup"><span data-stu-id="685de-110">Attribute</span></span>|<span data-ttu-id="685de-111">説明</span><span class="sxs-lookup"><span data-stu-id="685de-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="685de-112">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="685de-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="685de-113">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="685de-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="685de-114">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="685de-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="685de-115">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="685de-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="685de-116">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="685de-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="685de-117">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="685de-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="685de-118">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="685de-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="685de-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="685de-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="685de-120">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685de-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="685de-121">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="685de-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="685de-122">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="685de-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="685de-123">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="685de-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="685de-124">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="685de-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="685de-125">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="685de-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="685de-126">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="685de-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="685de-127">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="685de-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="685de-128">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="685de-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="685de-129">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="685de-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="685de-130">子要素</span><span class="sxs-lookup"><span data-stu-id="685de-130">Child Elements</span></span>  
 <span data-ttu-id="685de-131">なし。</span><span class="sxs-lookup"><span data-stu-id="685de-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="685de-132">親要素</span><span class="sxs-lookup"><span data-stu-id="685de-132">Parent Elements</span></span>  
  
|<span data-ttu-id="685de-133">要素</span><span class="sxs-lookup"><span data-stu-id="685de-133">Element</span></span>|<span data-ttu-id="685de-134">説明</span><span class="sxs-lookup"><span data-stu-id="685de-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="685de-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="685de-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="685de-136">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="685de-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="685de-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="685de-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="685de-138">方法: 構成ファイルを使用してサービスのメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="685de-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="685de-139">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="685de-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="685de-140">メタデータ</span><span class="sxs-lookup"><span data-stu-id="685de-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="685de-141">バインディング</span><span class="sxs-lookup"><span data-stu-id="685de-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="685de-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="685de-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="685de-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="685de-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="685de-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="685de-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
