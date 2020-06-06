---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430306"
---
# \<mexTcpBinding>
<span data-ttu-id="069c4-101">TCP 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="069c4-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="069c4-102">構文</span><span class="sxs-lookup"><span data-stu-id="069c4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="069c4-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="069c4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="069c4-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="069c4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="069c4-105">属性</span><span class="sxs-lookup"><span data-stu-id="069c4-105">Attributes</span></span>  
  
|<span data-ttu-id="069c4-106">属性</span><span class="sxs-lookup"><span data-stu-id="069c4-106">Attribute</span></span>|<span data-ttu-id="069c4-107">説明</span><span class="sxs-lookup"><span data-stu-id="069c4-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="069c4-108">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="069c4-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="069c4-109">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="069c4-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="069c4-110">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="069c4-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="069c4-111">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="069c4-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="069c4-112">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="069c4-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="069c4-113">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="069c4-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="069c4-114">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="069c4-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="069c4-115">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="069c4-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="069c4-116">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="069c4-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="069c4-117">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="069c4-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="069c4-118">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="069c4-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="069c4-119">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="069c4-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="069c4-120">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="069c4-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="069c4-121">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="069c4-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="069c4-122">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="069c4-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="069c4-123">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="069c4-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="069c4-124">子要素</span><span class="sxs-lookup"><span data-stu-id="069c4-124">Child Elements</span></span>  
 <span data-ttu-id="069c4-125">なし。</span><span class="sxs-lookup"><span data-stu-id="069c4-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="069c4-126">親要素</span><span class="sxs-lookup"><span data-stu-id="069c4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="069c4-127">要素</span><span class="sxs-lookup"><span data-stu-id="069c4-127">Element</span></span>|<span data-ttu-id="069c4-128">Description</span><span class="sxs-lookup"><span data-stu-id="069c4-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="069c4-129">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="069c4-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="069c4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="069c4-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="069c4-131">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="069c4-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="069c4-132">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="069c4-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="069c4-133">Metadata</span><span class="sxs-lookup"><span data-stu-id="069c4-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="069c4-134">バインド</span><span class="sxs-lookup"><span data-stu-id="069c4-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="069c4-135">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="069c4-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="069c4-136">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="069c4-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
