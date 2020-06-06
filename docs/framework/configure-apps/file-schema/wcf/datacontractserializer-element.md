---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400451"
---
# \<dataContractSerializer>
<span data-ttu-id="73ff3-101"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73ff3-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="73ff3-102">この要素は、2 つの異なる階層で使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ff3-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="73ff3-103">1 つは以下の「スキーマの階層」に示したもので、もう 1 つは「解説」に記載しています。</span><span class="sxs-lookup"><span data-stu-id="73ff3-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="73ff3-104">構文</span><span class="sxs-lookup"><span data-stu-id="73ff3-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73ff3-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73ff3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="73ff3-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73ff3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73ff3-107">属性</span><span class="sxs-lookup"><span data-stu-id="73ff3-107">Attributes</span></span>  
  
|<span data-ttu-id="73ff3-108">要素</span><span class="sxs-lookup"><span data-stu-id="73ff3-108">Element</span></span>|<span data-ttu-id="73ff3-109">説明</span><span class="sxs-lookup"><span data-stu-id="73ff3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73ff3-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="73ff3-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="73ff3-111">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="73ff3-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="73ff3-112">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="73ff3-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="73ff3-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="73ff3-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="73ff3-114">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="73ff3-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="73ff3-115">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="73ff3-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73ff3-116">子要素</span><span class="sxs-lookup"><span data-stu-id="73ff3-116">Child Elements</span></span>  
 <span data-ttu-id="73ff3-117">なし。</span><span class="sxs-lookup"><span data-stu-id="73ff3-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73ff3-118">親要素</span><span class="sxs-lookup"><span data-stu-id="73ff3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="73ff3-119">要素</span><span class="sxs-lookup"><span data-stu-id="73ff3-119">Element</span></span>|<span data-ttu-id="73ff3-120">説明</span><span class="sxs-lookup"><span data-stu-id="73ff3-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="73ff3-121">サービスの動作設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="73ff3-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="73ff3-122"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="73ff3-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73ff3-123">解説</span><span class="sxs-lookup"><span data-stu-id="73ff3-123">Remarks</span></span>  
 <span data-ttu-id="73ff3-124">このトピックの冒頭で述べたように、これは要素が存在する2番目の階層です \<X509Extension> 。</span><span class="sxs-lookup"><span data-stu-id="73ff3-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="73ff3-125">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73ff3-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ff3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="73ff3-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="73ff3-127">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="73ff3-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="73ff3-128">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="73ff3-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
