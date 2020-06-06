---
title: <dataContractSerializer><の> の。
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398079"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="9cebe-102">\<dataContractSerializer> の \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="9cebe-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="9cebe-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cebe-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="9cebe-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cebe-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cebe-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9cebe-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cebe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cebe-107">属性</span><span class="sxs-lookup"><span data-stu-id="9cebe-107">Attributes</span></span>  
  
|<span data-ttu-id="9cebe-108">要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-108">Element</span></span>|<span data-ttu-id="9cebe-109">説明</span><span class="sxs-lookup"><span data-stu-id="9cebe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cebe-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="9cebe-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="9cebe-111">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="9cebe-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="9cebe-112">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="9cebe-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="9cebe-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="9cebe-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="9cebe-114">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="9cebe-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="9cebe-115">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="9cebe-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cebe-116">子要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-116">Child Elements</span></span>  
  
|<span data-ttu-id="9cebe-117">要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-117">Element</span></span>|<span data-ttu-id="9cebe-118">説明</span><span class="sxs-lookup"><span data-stu-id="9cebe-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="9cebe-119">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cebe-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="9cebe-120">データコントラクトと既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cebe-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cebe-121">親要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9cebe-122">要素</span><span class="sxs-lookup"><span data-stu-id="9cebe-122">Element</span></span>|<span data-ttu-id="9cebe-123">説明</span><span class="sxs-lookup"><span data-stu-id="9cebe-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="9cebe-124"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="9cebe-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cebe-125">解説</span><span class="sxs-lookup"><span data-stu-id="9cebe-125">Remarks</span></span>  
 <span data-ttu-id="9cebe-126">既知の型の詳細については、「」 <xref:System.Runtime.Serialization.DataContractSerializer> および「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cebe-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cebe-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cebe-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="9cebe-128">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="9cebe-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
