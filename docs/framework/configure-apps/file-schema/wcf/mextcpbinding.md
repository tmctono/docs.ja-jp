---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932530"
---
# <a name="mextcpbinding"></a><span data-ttu-id="eaad0-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="eaad0-101">\<mexTcpBinding></span></span>
<span data-ttu-id="eaad0-102">TCP 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eaad0-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="eaad0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eaad0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="eaad0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="eaad0-104">\<bindings></span></span>  
<span data-ttu-id="eaad0-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="eaad0-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaad0-106">構文</span><span class="sxs-lookup"><span data-stu-id="eaad0-106">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaad0-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eaad0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eaad0-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaad0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaad0-109">属性</span><span class="sxs-lookup"><span data-stu-id="eaad0-109">Attributes</span></span>  
  
|<span data-ttu-id="eaad0-110">属性</span><span class="sxs-lookup"><span data-stu-id="eaad0-110">Attribute</span></span>|<span data-ttu-id="eaad0-111">説明</span><span class="sxs-lookup"><span data-stu-id="eaad0-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="eaad0-112">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="eaad0-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="eaad0-113">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaad0-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="eaad0-114">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="eaad0-115">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="eaad0-116">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaad0-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="eaad0-117">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eaad0-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="eaad0-118">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="eaad0-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eaad0-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="eaad0-120">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaad0-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="eaad0-121">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="eaad0-122">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaad0-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="eaad0-123">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="eaad0-124">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="eaad0-125">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaad0-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="eaad0-126">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="eaad0-127">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="eaad0-128">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaad0-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="eaad0-129">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="eaad0-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaad0-130">子要素</span><span class="sxs-lookup"><span data-stu-id="eaad0-130">Child Elements</span></span>  
 <span data-ttu-id="eaad0-131">なし。</span><span class="sxs-lookup"><span data-stu-id="eaad0-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eaad0-132">親要素</span><span class="sxs-lookup"><span data-stu-id="eaad0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="eaad0-133">要素</span><span class="sxs-lookup"><span data-stu-id="eaad0-133">Element</span></span>|<span data-ttu-id="eaad0-134">説明</span><span class="sxs-lookup"><span data-stu-id="eaad0-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaad0-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="eaad0-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="eaad0-136">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="eaad0-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eaad0-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaad0-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="eaad0-138">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="eaad0-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="eaad0-139">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="eaad0-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="eaad0-140">メタデータ</span><span class="sxs-lookup"><span data-stu-id="eaad0-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="eaad0-141">バインディング</span><span class="sxs-lookup"><span data-stu-id="eaad0-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eaad0-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="eaad0-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="eaad0-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="eaad0-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="eaad0-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="eaad0-144">\<binding></span></span>](../../../misc/binding.md)
