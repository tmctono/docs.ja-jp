---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 64e250ae5ccb30da3f8857b94628b85b8c237a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204711"
---
# \<mexNamedPipeBinding>

<span data-ttu-id="3f01d-101">名前付きパイプを経由する WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f01d-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="3f01d-102">構文</span><span class="sxs-lookup"><span data-stu-id="3f01d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f01d-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f01d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3f01d-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f01d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f01d-105">属性</span><span class="sxs-lookup"><span data-stu-id="3f01d-105">Attributes</span></span>  
  
|<span data-ttu-id="3f01d-106">属性</span><span class="sxs-lookup"><span data-stu-id="3f01d-106">Attribute</span></span>|<span data-ttu-id="3f01d-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f01d-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3f01d-108">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="3f01d-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3f01d-109">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01d-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3f01d-110">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="3f01d-111">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3f01d-112">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01d-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3f01d-113">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3f01d-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3f01d-114">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f01d-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3f01d-115">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3f01d-116">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01d-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3f01d-117">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3f01d-118">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3f01d-119">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01d-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3f01d-120">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3f01d-121">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3f01d-122">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01d-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3f01d-123">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="3f01d-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f01d-124">子要素</span><span class="sxs-lookup"><span data-stu-id="3f01d-124">Child Elements</span></span>  

 <span data-ttu-id="3f01d-125">なし。</span><span class="sxs-lookup"><span data-stu-id="3f01d-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f01d-126">親要素</span><span class="sxs-lookup"><span data-stu-id="3f01d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3f01d-127">要素</span><span class="sxs-lookup"><span data-stu-id="3f01d-127">Element</span></span>|<span data-ttu-id="3f01d-128">説明</span><span class="sxs-lookup"><span data-stu-id="3f01d-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="3f01d-129">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="3f01d-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f01d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f01d-130">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="3f01d-131">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="3f01d-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="3f01d-132">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="3f01d-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="3f01d-133">Metadata</span><span class="sxs-lookup"><span data-stu-id="3f01d-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="3f01d-134">バインド</span><span class="sxs-lookup"><span data-stu-id="3f01d-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3f01d-135">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="3f01d-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3f01d-136">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="3f01d-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
