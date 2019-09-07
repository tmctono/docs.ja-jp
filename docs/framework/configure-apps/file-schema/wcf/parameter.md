---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400110"
---
# <a name="parameter"></a><span data-ttu-id="64c6d-101">\<パラメーター ></span><span class="sxs-lookup"><span data-stu-id="64c6d-101">\<parameter></span></span>
<span data-ttu-id="64c6d-102">宣言された型がジェネリック型である場合、ジェネリック パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="64c6d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64c6d-104">&nbsp;&nbsp;[ **\<> を実行します。** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="64c6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="64c6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="64c6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="64c6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownType >** ](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="64c6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="64c6d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<パラメーター >**</span><span class="sxs-lookup"><span data-stu-id="64c6d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64c6d-110">構文</span><span class="sxs-lookup"><span data-stu-id="64c6d-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64c6d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64c6d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="64c6d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64c6d-113">属性</span><span class="sxs-lookup"><span data-stu-id="64c6d-113">Attributes</span></span>  
  
|<span data-ttu-id="64c6d-114">属性</span><span class="sxs-lookup"><span data-stu-id="64c6d-114">Attribute</span></span>|<span data-ttu-id="64c6d-115">説明</span><span class="sxs-lookup"><span data-stu-id="64c6d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64c6d-116">インデックス</span><span class="sxs-lookup"><span data-stu-id="64c6d-116">index</span></span>|<span data-ttu-id="64c6d-117">宣言された型がジェネリック型である場合、既知の型を返すジェネリック パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="64c6d-118">型</span><span class="sxs-lookup"><span data-stu-id="64c6d-118">type</span></span>|<span data-ttu-id="64c6d-119">シリアル化と逆シリアル化で使用される既知の型を説明する文字列。</span><span class="sxs-lookup"><span data-stu-id="64c6d-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="64c6d-120">index 属性</span><span class="sxs-lookup"><span data-stu-id="64c6d-120">index Attribute</span></span>  
  
|<span data-ttu-id="64c6d-121">値</span><span class="sxs-lookup"><span data-stu-id="64c6d-121">Value</span></span>|<span data-ttu-id="64c6d-122">説明</span><span class="sxs-lookup"><span data-stu-id="64c6d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="64c6d-123">"0"</span><span class="sxs-lookup"><span data-stu-id="64c6d-123">"0"</span></span>|<span data-ttu-id="64c6d-124">ジェネリック型の最初のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="64c6d-124">The first parameter in the generic type.</span></span> <span data-ttu-id="64c6d-125">たとえば、<xref:System.Collections.Generic.List%601> にはパラメーターが 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="64c6d-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="64c6d-126">宣言型として使用される場合、index は "0" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="64c6d-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="64c6d-127">"1"</span><span class="sxs-lookup"><span data-stu-id="64c6d-127">"1"</span></span>|<span data-ttu-id="64c6d-128">ジェネリック型の 2 番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="64c6d-128">The second parameter in a generic type.</span></span> <span data-ttu-id="64c6d-129">たとえば、<xref:System.Collections.Generic.Dictionary%602> には 2 つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="64c6d-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="64c6d-130">2 番目のパラメーターによって既知の型が返される場合は、index 属性を "1" に設定します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64c6d-131">子要素</span><span class="sxs-lookup"><span data-stu-id="64c6d-131">Child Elements</span></span>  
 <span data-ttu-id="64c6d-132">なし。</span><span class="sxs-lookup"><span data-stu-id="64c6d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64c6d-133">親要素</span><span class="sxs-lookup"><span data-stu-id="64c6d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="64c6d-134">要素</span><span class="sxs-lookup"><span data-stu-id="64c6d-134">Element</span></span>|<span data-ttu-id="64c6d-135">説明</span><span class="sxs-lookup"><span data-stu-id="64c6d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64c6d-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="64c6d-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="64c6d-137">宣言型のフィールドまたはプロパティによって返される既知の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64c6d-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="64c6d-138">Remarks</span></span>  
 <span data-ttu-id="64c6d-139">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c6d-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="64c6d-140">この要素の使用例については、 [ \<dataContractSerializer >](datacontractserializer-element.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c6d-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="64c6d-141">この構成要素に、両方の属性を同時に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="64c6d-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="64c6d-142">両方の属性が設定された場合、<xref:System.Configuration.ConfigurationErrorsException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="64c6d-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c6d-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="64c6d-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="64c6d-144">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="64c6d-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="64c6d-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="64c6d-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="64c6d-146">\<add></span><span class="sxs-lookup"><span data-stu-id="64c6d-146">\<add></span></span>](add-of-declaredtypes-element.md)
