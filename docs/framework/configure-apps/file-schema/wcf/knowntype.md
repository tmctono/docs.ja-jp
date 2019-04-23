---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148838"
---
# <a name="knowntype"></a><span data-ttu-id="b5bbb-101">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="b5bbb-101">\<knownType></span></span>
<span data-ttu-id="b5bbb-102">逆シリアル化中に <xref:System.Runtime.Serialization.DataContractSerializer> によって使用される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="b5bbb-103">この要素には、"宣言型" のフィールドまたはプロパティによって返される "既知の型" を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="b5bbb-104">詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="b5bbb-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b5bbb-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="b5bbb-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b5bbb-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="b5bbb-107">\<declaredTypes > 要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="b5bbb-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="b5bbb-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="b5bbb-109">\<knownType > 要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5bbb-110">構文</span><span class="sxs-lookup"><span data-stu-id="b5bbb-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="b5bbb-111">型</span><span class="sxs-lookup"><span data-stu-id="b5bbb-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5bbb-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b5bbb-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5bbb-114">属性</span><span class="sxs-lookup"><span data-stu-id="b5bbb-114">Attributes</span></span>  
  
|<span data-ttu-id="b5bbb-115">属性</span><span class="sxs-lookup"><span data-stu-id="b5bbb-115">Attribute</span></span>|<span data-ttu-id="b5bbb-116">説明</span><span class="sxs-lookup"><span data-stu-id="b5bbb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5bbb-117">型</span><span class="sxs-lookup"><span data-stu-id="b5bbb-117">type</span></span>|<span data-ttu-id="b5bbb-118">型 (名前空間を含む)、アセンブリ名、バージョン、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5bbb-119">子要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-119">Child Elements</span></span>  
  
|<span data-ttu-id="b5bbb-120">要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-120">Element</span></span>|<span data-ttu-id="b5bbb-121">説明</span><span class="sxs-lookup"><span data-stu-id="b5bbb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5bbb-122">\<パラメーター ></span><span class="sxs-lookup"><span data-stu-id="b5bbb-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="b5bbb-123">宣言型がジェネリック型である場合に、パラメーター インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5bbb-124">親要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b5bbb-125">要素</span><span class="sxs-lookup"><span data-stu-id="b5bbb-125">Element</span></span>|<span data-ttu-id="b5bbb-126">説明</span><span class="sxs-lookup"><span data-stu-id="b5bbb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5bbb-127">\<add></span><span class="sxs-lookup"><span data-stu-id="b5bbb-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="b5bbb-128">宣言されたタイプのコレクションに、宣言されたタイプを追加します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5bbb-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5bbb-129">Remarks</span></span>  
 <span data-ttu-id="b5bbb-130">既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)と<xref:System.Runtime.Serialization.DataContractSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b5bbb-131">参照してください、 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)この要素の使用例についてはします。</span><span class="sxs-lookup"><span data-stu-id="b5bbb-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5bbb-132">例</span><span class="sxs-lookup"><span data-stu-id="b5bbb-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b5bbb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5bbb-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="b5bbb-134">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="b5bbb-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="b5bbb-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b5bbb-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="b5bbb-136">\<add></span><span class="sxs-lookup"><span data-stu-id="b5bbb-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
