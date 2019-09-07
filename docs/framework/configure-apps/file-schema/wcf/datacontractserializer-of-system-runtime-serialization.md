---
title: <dataContractSerializer>< の > の。
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398079"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="dc861-102">\<dataContractSerializer > の\<></span><span class="sxs-lookup"><span data-stu-id="dc861-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="dc861-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc861-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="dc861-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc861-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc861-105">&nbsp;&nbsp;[ **\<> を実行します。** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="dc861-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="dc861-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="dc861-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc861-107">構文</span><span class="sxs-lookup"><span data-stu-id="dc861-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc861-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dc861-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc861-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc861-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc861-110">属性</span><span class="sxs-lookup"><span data-stu-id="dc861-110">Attributes</span></span>  
  
|<span data-ttu-id="dc861-111">要素</span><span class="sxs-lookup"><span data-stu-id="dc861-111">Element</span></span>|<span data-ttu-id="dc861-112">説明</span><span class="sxs-lookup"><span data-stu-id="dc861-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc861-113">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="dc861-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="dc861-114">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="dc861-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="dc861-115">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="dc861-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="dc861-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="dc861-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="dc861-117">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="dc861-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="dc861-118">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="dc861-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc861-119">子要素</span><span class="sxs-lookup"><span data-stu-id="dc861-119">Child Elements</span></span>  
  
|<span data-ttu-id="dc861-120">要素</span><span class="sxs-lookup"><span data-stu-id="dc861-120">Element</span></span>|<span data-ttu-id="dc861-121">説明</span><span class="sxs-lookup"><span data-stu-id="dc861-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc861-122">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="dc861-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="dc861-123">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc861-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="dc861-124">データコントラクトと既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc861-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc861-125">親要素</span><span class="sxs-lookup"><span data-stu-id="dc861-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dc861-126">要素</span><span class="sxs-lookup"><span data-stu-id="dc861-126">Element</span></span>|<span data-ttu-id="dc861-127">説明</span><span class="sxs-lookup"><span data-stu-id="dc861-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc861-128">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="dc861-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="dc861-129"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="dc861-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc861-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc861-130">Remarks</span></span>  
 <span data-ttu-id="dc861-131">既知の型の詳細について<xref:System.Runtime.Serialization.DataContractSerializer>は、「」および「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc861-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc861-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc861-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="dc861-133">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="dc861-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
