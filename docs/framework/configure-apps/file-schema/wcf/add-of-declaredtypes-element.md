---
title: <add> <declaredTypes>要素
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 1ea008dcc72d555b00e9648ace95bb9522ffc2c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920184"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="c33a7-102">\<declaredTypes > 要素\<の > の追加</span><span class="sxs-lookup"><span data-stu-id="c33a7-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="c33a7-103">逆シリアル化中に、<xref:System.Runtime.Serialization.DataContractSerializer> で使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="c33a7-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="c33a7-104">各宣言型は、宣言型のフィールドまたはプロパティとして返される既知の型を含みます。</span><span class="sxs-lookup"><span data-stu-id="c33a7-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="c33a7-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="c33a7-105">system.runtime.serialization</span></span>  
<span data-ttu-id="c33a7-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c33a7-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="c33a7-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c33a7-107">\<declaredTypes></span></span>  
<span data-ttu-id="c33a7-108">\<declaredTypes > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="c33a7-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33a7-109">構文</span><span class="sxs-lookup"><span data-stu-id="c33a7-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c33a7-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c33a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c33a7-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c33a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c33a7-112">属性</span><span class="sxs-lookup"><span data-stu-id="c33a7-112">Attributes</span></span>  
  
|<span data-ttu-id="c33a7-113">属性</span><span class="sxs-lookup"><span data-stu-id="c33a7-113">Attribute</span></span>|<span data-ttu-id="c33a7-114">説明</span><span class="sxs-lookup"><span data-stu-id="c33a7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c33a7-115">型</span><span class="sxs-lookup"><span data-stu-id="c33a7-115">type</span></span>|<span data-ttu-id="c33a7-116">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="c33a7-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="c33a7-117">型名 (名前空間を含む)、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c33a7-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c33a7-118">子要素</span><span class="sxs-lookup"><span data-stu-id="c33a7-118">Child Elements</span></span>  
  
|<span data-ttu-id="c33a7-119">要素</span><span class="sxs-lookup"><span data-stu-id="c33a7-119">Element</span></span>|<span data-ttu-id="c33a7-120">説明</span><span class="sxs-lookup"><span data-stu-id="c33a7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c33a7-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="c33a7-121">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="c33a7-122">追加される宣言型の既知の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c33a7-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="c33a7-123">宣言型がジェネリック型の場合は、既知の型を返すために使用されるジェネリック パラメーターを指定するために、`<knownType>` にパラメーター要素も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c33a7-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c33a7-124">親要素</span><span class="sxs-lookup"><span data-stu-id="c33a7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c33a7-125">要素</span><span class="sxs-lookup"><span data-stu-id="c33a7-125">Element</span></span>|<span data-ttu-id="c33a7-126">説明</span><span class="sxs-lookup"><span data-stu-id="c33a7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c33a7-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="c33a7-127">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="c33a7-128"><xref:System.Runtime.Serialization.DataContractSerializer> による逆シリアル化中に既知のタイプを必要とするタイプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c33a7-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c33a7-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="c33a7-129">Remarks</span></span>  
 <span data-ttu-id="c33a7-130">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c33a7-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="c33a7-131">この要素の使用例については、 [ \<dataContractSerializer >](datacontractserializer-element.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c33a7-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c33a7-132"><xref:System.Object> 型を `<declaredType>` として追加すると、<xref:System.Configuration.ConfigurationErrorsException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c33a7-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="c33a7-133">これは、構成で <xref:System.Object> 型を宣言型として使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="c33a7-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c33a7-134">例</span><span class="sxs-lookup"><span data-stu-id="c33a7-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c33a7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c33a7-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="c33a7-136">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="c33a7-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="c33a7-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c33a7-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="c33a7-138">\<declaredTypes > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="c33a7-138">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
