---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397874"
---
# <a name="knowntype"></a><span data-ttu-id="d4b42-101">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="d4b42-101">\<knownType></span></span>
<span data-ttu-id="d4b42-102">逆シリアル化中に <xref:System.Runtime.Serialization.DataContractSerializer> によって使用される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="d4b42-103">この要素には、"宣言型" のフィールドまたはプロパティによって返される "既知の型" を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="d4b42-104">詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b42-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="d4b42-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4b42-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4b42-106">&nbsp;&nbsp;[ **\<> を実行します。** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="d4b42-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="d4b42-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="d4b42-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="d4b42-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="d4b42-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="d4b42-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4b42-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="d4b42-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownType >**</span><span class="sxs-lookup"><span data-stu-id="d4b42-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b42-111">構文</span><span class="sxs-lookup"><span data-stu-id="d4b42-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="d4b42-112">型</span><span class="sxs-lookup"><span data-stu-id="d4b42-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4b42-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4b42-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d4b42-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4b42-115">属性</span><span class="sxs-lookup"><span data-stu-id="d4b42-115">Attributes</span></span>  
  
|<span data-ttu-id="d4b42-116">属性</span><span class="sxs-lookup"><span data-stu-id="d4b42-116">Attribute</span></span>|<span data-ttu-id="d4b42-117">説明</span><span class="sxs-lookup"><span data-stu-id="d4b42-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4b42-118">型</span><span class="sxs-lookup"><span data-stu-id="d4b42-118">type</span></span>|<span data-ttu-id="d4b42-119">型 (名前空間を含む)、アセンブリ名、バージョン、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4b42-120">子要素</span><span class="sxs-lookup"><span data-stu-id="d4b42-120">Child Elements</span></span>  
  
|<span data-ttu-id="d4b42-121">要素</span><span class="sxs-lookup"><span data-stu-id="d4b42-121">Element</span></span>|<span data-ttu-id="d4b42-122">説明</span><span class="sxs-lookup"><span data-stu-id="d4b42-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b42-123">\<パラメーター ></span><span class="sxs-lookup"><span data-stu-id="d4b42-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="d4b42-124">宣言型がジェネリック型である場合に、パラメーター インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4b42-125">親要素</span><span class="sxs-lookup"><span data-stu-id="d4b42-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d4b42-126">要素</span><span class="sxs-lookup"><span data-stu-id="d4b42-126">Element</span></span>|<span data-ttu-id="d4b42-127">説明</span><span class="sxs-lookup"><span data-stu-id="d4b42-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b42-128">\<add></span><span class="sxs-lookup"><span data-stu-id="d4b42-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="d4b42-129">宣言されたタイプのコレクションに、宣言されたタイプを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4b42-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4b42-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4b42-130">Remarks</span></span>  
 <span data-ttu-id="d4b42-131">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b42-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d4b42-132">この要素の使用例については、 [ \<dataContractSerializer >](datacontractserializer-element.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b42-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b42-133">例</span><span class="sxs-lookup"><span data-stu-id="d4b42-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d4b42-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4b42-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="d4b42-135">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="d4b42-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="d4b42-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="d4b42-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="d4b42-137">\<add></span><span class="sxs-lookup"><span data-stu-id="d4b42-137">\<add></span></span>](add-of-declaredtypes-element.md)
