---
title: <dataContractSerializer>< の > の。
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 380d9ba5b8407d78b5045fd34fcdf37c0818d6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919348"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="39e75-102">\<dataContractSerializer > の\<></span><span class="sxs-lookup"><span data-stu-id="39e75-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="39e75-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39e75-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="39e75-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="39e75-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="39e75-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="39e75-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e75-106">構文</span><span class="sxs-lookup"><span data-stu-id="39e75-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39e75-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="39e75-107">Attributes and Elements</span></span>  
 <span data-ttu-id="39e75-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="39e75-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39e75-109">属性</span><span class="sxs-lookup"><span data-stu-id="39e75-109">Attributes</span></span>  
  
|<span data-ttu-id="39e75-110">要素</span><span class="sxs-lookup"><span data-stu-id="39e75-110">Element</span></span>|<span data-ttu-id="39e75-111">説明</span><span class="sxs-lookup"><span data-stu-id="39e75-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39e75-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="39e75-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="39e75-113">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="39e75-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="39e75-114">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="39e75-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="39e75-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="39e75-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="39e75-116">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="39e75-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="39e75-117">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="39e75-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39e75-118">子要素</span><span class="sxs-lookup"><span data-stu-id="39e75-118">Child Elements</span></span>  
  
|<span data-ttu-id="39e75-119">要素</span><span class="sxs-lookup"><span data-stu-id="39e75-119">Element</span></span>|<span data-ttu-id="39e75-120">説明</span><span class="sxs-lookup"><span data-stu-id="39e75-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39e75-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="39e75-121">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="39e75-122">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="39e75-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="39e75-123">データコントラクトと既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39e75-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39e75-124">親要素</span><span class="sxs-lookup"><span data-stu-id="39e75-124">Parent Elements</span></span>  
  
|<span data-ttu-id="39e75-125">要素</span><span class="sxs-lookup"><span data-stu-id="39e75-125">Element</span></span>|<span data-ttu-id="39e75-126">説明</span><span class="sxs-lookup"><span data-stu-id="39e75-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39e75-127">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="39e75-127">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="39e75-128"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="39e75-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39e75-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="39e75-129">Remarks</span></span>  
 <span data-ttu-id="39e75-130">既知の型の詳細について<xref:System.Runtime.Serialization.DataContractSerializer>は、「」および「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39e75-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e75-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="39e75-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="39e75-132">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="39e75-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
