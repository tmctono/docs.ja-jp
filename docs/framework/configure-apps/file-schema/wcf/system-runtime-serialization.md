---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152971"
---
# \<system.runtime.serialization>
<span data-ttu-id="05297-102"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="05297-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="05297-103">構文</span><span class="sxs-lookup"><span data-stu-id="05297-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05297-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05297-104">Attributes and Elements</span></span>  
 <span data-ttu-id="05297-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05297-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05297-106">属性</span><span class="sxs-lookup"><span data-stu-id="05297-106">Attributes</span></span>  
 <span data-ttu-id="05297-107">なし。</span><span class="sxs-lookup"><span data-stu-id="05297-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05297-108">子要素</span><span class="sxs-lookup"><span data-stu-id="05297-108">Child Elements</span></span>  
  
|<span data-ttu-id="05297-109">要素</span><span class="sxs-lookup"><span data-stu-id="05297-109">Element</span></span>|<span data-ttu-id="05297-110">説明</span><span class="sxs-lookup"><span data-stu-id="05297-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="05297-111">逆シリアル化時に使用される既知の型の追加を可能にします。</span><span class="sxs-lookup"><span data-stu-id="05297-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05297-112">親要素</span><span class="sxs-lookup"><span data-stu-id="05297-112">Parent Elements</span></span>  
  
|<span data-ttu-id="05297-113">要素</span><span class="sxs-lookup"><span data-stu-id="05297-113">Element</span></span>|<span data-ttu-id="05297-114">説明</span><span class="sxs-lookup"><span data-stu-id="05297-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05297-115">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="05297-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="05297-116">構成の最上位の要素。</span><span class="sxs-lookup"><span data-stu-id="05297-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05297-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="05297-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="05297-118">データ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="05297-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="05297-119">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="05297-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
