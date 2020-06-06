---
title: <add><declaredTypes>要素の
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400658"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="7b96f-102">\<add>\<declaredTypes>要素の</span><span class="sxs-lookup"><span data-stu-id="7b96f-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="7b96f-103">逆シリアル化中に、<xref:System.Runtime.Serialization.DataContractSerializer> で使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b96f-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7b96f-104">各宣言型は、宣言型のフィールドまたはプロパティとして返される既知の型を含みます。</span><span class="sxs-lookup"><span data-stu-id="7b96f-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7b96f-105">構文</span><span class="sxs-lookup"><span data-stu-id="7b96f-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b96f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b96f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7b96f-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b96f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b96f-108">属性</span><span class="sxs-lookup"><span data-stu-id="7b96f-108">Attributes</span></span>  
  
|<span data-ttu-id="7b96f-109">属性</span><span class="sxs-lookup"><span data-stu-id="7b96f-109">Attribute</span></span>|<span data-ttu-id="7b96f-110">説明</span><span class="sxs-lookup"><span data-stu-id="7b96f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b96f-111">type</span><span class="sxs-lookup"><span data-stu-id="7b96f-111">type</span></span>|<span data-ttu-id="7b96f-112">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="7b96f-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7b96f-113">型名 (名前空間を含む)、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b96f-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b96f-114">子要素</span><span class="sxs-lookup"><span data-stu-id="7b96f-114">Child Elements</span></span>  
  
|<span data-ttu-id="7b96f-115">要素</span><span class="sxs-lookup"><span data-stu-id="7b96f-115">Element</span></span>|<span data-ttu-id="7b96f-116">Description</span><span class="sxs-lookup"><span data-stu-id="7b96f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="7b96f-117">追加される宣言型の既知の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b96f-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="7b96f-118">宣言型がジェネリック型の場合は、既知の型を返すために使用されるジェネリック パラメーターを指定するために、`<knownType>` にパラメーター要素も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b96f-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b96f-119">親要素</span><span class="sxs-lookup"><span data-stu-id="7b96f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7b96f-120">要素</span><span class="sxs-lookup"><span data-stu-id="7b96f-120">Element</span></span>|<span data-ttu-id="7b96f-121">Description</span><span class="sxs-lookup"><span data-stu-id="7b96f-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="7b96f-122"><xref:System.Runtime.Serialization.DataContractSerializer> による逆シリアル化中に既知のタイプを必要とするタイプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b96f-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b96f-123">解説</span><span class="sxs-lookup"><span data-stu-id="7b96f-123">Remarks</span></span>  
 <span data-ttu-id="7b96f-124">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と「」を参照してください <xref:System.Runtime.Serialization.DataContractSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="7b96f-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7b96f-125">[\<dataContractSerializer>](datacontractserializer-element.md)この要素の使用例については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b96f-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b96f-126"><xref:System.Object> 型を `<declaredType>` として追加すると、<xref:System.Configuration.ConfigurationErrorsException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="7b96f-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="7b96f-127">これは、構成で <xref:System.Object> 型を宣言型として使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="7b96f-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b96f-128">例</span><span class="sxs-lookup"><span data-stu-id="7b96f-128">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="7b96f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b96f-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7b96f-130">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="7b96f-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="7b96f-131">\<add>の\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7b96f-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
