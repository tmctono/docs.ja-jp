---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152971"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="61edd-102">\<シリアル化></span><span class="sxs-lookup"><span data-stu-id="61edd-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="61edd-103"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="61edd-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="61edd-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="61edd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="61edd-105">&nbsp;&nbsp;**\<シリアル化>**</span><span class="sxs-lookup"><span data-stu-id="61edd-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61edd-106">構文</span><span class="sxs-lookup"><span data-stu-id="61edd-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61edd-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61edd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="61edd-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61edd-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61edd-109">属性</span><span class="sxs-lookup"><span data-stu-id="61edd-109">Attributes</span></span>  
 <span data-ttu-id="61edd-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="61edd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61edd-111">子要素</span><span class="sxs-lookup"><span data-stu-id="61edd-111">Child Elements</span></span>  
  
|<span data-ttu-id="61edd-112">要素</span><span class="sxs-lookup"><span data-stu-id="61edd-112">Element</span></span>|<span data-ttu-id="61edd-113">説明</span><span class="sxs-lookup"><span data-stu-id="61edd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61edd-114">\<データコントラクトシリアライザー></span><span class="sxs-lookup"><span data-stu-id="61edd-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="61edd-115">逆シリアル化時に使用される既知の型の追加を可能にします。</span><span class="sxs-lookup"><span data-stu-id="61edd-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61edd-116">親要素</span><span class="sxs-lookup"><span data-stu-id="61edd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="61edd-117">要素</span><span class="sxs-lookup"><span data-stu-id="61edd-117">Element</span></span>|<span data-ttu-id="61edd-118">説明</span><span class="sxs-lookup"><span data-stu-id="61edd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61edd-119">\<要素>構成</span><span class="sxs-lookup"><span data-stu-id="61edd-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="61edd-120">構成の最上位の要素。</span><span class="sxs-lookup"><span data-stu-id="61edd-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61edd-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="61edd-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="61edd-122">データ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="61edd-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="61edd-123">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="61edd-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
