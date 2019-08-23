---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925909"
---
# <a name="datacontractserializer"></a><span data-ttu-id="1a337-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1a337-101">\<dataContractSerializer></span></span>
<span data-ttu-id="1a337-102"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a337-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="1a337-103">この要素は、2 つの異なる階層で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a337-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="1a337-104">1 つは以下の「スキーマの階層」に示したもので、もう 1 つは「解説」に記載しています。</span><span class="sxs-lookup"><span data-stu-id="1a337-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="1a337-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1a337-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1a337-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="1a337-106">\<behaviors></span></span>  
<span data-ttu-id="1a337-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1a337-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="1a337-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1a337-108">\<behavior></span></span>  
<span data-ttu-id="1a337-109">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1a337-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a337-110">構文</span><span class="sxs-lookup"><span data-stu-id="1a337-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a337-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a337-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1a337-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a337-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a337-113">属性</span><span class="sxs-lookup"><span data-stu-id="1a337-113">Attributes</span></span>  
  
|<span data-ttu-id="1a337-114">要素</span><span class="sxs-lookup"><span data-stu-id="1a337-114">Element</span></span>|<span data-ttu-id="1a337-115">説明</span><span class="sxs-lookup"><span data-stu-id="1a337-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a337-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="1a337-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="1a337-117">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="1a337-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="1a337-118">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="1a337-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="1a337-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="1a337-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="1a337-120">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="1a337-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="1a337-121">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="1a337-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a337-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1a337-122">Child Elements</span></span>  
 <span data-ttu-id="1a337-123">なし。</span><span class="sxs-lookup"><span data-stu-id="1a337-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a337-124">親要素</span><span class="sxs-lookup"><span data-stu-id="1a337-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1a337-125">要素</span><span class="sxs-lookup"><span data-stu-id="1a337-125">Element</span></span>|<span data-ttu-id="1a337-126">説明</span><span class="sxs-lookup"><span data-stu-id="1a337-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a337-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1a337-127">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="1a337-128">サービスの動作設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1a337-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="1a337-129">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="1a337-129">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="1a337-130"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="1a337-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a337-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a337-131">Remarks</span></span>  
 <span data-ttu-id="1a337-132">このトピックの冒頭で述べたように、これは\<X509Extension > 要素が発生する2番目の階層です。</span><span class="sxs-lookup"><span data-stu-id="1a337-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="1a337-133">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="1a337-133">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="1a337-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1a337-134">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="1a337-135">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a337-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a337-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a337-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="1a337-137">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="1a337-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="1a337-138">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="1a337-138">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
