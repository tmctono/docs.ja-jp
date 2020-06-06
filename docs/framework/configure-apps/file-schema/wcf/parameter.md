---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400110"
---
# \<parameter>
<span data-ttu-id="a969b-101">宣言された型がジェネリック型である場合、ジェネリック パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a969b-101">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="a969b-102">構文</span><span class="sxs-lookup"><span data-stu-id="a969b-102">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a969b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a969b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a969b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a969b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a969b-105">属性</span><span class="sxs-lookup"><span data-stu-id="a969b-105">Attributes</span></span>  
  
|<span data-ttu-id="a969b-106">属性</span><span class="sxs-lookup"><span data-stu-id="a969b-106">Attribute</span></span>|<span data-ttu-id="a969b-107">説明</span><span class="sxs-lookup"><span data-stu-id="a969b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a969b-108">インデックス (index)</span><span class="sxs-lookup"><span data-stu-id="a969b-108">index</span></span>|<span data-ttu-id="a969b-109">宣言された型がジェネリック型である場合、既知の型を返すジェネリック パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a969b-109">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="a969b-110">type</span><span class="sxs-lookup"><span data-stu-id="a969b-110">type</span></span>|<span data-ttu-id="a969b-111">シリアル化と逆シリアル化で使用される既知の型を説明する文字列。</span><span class="sxs-lookup"><span data-stu-id="a969b-111">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="a969b-112">index 属性</span><span class="sxs-lookup"><span data-stu-id="a969b-112">index Attribute</span></span>  
  
|<span data-ttu-id="a969b-113">値</span><span class="sxs-lookup"><span data-stu-id="a969b-113">Value</span></span>|<span data-ttu-id="a969b-114">Description</span><span class="sxs-lookup"><span data-stu-id="a969b-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a969b-115">"0"</span><span class="sxs-lookup"><span data-stu-id="a969b-115">"0"</span></span>|<span data-ttu-id="a969b-116">ジェネリック型の最初のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a969b-116">The first parameter in the generic type.</span></span> <span data-ttu-id="a969b-117">たとえば、<xref:System.Collections.Generic.List%601> にはパラメーターが 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="a969b-117">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="a969b-118">宣言型として使用される場合、index は "0" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a969b-118">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="a969b-119">"1"</span><span class="sxs-lookup"><span data-stu-id="a969b-119">"1"</span></span>|<span data-ttu-id="a969b-120">ジェネリック型の 2 番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a969b-120">The second parameter in a generic type.</span></span> <span data-ttu-id="a969b-121">たとえば、<xref:System.Collections.Generic.Dictionary%602> には 2 つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a969b-121">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="a969b-122">2 番目のパラメーターによって既知の型が返される場合は、index 属性を "1" に設定します。</span><span class="sxs-lookup"><span data-stu-id="a969b-122">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a969b-123">子要素</span><span class="sxs-lookup"><span data-stu-id="a969b-123">Child Elements</span></span>  
 <span data-ttu-id="a969b-124">なし。</span><span class="sxs-lookup"><span data-stu-id="a969b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a969b-125">親要素</span><span class="sxs-lookup"><span data-stu-id="a969b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a969b-126">要素</span><span class="sxs-lookup"><span data-stu-id="a969b-126">Element</span></span>|<span data-ttu-id="a969b-127">Description</span><span class="sxs-lookup"><span data-stu-id="a969b-127">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="a969b-128">宣言型のフィールドまたはプロパティによって返される既知の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a969b-128">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a969b-129">解説</span><span class="sxs-lookup"><span data-stu-id="a969b-129">Remarks</span></span>  
 <span data-ttu-id="a969b-130">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と「」を参照してください <xref:System.Runtime.Serialization.DataContractSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="a969b-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="a969b-131">[\<dataContractSerializer>](datacontractserializer-element.md)この要素の使用例については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a969b-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="a969b-132">この構成要素に、両方の属性を同時に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a969b-132">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="a969b-133">両方の属性が設定された場合、<xref:System.Configuration.ConfigurationErrorsException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="a969b-133">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a969b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a969b-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="a969b-135">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="a969b-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
