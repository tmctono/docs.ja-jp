---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430306"
---
# <a name="mextcpbinding"></a><span data-ttu-id="e46d3-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e46d3-101">\<mexTcpBinding></span></span>
<span data-ttu-id="e46d3-102">TCP 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e46d3-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="e46d3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e46d3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e46d3-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e46d3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e46d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e46d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e46d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexTcpBinding>**</span><span class="sxs-lookup"><span data-stu-id="e46d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46d3-107">構文</span><span class="sxs-lookup"><span data-stu-id="e46d3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e46d3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e46d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e46d3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e46d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e46d3-110">属性</span><span class="sxs-lookup"><span data-stu-id="e46d3-110">Attributes</span></span>  
  
|<span data-ttu-id="e46d3-111">属性</span><span class="sxs-lookup"><span data-stu-id="e46d3-111">Attribute</span></span>|<span data-ttu-id="e46d3-112">説明</span><span class="sxs-lookup"><span data-stu-id="e46d3-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e46d3-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="e46d3-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e46d3-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46d3-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46d3-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="e46d3-116">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e46d3-117">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46d3-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e46d3-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="e46d3-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e46d3-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e46d3-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e46d3-120">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e46d3-121">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46d3-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46d3-122">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e46d3-123">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e46d3-124">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46d3-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46d3-125">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e46d3-126">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e46d3-127">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e46d3-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e46d3-128">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="e46d3-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e46d3-129">子要素</span><span class="sxs-lookup"><span data-stu-id="e46d3-129">Child Elements</span></span>  
 <span data-ttu-id="e46d3-130">なし。</span><span class="sxs-lookup"><span data-stu-id="e46d3-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e46d3-131">親要素</span><span class="sxs-lookup"><span data-stu-id="e46d3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="e46d3-132">要素</span><span class="sxs-lookup"><span data-stu-id="e46d3-132">Element</span></span>|<span data-ttu-id="e46d3-133">説明</span><span class="sxs-lookup"><span data-stu-id="e46d3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e46d3-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e46d3-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="e46d3-135">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="e46d3-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e46d3-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e46d3-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="e46d3-137">方法 : 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="e46d3-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="e46d3-138">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="e46d3-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="e46d3-139">メタデータ</span><span class="sxs-lookup"><span data-stu-id="e46d3-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="e46d3-140">バインディング</span><span class="sxs-lookup"><span data-stu-id="e46d3-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e46d3-141">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e46d3-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e46d3-142">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e46d3-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e46d3-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="e46d3-143">\<binding></span></span>](bindings.md)
