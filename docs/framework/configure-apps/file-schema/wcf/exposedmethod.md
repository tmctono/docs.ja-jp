---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855312"
---
# <a name="exposedmethod"></a><span data-ttu-id="b59ea-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="b59ea-101">\<exposedMethod></span></span>
<span data-ttu-id="b59ea-102">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="b59ea-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b59ea-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b59ea-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b59ea-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b59ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="b59ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="b59ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="b59ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="b59ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<exposedMethods >** ](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="b59ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="b59ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<exposedMethod >**</span><span class="sxs-lookup"><span data-stu-id="b59ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b59ea-109">構文</span><span class="sxs-lookup"><span data-stu-id="b59ea-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b59ea-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b59ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b59ea-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b59ea-112">属性</span><span class="sxs-lookup"><span data-stu-id="b59ea-112">Attributes</span></span>  
  
|<span data-ttu-id="b59ea-113">属性</span><span class="sxs-lookup"><span data-stu-id="b59ea-113">Attribute</span></span>|<span data-ttu-id="b59ea-114">説明</span><span class="sxs-lookup"><span data-stu-id="b59ea-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b59ea-115">name</span><span class="sxs-lookup"><span data-stu-id="b59ea-115">name</span></span>|<span data-ttu-id="b59ea-116">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="b59ea-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b59ea-117">子要素</span><span class="sxs-lookup"><span data-stu-id="b59ea-117">Child Elements</span></span>  
 <span data-ttu-id="b59ea-118">なし。</span><span class="sxs-lookup"><span data-stu-id="b59ea-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b59ea-119">親要素</span><span class="sxs-lookup"><span data-stu-id="b59ea-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b59ea-120">要素</span><span class="sxs-lookup"><span data-stu-id="b59ea-120">Element</span></span>|<span data-ttu-id="b59ea-121">説明</span><span class="sxs-lookup"><span data-stu-id="b59ea-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b59ea-122">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="b59ea-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="b59ea-123">[ \<ExposedMethod >](exposedmethod.md)要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="b59ea-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b59ea-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b59ea-124">Remarks</span></span>  
 <span data-ttu-id="b59ea-125">COM+ 統合構成ツール (ComSvcConfig.exe) を使用して、COM インターフェイスから特定のメソッドを追加して、生成されるサービス コントラクトに表示できます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="b59ea-126">たとえば、次のコマンドを使用して、`IFinances`.Financial コンポーネントの `ItemOrders` COM インターフェイスから、3 つの名前付きメソッドを、生成されるサービス コントラクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="b59ea-127">また、comsvcconfig.exe を実行すると、前述のメソッドを[ \<exposedMethod >](exposedmethod.md)要素として一覧表示する次のサービスコントラクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="b59ea-128">サービスの初期化時に、ランタイムは、 [ \<exposedMethod >](exposedmethod.md)要素のリストに含まれるメソッドのみを反映し、追加することによって、サービスコントラクトの生成を試みます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="b59ea-129">トレースは、サービス コントラクトに含まれないインターフェイス メソッド用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59ea-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b59ea-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="b59ea-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="b59ea-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="b59ea-132">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="b59ea-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="b59ea-133">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="b59ea-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
