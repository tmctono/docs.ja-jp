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
ms.openlocfilehash: 8919ee717012f8badcf7015bf8d850ed431c5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701165"
---
# <a name="declaredtypes"></a><span data-ttu-id="ec08b-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="ec08b-101">\<declaredTypes></span></span>
<span data-ttu-id="ec08b-102">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec08b-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="ec08b-103">データ コントラクトと既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="ec08b-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="ec08b-104">system.runtime.serialization</span></span>  
<span data-ttu-id="ec08b-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="ec08b-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="ec08b-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="ec08b-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec08b-107">構文</span><span class="sxs-lookup"><span data-stu-id="ec08b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec08b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ec08b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec08b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec08b-110">属性</span><span class="sxs-lookup"><span data-stu-id="ec08b-110">Attributes</span></span>  
 <span data-ttu-id="ec08b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ec08b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec08b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ec08b-112">Child Elements</span></span>  
  
|<span data-ttu-id="ec08b-113">要素</span><span class="sxs-lookup"><span data-stu-id="ec08b-113">Element</span></span>|<span data-ttu-id="ec08b-114">説明</span><span class="sxs-lookup"><span data-stu-id="ec08b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec08b-115">\<add></span><span class="sxs-lookup"><span data-stu-id="ec08b-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="ec08b-116">既知の型を必要とする型を追加します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec08b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ec08b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ec08b-118">要素</span><span class="sxs-lookup"><span data-stu-id="ec08b-118">Element</span></span>|<span data-ttu-id="ec08b-119">説明</span><span class="sxs-lookup"><span data-stu-id="ec08b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec08b-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ec08b-120">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ec08b-121"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec08b-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec08b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec08b-122">Remarks</span></span>  
 <span data-ttu-id="ec08b-123">既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)と<xref:System.Runtime.Serialization.DataContractSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-123">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec08b-124">例</span><span class="sxs-lookup"><span data-stu-id="ec08b-124">Example</span></span>  
 <span data-ttu-id="ec08b-125">宣言された型と既知の型に追加された次の XML コードを示しています、`DataContractSerializer`要素。</span><span class="sxs-lookup"><span data-stu-id="ec08b-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="ec08b-126">この例は、追加された 3 つの型を示しています。</span><span class="sxs-lookup"><span data-stu-id="ec08b-126">The example shows three types being added.</span></span> <span data-ttu-id="ec08b-127">最初の型は、"Item" という既知の型を使用する "Orders" という名前のカスタム型です。</span><span class="sxs-lookup"><span data-stu-id="ec08b-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="ec08b-128">2 つ目の宣言型は、既知の型として <xref:System.Collections.Generic.List%601> を使用する `Item` です。</span><span class="sxs-lookup"><span data-stu-id="ec08b-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="ec08b-129">最後の 3 つ目の宣言型は、<xref:System.Collections.Generic.Dictionary%602> です。</span><span class="sxs-lookup"><span data-stu-id="ec08b-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="ec08b-130"><xref:System.Collections.Generic.Dictionary%602> クラスの型は、2 種類のパラメーターを持つジェネリック型です。</span><span class="sxs-lookup"><span data-stu-id="ec08b-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="ec08b-131">最初のパラメーターはキーを表し、2 番目のパラメーターは値を表します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="ec08b-132">次の例は、2 番目の型 (値) の <xref:System.Collections.Generic.List%601> を既知の型の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="ec08b-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="ec08b-133">`index` 属性を使用して、既知の型で使用する型パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec08b-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="ec08b-134">この場合には、"1" に設定された index 属性 (コレクションは 0 から始まる) によって値型が示されます。</span><span class="sxs-lookup"><span data-stu-id="ec08b-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec08b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec08b-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="ec08b-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ec08b-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="ec08b-137">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="ec08b-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="ec08b-138">\<add></span><span class="sxs-lookup"><span data-stu-id="ec08b-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
