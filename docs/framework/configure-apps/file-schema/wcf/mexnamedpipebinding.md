---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430873"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="b37f8-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="b37f8-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="b37f8-102">名前付きパイプを経由する WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b37f8-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="b37f8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b37f8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b37f8-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b37f8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b37f8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b37f8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b37f8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexNamedPipeBinding>**</span><span class="sxs-lookup"><span data-stu-id="b37f8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37f8-107">構文</span><span class="sxs-lookup"><span data-stu-id="b37f8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b37f8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b37f8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b37f8-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b37f8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b37f8-110">属性</span><span class="sxs-lookup"><span data-stu-id="b37f8-110">Attributes</span></span>  
  
|<span data-ttu-id="b37f8-111">属性</span><span class="sxs-lookup"><span data-stu-id="b37f8-111">Attribute</span></span>|<span data-ttu-id="b37f8-112">説明</span><span class="sxs-lookup"><span data-stu-id="b37f8-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b37f8-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="b37f8-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b37f8-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f8-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b37f8-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="b37f8-116">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b37f8-117">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f8-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b37f8-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="b37f8-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b37f8-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b37f8-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="b37f8-120">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b37f8-121">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f8-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b37f8-122">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b37f8-123">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b37f8-124">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f8-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b37f8-125">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b37f8-126">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b37f8-127">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b37f8-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b37f8-128">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b37f8-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b37f8-129">子要素</span><span class="sxs-lookup"><span data-stu-id="b37f8-129">Child Elements</span></span>  
 <span data-ttu-id="b37f8-130">なし。</span><span class="sxs-lookup"><span data-stu-id="b37f8-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b37f8-131">親要素</span><span class="sxs-lookup"><span data-stu-id="b37f8-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b37f8-132">要素</span><span class="sxs-lookup"><span data-stu-id="b37f8-132">Element</span></span>|<span data-ttu-id="b37f8-133">説明</span><span class="sxs-lookup"><span data-stu-id="b37f8-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b37f8-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b37f8-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="b37f8-135">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b37f8-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b37f8-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b37f8-136">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="b37f8-137">方法 : 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="b37f8-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="b37f8-138">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="b37f8-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="b37f8-139">メタデータ</span><span class="sxs-lookup"><span data-stu-id="b37f8-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="b37f8-140">バインディング</span><span class="sxs-lookup"><span data-stu-id="b37f8-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b37f8-141">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="b37f8-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b37f8-142">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="b37f8-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b37f8-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="b37f8-143">\<binding></span></span>](bindings.md)
