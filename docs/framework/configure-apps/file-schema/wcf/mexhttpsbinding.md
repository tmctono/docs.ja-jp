---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430345"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="2397c-101">\<mexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="2397c-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="2397c-102">HTTPS 経由の WS-MetadataExchange (WS-MEX) メッセージ交換に使用されるバインディングの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2397c-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="2397c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2397c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2397c-104">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2397c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2397c-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)></span><span class="sxs-lookup"><span data-stu-id="2397c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2397c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mexHttpsBinding >**</span><span class="sxs-lookup"><span data-stu-id="2397c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2397c-107">構文</span><span class="sxs-lookup"><span data-stu-id="2397c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2397c-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2397c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2397c-109">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2397c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2397c-110">属性</span><span class="sxs-lookup"><span data-stu-id="2397c-110">Attributes</span></span>  
  
|<span data-ttu-id="2397c-111">属性</span><span class="sxs-lookup"><span data-stu-id="2397c-111">Attribute</span></span>|<span data-ttu-id="2397c-112">説明</span><span class="sxs-lookup"><span data-stu-id="2397c-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="2397c-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="2397c-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="2397c-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2397c-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="2397c-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="2397c-116">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="2397c-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="2397c-117">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="2397c-118">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2397c-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2397c-119">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2397c-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="2397c-120">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="2397c-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="2397c-121">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2397c-122">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="2397c-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="2397c-123">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="2397c-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="2397c-124">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2397c-125">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="2397c-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="2397c-126">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="2397c-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="2397c-127">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2397c-128">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="2397c-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2397c-129">子要素</span><span class="sxs-lookup"><span data-stu-id="2397c-129">Child Elements</span></span>  
 <span data-ttu-id="2397c-130">[なし]。</span><span class="sxs-lookup"><span data-stu-id="2397c-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2397c-131">親要素</span><span class="sxs-lookup"><span data-stu-id="2397c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2397c-132">要素</span><span class="sxs-lookup"><span data-stu-id="2397c-132">Element</span></span>|<span data-ttu-id="2397c-133">説明</span><span class="sxs-lookup"><span data-stu-id="2397c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2397c-134">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="2397c-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="2397c-135">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="2397c-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2397c-136">コメント</span><span class="sxs-lookup"><span data-stu-id="2397c-136">Remarks</span></span>  
 <span data-ttu-id="2397c-137">このバインディングは、基本的には証明書を使用してトランスポート レベルのセキュリティをサポートする `WSHttpBinding` バインディングです。</span><span class="sxs-lookup"><span data-stu-id="2397c-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="2397c-138">このようなメタデータエンドポイントの構成と使用の詳細については、「[方法: カスタム WS-Metadata Exchange バインディングを構成](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)する」、「[方法: MEX 以外のバインディングを使用してメタデータを取得する](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)」、および「[カスタムのセキュリティで保護されたメタデータエンドポイント](../../../wcf/samples/custom-secure-metadata-endpoint.md)のサンプル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2397c-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2397c-139">参照</span><span class="sxs-lookup"><span data-stu-id="2397c-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="2397c-140">方法 : 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="2397c-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="2397c-141">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="2397c-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="2397c-142">方法 : カスタム WS-Metadata Exchange バインディングを構成する</span><span class="sxs-lookup"><span data-stu-id="2397c-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="2397c-143">方法 : MEX 以外のバインディングを介してメタデータを取得する</span><span class="sxs-lookup"><span data-stu-id="2397c-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="2397c-144">カスタム セキュア メタデータ エンドポイント</span><span class="sxs-lookup"><span data-stu-id="2397c-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="2397c-145">メタデータ</span><span class="sxs-lookup"><span data-stu-id="2397c-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="2397c-146">バインディング</span><span class="sxs-lookup"><span data-stu-id="2397c-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2397c-147">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="2397c-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2397c-148">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="2397c-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2397c-149">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="2397c-149">\<binding></span></span>](bindings.md)
