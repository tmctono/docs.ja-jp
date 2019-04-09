---
title: <dataContractSerializer> < system.runtime.serialization > の
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115363"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="82442-102">\<dataContractSerializer > の\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="82442-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="82442-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82442-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="82442-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="82442-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="82442-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="82442-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82442-106">構文</span><span class="sxs-lookup"><span data-stu-id="82442-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82442-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="82442-107">Attributes and Elements</span></span>  
 <span data-ttu-id="82442-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="82442-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82442-109">属性</span><span class="sxs-lookup"><span data-stu-id="82442-109">Attributes</span></span>  
  
|<span data-ttu-id="82442-110">要素</span><span class="sxs-lookup"><span data-stu-id="82442-110">Element</span></span>|<span data-ttu-id="82442-111">説明</span><span class="sxs-lookup"><span data-stu-id="82442-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82442-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="82442-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="82442-113">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="82442-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="82442-114">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="82442-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="82442-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="82442-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="82442-116">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="82442-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="82442-117">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="82442-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82442-118">子要素</span><span class="sxs-lookup"><span data-stu-id="82442-118">Child Elements</span></span>  
  
|<span data-ttu-id="82442-119">要素</span><span class="sxs-lookup"><span data-stu-id="82442-119">Element</span></span>|<span data-ttu-id="82442-120">説明</span><span class="sxs-lookup"><span data-stu-id="82442-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82442-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="82442-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="82442-122">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82442-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="82442-123">データ コントラクトと既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="82442-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82442-124">親要素</span><span class="sxs-lookup"><span data-stu-id="82442-124">Parent Elements</span></span>  
  
|<span data-ttu-id="82442-125">要素</span><span class="sxs-lookup"><span data-stu-id="82442-125">Element</span></span>|<span data-ttu-id="82442-126">説明</span><span class="sxs-lookup"><span data-stu-id="82442-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82442-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="82442-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="82442-128"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="82442-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82442-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="82442-129">Remarks</span></span>  
 <span data-ttu-id="82442-130">既知の型の詳細については、次を参照してください。<xref:System.Runtime.Serialization.DataContractSerializer>と[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="82442-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82442-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="82442-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="82442-132">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="82442-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
