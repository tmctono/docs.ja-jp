---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165894"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="28c63-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="28c63-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="28c63-103"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="28c63-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="28c63-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="28c63-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c63-105">構文</span><span class="sxs-lookup"><span data-stu-id="28c63-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28c63-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="28c63-106">Attributes and Elements</span></span>  
 <span data-ttu-id="28c63-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="28c63-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28c63-108">属性</span><span class="sxs-lookup"><span data-stu-id="28c63-108">Attributes</span></span>  
 <span data-ttu-id="28c63-109">なし。</span><span class="sxs-lookup"><span data-stu-id="28c63-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28c63-110">子要素</span><span class="sxs-lookup"><span data-stu-id="28c63-110">Child Elements</span></span>  
  
|<span data-ttu-id="28c63-111">要素</span><span class="sxs-lookup"><span data-stu-id="28c63-111">Element</span></span>|<span data-ttu-id="28c63-112">説明</span><span class="sxs-lookup"><span data-stu-id="28c63-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28c63-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="28c63-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="28c63-114">逆シリアル化時に使用される既知の型の追加を可能にします。</span><span class="sxs-lookup"><span data-stu-id="28c63-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28c63-115">親要素</span><span class="sxs-lookup"><span data-stu-id="28c63-115">Parent Elements</span></span>  
  
|<span data-ttu-id="28c63-116">要素</span><span class="sxs-lookup"><span data-stu-id="28c63-116">Element</span></span>|<span data-ttu-id="28c63-117">説明</span><span class="sxs-lookup"><span data-stu-id="28c63-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28c63-118">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="28c63-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="28c63-119">構成の最上位の要素。</span><span class="sxs-lookup"><span data-stu-id="28c63-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28c63-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="28c63-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="28c63-121">データ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="28c63-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="28c63-122">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="28c63-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
