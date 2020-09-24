---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183794"
---
# \<knownType>

<span data-ttu-id="9b225-101">逆シリアル化中に <xref:System.Runtime.Serialization.DataContractSerializer> によって使用される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b225-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="9b225-102">この要素には、"宣言型" のフィールドまたはプロパティによって返される "既知の型" を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b225-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="9b225-103">詳細については、「 [データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b225-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="9b225-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b225-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="9b225-105">種類</span><span class="sxs-lookup"><span data-stu-id="9b225-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b225-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b225-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9b225-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b225-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b225-108">属性</span><span class="sxs-lookup"><span data-stu-id="9b225-108">Attributes</span></span>  
  
|<span data-ttu-id="9b225-109">属性</span><span class="sxs-lookup"><span data-stu-id="9b225-109">Attribute</span></span>|<span data-ttu-id="9b225-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="9b225-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b225-111">type</span><span class="sxs-lookup"><span data-stu-id="9b225-111">type</span></span>|<span data-ttu-id="9b225-112">型 (名前空間を含む)、アセンブリ名、バージョン、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b225-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b225-113">子要素</span><span class="sxs-lookup"><span data-stu-id="9b225-113">Child Elements</span></span>  
  
|<span data-ttu-id="9b225-114">要素</span><span class="sxs-lookup"><span data-stu-id="9b225-114">Element</span></span>|<span data-ttu-id="9b225-115">説明</span><span class="sxs-lookup"><span data-stu-id="9b225-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="9b225-116">宣言型がジェネリック型である場合に、パラメーター インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b225-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b225-117">親要素</span><span class="sxs-lookup"><span data-stu-id="9b225-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9b225-118">要素</span><span class="sxs-lookup"><span data-stu-id="9b225-118">Element</span></span>|<span data-ttu-id="9b225-119">説明</span><span class="sxs-lookup"><span data-stu-id="9b225-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="9b225-120">宣言されたタイプのコレクションに、宣言されたタイプを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b225-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b225-121">解説</span><span class="sxs-lookup"><span data-stu-id="9b225-121">Remarks</span></span>  

 <span data-ttu-id="9b225-122">既知の型の詳細については、「 [データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md) 」と「」を参照してください <xref:System.Runtime.Serialization.DataContractSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="9b225-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="9b225-123">[\<dataContractSerializer>](datacontractserializer-element.md)この要素の使用例については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b225-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b225-124">例</span><span class="sxs-lookup"><span data-stu-id="9b225-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b225-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b225-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="9b225-126">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="9b225-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
