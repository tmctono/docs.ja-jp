---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: cef34a8836c7b17fe9a85cac190090f42653df14
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919253"
---
# <a name="declaredtypes"></a><span data-ttu-id="89862-101">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="89862-101">\<declaredTypes></span></span>
<span data-ttu-id="89862-102">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89862-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="89862-103">データコントラクトと既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89862-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="89862-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="89862-104">system.runtime.serialization</span></span>  
<span data-ttu-id="89862-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="89862-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="89862-106">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="89862-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89862-107">構文</span><span class="sxs-lookup"><span data-stu-id="89862-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89862-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="89862-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89862-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89862-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89862-110">属性</span><span class="sxs-lookup"><span data-stu-id="89862-110">Attributes</span></span>  
 <span data-ttu-id="89862-111">なし。</span><span class="sxs-lookup"><span data-stu-id="89862-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89862-112">子要素</span><span class="sxs-lookup"><span data-stu-id="89862-112">Child Elements</span></span>  
  
|<span data-ttu-id="89862-113">要素</span><span class="sxs-lookup"><span data-stu-id="89862-113">Element</span></span>|<span data-ttu-id="89862-114">説明</span><span class="sxs-lookup"><span data-stu-id="89862-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89862-115">\<add></span><span class="sxs-lookup"><span data-stu-id="89862-115">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="89862-116">既知の型を必要とする型を追加します。</span><span class="sxs-lookup"><span data-stu-id="89862-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89862-117">親要素</span><span class="sxs-lookup"><span data-stu-id="89862-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89862-118">要素</span><span class="sxs-lookup"><span data-stu-id="89862-118">Element</span></span>|<span data-ttu-id="89862-119">説明</span><span class="sxs-lookup"><span data-stu-id="89862-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89862-120">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="89862-120">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="89862-121"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89862-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89862-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="89862-122">Remarks</span></span>  
 <span data-ttu-id="89862-123">既知の型の詳細については、「[データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」と<xref:System.Runtime.Serialization.DataContractSerializer>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89862-123">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89862-124">例</span><span class="sxs-lookup"><span data-stu-id="89862-124">Example</span></span>  
 <span data-ttu-id="89862-125">次の XML コードは、 `DataContractSerializer`要素に追加された宣言型と既知の型を示しています。</span><span class="sxs-lookup"><span data-stu-id="89862-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="89862-126">この例は、追加された 3 つの型を示しています。</span><span class="sxs-lookup"><span data-stu-id="89862-126">The example shows three types being added.</span></span> <span data-ttu-id="89862-127">最初の型は、"Item" という既知の型を使用する "Orders" という名前のカスタム型です。</span><span class="sxs-lookup"><span data-stu-id="89862-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="89862-128">2 つ目の宣言型は、既知の型として <xref:System.Collections.Generic.List%601> を使用する `Item` です。</span><span class="sxs-lookup"><span data-stu-id="89862-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="89862-129">最後の 3 つ目の宣言型は、<xref:System.Collections.Generic.Dictionary%602> です。</span><span class="sxs-lookup"><span data-stu-id="89862-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="89862-130"><xref:System.Collections.Generic.Dictionary%602> クラスの型は、2 種類のパラメーターを持つジェネリック型です。</span><span class="sxs-lookup"><span data-stu-id="89862-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="89862-131">最初のパラメーターはキーを表し、2 番目のパラメーターは値を表します。</span><span class="sxs-lookup"><span data-stu-id="89862-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="89862-132">次の例は、2 番目の型 (値) の <xref:System.Collections.Generic.List%601> を既知の型の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="89862-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="89862-133">`index` 属性を使用して、既知の型で使用する型パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="89862-134">この場合には、"1" に設定された index 属性 (コレクションは 0 から始まる) によって値型が示されます。</span><span class="sxs-lookup"><span data-stu-id="89862-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="89862-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="89862-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="89862-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="89862-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="89862-137">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="89862-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="89862-138">\<add></span><span class="sxs-lookup"><span data-stu-id="89862-138">\<add></span></span>](add-of-declaredtypes-element.md)
