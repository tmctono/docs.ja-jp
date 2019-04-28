---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8ba16d9cc30b07d3e6b0924e6013ec01443867d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704129"
---
# <a name="datacontractserializer"></a><span data-ttu-id="760d9-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="760d9-102">dataContractSerializer</span></span>
<span data-ttu-id="760d9-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="760d9-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="760d9-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="760d9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="760d9-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="760d9-105">\<behaviors></span></span>  
<span data-ttu-id="760d9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="760d9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="760d9-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="760d9-107">\<behavior></span></span>  
<span data-ttu-id="760d9-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="760d9-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="760d9-109">構文</span><span class="sxs-lookup"><span data-stu-id="760d9-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="760d9-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="760d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="760d9-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="760d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="760d9-112">属性</span><span class="sxs-lookup"><span data-stu-id="760d9-112">Attributes</span></span>  
  
|<span data-ttu-id="760d9-113">要素</span><span class="sxs-lookup"><span data-stu-id="760d9-113">Element</span></span>|<span data-ttu-id="760d9-114">説明</span><span class="sxs-lookup"><span data-stu-id="760d9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="760d9-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="760d9-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="760d9-116">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="760d9-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="760d9-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="760d9-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="760d9-118">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="760d9-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="760d9-119">子要素</span><span class="sxs-lookup"><span data-stu-id="760d9-119">Child Elements</span></span>  
 <span data-ttu-id="760d9-120">なし。</span><span class="sxs-lookup"><span data-stu-id="760d9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="760d9-121">親要素</span><span class="sxs-lookup"><span data-stu-id="760d9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="760d9-122">要素</span><span class="sxs-lookup"><span data-stu-id="760d9-122">Element</span></span>|<span data-ttu-id="760d9-123">説明</span><span class="sxs-lookup"><span data-stu-id="760d9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="760d9-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="760d9-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="760d9-125">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="760d9-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="760d9-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="760d9-126">Remarks</span></span>  
 <span data-ttu-id="760d9-127">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="760d9-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="760d9-128">`<dataContractSerializer>` 動作要素が存在する場合は、構成ファイル内で `<enableWebScript>` 動作要素よりも前に出現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="760d9-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="760d9-129">それ以外の場合は、動作結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="760d9-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760d9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="760d9-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="760d9-131">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="760d9-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="760d9-132">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="760d9-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
