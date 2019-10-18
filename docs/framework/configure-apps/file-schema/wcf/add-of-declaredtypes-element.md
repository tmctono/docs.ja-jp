---
title: <add> <declaredTypes>要素
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400658"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="99796-102">\<declaredTypes > 要素\<の > の追加</span><span class="sxs-lookup"><span data-stu-id="99796-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="99796-103">逆シリアル化中に、<xref:System.Runtime.Serialization.DataContractSerializer> で使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="99796-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="99796-104">各宣言型は、宣言型のフィールドまたはプロパティとして返される既知の型を含みます。</span><span class="sxs-lookup"><span data-stu-id="99796-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="99796-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99796-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99796-106">&nbsp;&nbsp;[ **\<> を実行します。** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="99796-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="99796-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="99796-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="99796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="99796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="99796-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="99796-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99796-110">構文</span><span class="sxs-lookup"><span data-stu-id="99796-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99796-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99796-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99796-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99796-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99796-113">属性</span><span class="sxs-lookup"><span data-stu-id="99796-113">Attributes</span></span>  
  
|<span data-ttu-id="99796-114">属性</span><span class="sxs-lookup"><span data-stu-id="99796-114">Attribute</span></span>|<span data-ttu-id="99796-115">説明</span><span class="sxs-lookup"><span data-stu-id="99796-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99796-116">型</span><span class="sxs-lookup"><span data-stu-id="99796-116">type</span></span>|<span data-ttu-id="99796-117">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="99796-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="99796-118">型名 (名前空間を含む)、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="99796-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99796-119">子要素</span><span class="sxs-lookup"><span data-stu-id="99796-119">Child Elements</span></span>  
  
|<span data-ttu-id="99796-120">要素</span><span class="sxs-lookup"><span data-stu-id="99796-120">Element</span></span>|<span data-ttu-id="99796-121">説明</span><span class="sxs-lookup"><span data-stu-id="99796-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99796-122">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="99796-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="99796-123">追加される宣言型の既知の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="99796-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="99796-124">宣言型がジェネリック型の場合は、既知の型を返すために使用されるジェネリック パラメーターを指定するために、`<knownType>` にパラメーター要素も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99796-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99796-125">親要素</span><span class="sxs-lookup"><span data-stu-id="99796-125">Parent Elements</span></span>  
  
|<span data-ttu-id="99796-126">要素</span><span class="sxs-lookup"><span data-stu-id="99796-126">Element</span></span>|<span data-ttu-id="99796-127">説明</span><span class="sxs-lookup"><span data-stu-id="99796-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99796-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="99796-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="99796-129"><xref:System.Runtime.Serialization.DataContractSerializer> による逆シリアル化中に既知のタイプを必要とするタイプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99796-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99796-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="99796-130">Remarks</span></span>  
 <span data-ttu-id="99796-131">既知の型の詳細については、「[既知のデータ コントラクト型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99796-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="99796-132">この要素の使用例については、 [ \<dataContractSerializer >](datacontractserializer-element.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99796-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99796-133"><xref:System.Object> 型を `<declaredType>` として追加すると、<xref:System.Configuration.ConfigurationErrorsException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="99796-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="99796-134">これは、構成で <xref:System.Object> 型を宣言型として使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="99796-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99796-135">例</span><span class="sxs-lookup"><span data-stu-id="99796-135">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99796-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="99796-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="99796-137">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="99796-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="99796-138">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="99796-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="99796-139">\<declaredTypes > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="99796-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
