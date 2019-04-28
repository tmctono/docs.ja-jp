---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760689"
---
# <a name="knowntype"></a><span data-ttu-id="363aa-101">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="363aa-101">\<knownType></span></span>
<span data-ttu-id="363aa-102">逆シリアル化中に <xref:System.Runtime.Serialization.DataContractSerializer> によって使用される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="363aa-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="363aa-103">この要素には、"宣言型" のフィールドまたはプロパティによって返される "既知の型" を指定します。</span><span class="sxs-lookup"><span data-stu-id="363aa-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="363aa-104">詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="363aa-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="363aa-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="363aa-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="363aa-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="363aa-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="363aa-107">\<declaredTypes > 要素</span><span class="sxs-lookup"><span data-stu-id="363aa-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="363aa-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="363aa-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="363aa-109">\<knownType > 要素</span><span class="sxs-lookup"><span data-stu-id="363aa-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363aa-110">構文</span><span class="sxs-lookup"><span data-stu-id="363aa-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="363aa-111">型</span><span class="sxs-lookup"><span data-stu-id="363aa-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="363aa-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="363aa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="363aa-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="363aa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="363aa-114">属性</span><span class="sxs-lookup"><span data-stu-id="363aa-114">Attributes</span></span>  
  
|<span data-ttu-id="363aa-115">属性</span><span class="sxs-lookup"><span data-stu-id="363aa-115">Attribute</span></span>|<span data-ttu-id="363aa-116">説明</span><span class="sxs-lookup"><span data-stu-id="363aa-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="363aa-117">型</span><span class="sxs-lookup"><span data-stu-id="363aa-117">type</span></span>|<span data-ttu-id="363aa-118">型 (名前空間を含む)、アセンブリ名、バージョン、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="363aa-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="363aa-119">子要素</span><span class="sxs-lookup"><span data-stu-id="363aa-119">Child Elements</span></span>  
  
|<span data-ttu-id="363aa-120">要素</span><span class="sxs-lookup"><span data-stu-id="363aa-120">Element</span></span>|<span data-ttu-id="363aa-121">説明</span><span class="sxs-lookup"><span data-stu-id="363aa-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="363aa-122">\<パラメーター ></span><span class="sxs-lookup"><span data-stu-id="363aa-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="363aa-123">宣言型がジェネリック型である場合に、パラメーター インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="363aa-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="363aa-124">親要素</span><span class="sxs-lookup"><span data-stu-id="363aa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="363aa-125">要素</span><span class="sxs-lookup"><span data-stu-id="363aa-125">Element</span></span>|<span data-ttu-id="363aa-126">説明</span><span class="sxs-lookup"><span data-stu-id="363aa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="363aa-127">\<add></span><span class="sxs-lookup"><span data-stu-id="363aa-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="363aa-128">宣言されたタイプのコレクションに、宣言されたタイプを追加します。</span><span class="sxs-lookup"><span data-stu-id="363aa-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="363aa-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="363aa-129">Remarks</span></span>  
 <span data-ttu-id="363aa-130">既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)と<xref:System.Runtime.Serialization.DataContractSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="363aa-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="363aa-131">参照してください、 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)この要素の使用例についてはします。</span><span class="sxs-lookup"><span data-stu-id="363aa-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="363aa-132">例</span><span class="sxs-lookup"><span data-stu-id="363aa-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="363aa-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="363aa-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="363aa-134">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="363aa-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="363aa-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="363aa-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="363aa-136">\<add></span><span class="sxs-lookup"><span data-stu-id="363aa-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
