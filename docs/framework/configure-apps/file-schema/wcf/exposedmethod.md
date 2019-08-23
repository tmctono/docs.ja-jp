---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 032139b714aa11079c7ee8610c332e404b3981ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918990"
---
# <a name="exposedmethod"></a><span data-ttu-id="03cb0-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="03cb0-101">\<exposedMethod></span></span>
<span data-ttu-id="03cb0-102">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="03cb0-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="03cb0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="03cb0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="03cb0-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="03cb0-104">\<comContracts></span></span>  
<span data-ttu-id="03cb0-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="03cb0-105">\<comContract></span></span>  
<span data-ttu-id="03cb0-106">\<メソッド ></span><span class="sxs-lookup"><span data-stu-id="03cb0-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03cb0-107">構文</span><span class="sxs-lookup"><span data-stu-id="03cb0-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03cb0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="03cb0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03cb0-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="03cb0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03cb0-110">属性</span><span class="sxs-lookup"><span data-stu-id="03cb0-110">Attributes</span></span>  
  
|<span data-ttu-id="03cb0-111">属性</span><span class="sxs-lookup"><span data-stu-id="03cb0-111">Attribute</span></span>|<span data-ttu-id="03cb0-112">説明</span><span class="sxs-lookup"><span data-stu-id="03cb0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03cb0-113">name</span><span class="sxs-lookup"><span data-stu-id="03cb0-113">name</span></span>|<span data-ttu-id="03cb0-114">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="03cb0-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03cb0-115">子要素</span><span class="sxs-lookup"><span data-stu-id="03cb0-115">Child Elements</span></span>  
 <span data-ttu-id="03cb0-116">なし。</span><span class="sxs-lookup"><span data-stu-id="03cb0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03cb0-117">親要素</span><span class="sxs-lookup"><span data-stu-id="03cb0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="03cb0-118">要素</span><span class="sxs-lookup"><span data-stu-id="03cb0-118">Element</span></span>|<span data-ttu-id="03cb0-119">説明</span><span class="sxs-lookup"><span data-stu-id="03cb0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03cb0-120">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="03cb0-120">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="03cb0-121">[ \<ExposedMethod >](exposedmethod.md)要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="03cb0-121">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03cb0-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="03cb0-122">Remarks</span></span>  
 <span data-ttu-id="03cb0-123">COM+ 統合構成ツール (ComSvcConfig.exe) を使用して、COM インターフェイスから特定のメソッドを追加して、生成されるサービス コントラクトに表示できます。</span><span class="sxs-lookup"><span data-stu-id="03cb0-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="03cb0-124">たとえば、次のコマンドを使用して、`IFinances`.Financial コンポーネントの `ItemOrders` COM インターフェイスから、3 つの名前付きメソッドを、生成されるサービス コントラクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="03cb0-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="03cb0-125">また、comsvcconfig.exe を実行すると、前述のメソッドを[ \<exposedMethod >](exposedmethod.md)要素として一覧表示する次のサービスコントラクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="03cb0-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="03cb0-126">サービスの初期化時に、ランタイムは、 [ \<exposedMethod >](exposedmethod.md)要素のリストに含まれるメソッドのみを反映し、追加することによって、サービスコントラクトの生成を試みます。</span><span class="sxs-lookup"><span data-stu-id="03cb0-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="03cb0-127">トレースは、サービス コントラクトに含まれないインターフェイス メソッド用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="03cb0-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03cb0-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="03cb0-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="03cb0-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="03cb0-129">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="03cb0-130">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="03cb0-130">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="03cb0-131">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="03cb0-131">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
