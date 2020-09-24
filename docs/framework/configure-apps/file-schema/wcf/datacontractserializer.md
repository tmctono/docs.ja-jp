---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153925"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3a365-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3a365-102">dataContractSerializer</span></span>

<span data-ttu-id="3a365-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a365-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="3a365-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a365-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a365-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3a365-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3a365-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a365-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a365-107">属性</span><span class="sxs-lookup"><span data-stu-id="3a365-107">Attributes</span></span>  
  
|<span data-ttu-id="3a365-108">要素</span><span class="sxs-lookup"><span data-stu-id="3a365-108">Element</span></span>|<span data-ttu-id="3a365-109">説明</span><span class="sxs-lookup"><span data-stu-id="3a365-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a365-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3a365-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3a365-111">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="3a365-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3a365-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3a365-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3a365-113">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="3a365-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a365-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3a365-114">Child Elements</span></span>  

 <span data-ttu-id="3a365-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3a365-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a365-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3a365-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3a365-117">要素</span><span class="sxs-lookup"><span data-stu-id="3a365-117">Element</span></span>|<span data-ttu-id="3a365-118">説明</span><span class="sxs-lookup"><span data-stu-id="3a365-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3a365-119">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a365-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a365-120">解説</span><span class="sxs-lookup"><span data-stu-id="3a365-120">Remarks</span></span>  

 <span data-ttu-id="3a365-121">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a365-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3a365-122">`<dataContractSerializer>` 動作要素が存在する場合は、構成ファイル内で `<enableWebScript>` 動作要素よりも前に出現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a365-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3a365-123">それ以外の場合は、動作結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="3a365-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a365-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a365-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3a365-125">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="3a365-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3a365-126">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="3a365-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
