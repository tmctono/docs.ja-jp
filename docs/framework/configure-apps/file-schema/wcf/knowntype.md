---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928870"
---
# <a name="knowntype"></a><span data-ttu-id="05ed2-101">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="05ed2-101">\<knownType></span></span>
<span data-ttu-id="05ed2-102">逆シリアル化中に <xref:System.Runtime.Serialization.DataContractSerializer> によって使用される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="05ed2-103">この要素には、"宣言型" のフィールドまたはプロパティによって返される "既知の型" を指定します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="05ed2-104">詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05ed2-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="05ed2-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="05ed2-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="05ed2-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="05ed2-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="05ed2-107">\<declaredTypes > 要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="05ed2-108">\<declaredTypes > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="05ed2-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="05ed2-109">\<knownType > 要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05ed2-110">構文</span><span class="sxs-lookup"><span data-stu-id="05ed2-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="05ed2-111">型</span><span class="sxs-lookup"><span data-stu-id="05ed2-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05ed2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="05ed2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05ed2-114">属性</span><span class="sxs-lookup"><span data-stu-id="05ed2-114">Attributes</span></span>  
  
|<span data-ttu-id="05ed2-115">属性</span><span class="sxs-lookup"><span data-stu-id="05ed2-115">Attribute</span></span>|<span data-ttu-id="05ed2-116">説明</span><span class="sxs-lookup"><span data-stu-id="05ed2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05ed2-117">型</span><span class="sxs-lookup"><span data-stu-id="05ed2-117">type</span></span>|<span data-ttu-id="05ed2-118">型 (名前空間を含む)、アセンブリ名、バージョン、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05ed2-119">子要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-119">Child Elements</span></span>  
  
|<span data-ttu-id="05ed2-120">要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-120">Element</span></span>|<span data-ttu-id="05ed2-121">説明</span><span class="sxs-lookup"><span data-stu-id="05ed2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05ed2-122">\<パラメーター ></span><span class="sxs-lookup"><span data-stu-id="05ed2-122">\<parameter></span></span>](parameter.md)|<span data-ttu-id="05ed2-123">宣言型がジェネリック型である場合に、パラメーター インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05ed2-124">親要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="05ed2-125">要素</span><span class="sxs-lookup"><span data-stu-id="05ed2-125">Element</span></span>|<span data-ttu-id="05ed2-126">説明</span><span class="sxs-lookup"><span data-stu-id="05ed2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05ed2-127">\<add></span><span class="sxs-lookup"><span data-stu-id="05ed2-127">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="05ed2-128">宣言されたタイプのコレクションに、宣言されたタイプを追加します。</span><span class="sxs-lookup"><span data-stu-id="05ed2-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05ed2-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="05ed2-129">Remarks</span></span>  
 <span data-ttu-id="05ed2-130">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05ed2-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="05ed2-131">この要素の使用例については、 [ \<dataContractSerializer >](datacontractserializer-element.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05ed2-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05ed2-132">例</span><span class="sxs-lookup"><span data-stu-id="05ed2-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05ed2-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="05ed2-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="05ed2-134">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="05ed2-134">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="05ed2-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="05ed2-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="05ed2-136">\<add></span><span class="sxs-lookup"><span data-stu-id="05ed2-136">\<add></span></span>](add-of-declaredtypes-element.md)
