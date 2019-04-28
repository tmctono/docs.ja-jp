---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704142"
---
# <a name="datacontractserializer"></a><span data-ttu-id="a3f9c-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="a3f9c-101">\<dataContractSerializer></span></span>
<span data-ttu-id="a3f9c-102"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="a3f9c-103">この要素は、2 つの異なる階層で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="a3f9c-104">1 つは以下の「スキーマの階層」に示したもので、もう 1 つは「解説」に記載しています。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="a3f9c-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a3f9c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3f9c-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="a3f9c-106">\<behaviors></span></span>  
<span data-ttu-id="a3f9c-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3f9c-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="a3f9c-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3f9c-108">\<behavior></span></span>  
<span data-ttu-id="a3f9c-109">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="a3f9c-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f9c-110">構文</span><span class="sxs-lookup"><span data-stu-id="a3f9c-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3f9c-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a3f9c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a3f9c-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3f9c-113">属性</span><span class="sxs-lookup"><span data-stu-id="a3f9c-113">Attributes</span></span>  
  
|<span data-ttu-id="a3f9c-114">要素</span><span class="sxs-lookup"><span data-stu-id="a3f9c-114">Element</span></span>|<span data-ttu-id="a3f9c-115">説明</span><span class="sxs-lookup"><span data-stu-id="a3f9c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3f9c-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="a3f9c-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="a3f9c-117">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="a3f9c-118">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="a3f9c-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="a3f9c-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="a3f9c-120">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="a3f9c-121">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3f9c-122">子要素</span><span class="sxs-lookup"><span data-stu-id="a3f9c-122">Child Elements</span></span>  
 <span data-ttu-id="a3f9c-123">なし。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3f9c-124">親要素</span><span class="sxs-lookup"><span data-stu-id="a3f9c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a3f9c-125">要素</span><span class="sxs-lookup"><span data-stu-id="a3f9c-125">Element</span></span>|<span data-ttu-id="a3f9c-126">説明</span><span class="sxs-lookup"><span data-stu-id="a3f9c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3f9c-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3f9c-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="a3f9c-128">サービスの動作設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="a3f9c-129">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="a3f9c-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="a3f9c-130"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f9c-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3f9c-131">Remarks</span></span>  
 <span data-ttu-id="a3f9c-132">これを 2 番目の階層は、このトピックの冒頭で述べたように、 \<X509Extension > 要素に発生します。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="a3f9c-133">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="a3f9c-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="a3f9c-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="a3f9c-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="a3f9c-135">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3f9c-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f9c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3f9c-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="a3f9c-137">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="a3f9c-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="a3f9c-138">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="a3f9c-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
