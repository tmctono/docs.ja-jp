---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855312"
---
# \<exposedMethod>
<span data-ttu-id="703f9-101">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="703f9-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="703f9-102">構文</span><span class="sxs-lookup"><span data-stu-id="703f9-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="703f9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="703f9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="703f9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="703f9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="703f9-105">属性</span><span class="sxs-lookup"><span data-stu-id="703f9-105">Attributes</span></span>  
  
|<span data-ttu-id="703f9-106">属性</span><span class="sxs-lookup"><span data-stu-id="703f9-106">Attribute</span></span>|<span data-ttu-id="703f9-107">説明</span><span class="sxs-lookup"><span data-stu-id="703f9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="703f9-108">name</span><span class="sxs-lookup"><span data-stu-id="703f9-108">name</span></span>|<span data-ttu-id="703f9-109">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="703f9-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="703f9-110">子要素</span><span class="sxs-lookup"><span data-stu-id="703f9-110">Child Elements</span></span>  
 <span data-ttu-id="703f9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="703f9-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="703f9-112">親要素</span><span class="sxs-lookup"><span data-stu-id="703f9-112">Parent Elements</span></span>  
  
|<span data-ttu-id="703f9-113">要素</span><span class="sxs-lookup"><span data-stu-id="703f9-113">Element</span></span>|<span data-ttu-id="703f9-114">Description</span><span class="sxs-lookup"><span data-stu-id="703f9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="703f9-115">要素のコレクション [\<exposedMethod>](exposedmethod.md) 。</span><span class="sxs-lookup"><span data-stu-id="703f9-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="703f9-116">解説</span><span class="sxs-lookup"><span data-stu-id="703f9-116">Remarks</span></span>  
 <span data-ttu-id="703f9-117">COM+ 統合構成ツール (ComSvcConfig.exe) を使用して、COM インターフェイスから特定のメソッドを追加して、生成されるサービス コントラクトに表示できます。</span><span class="sxs-lookup"><span data-stu-id="703f9-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="703f9-118">たとえば、次のコマンドを使用して、`IFinances`.Financial コンポーネントの `ItemOrders` COM インターフェイスから、3 つの名前付きメソッドを、生成されるサービス コントラクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="703f9-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="703f9-119">また、Comsvcconfig.exe を実行すると、前述のメソッドを要素として一覧表示する次のサービスコントラクトが生成され [\<exposedMethod>](exposedmethod.md) ます。</span><span class="sxs-lookup"><span data-stu-id="703f9-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="703f9-120">サービスの初期化時に、ランタイムは、要素のリストに含まれているメソッドのみを反映し、追加することによって、サービスコントラクトの生成を試み [\<exposedMethod>](exposedmethod.md) ます。</span><span class="sxs-lookup"><span data-stu-id="703f9-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="703f9-121">トレースは、サービス コントラクトに含まれないインターフェイス メソッド用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="703f9-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703f9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="703f9-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="703f9-123">COM + アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="703f9-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="703f9-124">方法: COM+ サービス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="703f9-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
