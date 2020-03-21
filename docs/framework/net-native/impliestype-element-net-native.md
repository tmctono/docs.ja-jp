---
title: <ImpliesType>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 57f4208233cd5e8544b4f1c254e3b0e0eaacd508
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181014"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="3ceca-102">\<要素 (.NET ネイティブ)>型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="3ceca-103">型にポリシーを適用します (含んでいる型またはメソッドにそのポリシーが適用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3ceca-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ceca-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ceca-104">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
             Browse="policy_type"  
             Dynamic="policy_type"  
             Serialize="policy_type"
             DataContractSerializer="policy_setting"  
             DataContractJsonSerializer="policy_setting"  
             XmlSerializer="policy_setting"  
             MarshalObject="policy_setting"  
             MarshalDelegate="policy_setting"  
             MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ceca-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ceca-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3ceca-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ceca-107">属性</span><span class="sxs-lookup"><span data-stu-id="3ceca-107">Attributes</span></span>  
  
|<span data-ttu-id="3ceca-108">属性</span><span class="sxs-lookup"><span data-stu-id="3ceca-108">Attribute</span></span>|<span data-ttu-id="3ceca-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="3ceca-109">Attribute type</span></span>|<span data-ttu-id="3ceca-110">説明</span><span class="sxs-lookup"><span data-stu-id="3ceca-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="3ceca-111">全般</span><span class="sxs-lookup"><span data-stu-id="3ceca-111">General</span></span>|<span data-ttu-id="3ceca-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-112">Required attribute.</span></span> <span data-ttu-id="3ceca-113">型名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="3ceca-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="3ceca-114">Reflection</span></span>|<span data-ttu-id="3ceca-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-115">Optional attribute.</span></span> <span data-ttu-id="3ceca-116">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ceca-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="3ceca-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="3ceca-117">Reflection</span></span>|<span data-ttu-id="3ceca-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-118">Optional attribute.</span></span> <span data-ttu-id="3ceca-119">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="3ceca-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="3ceca-120">リフレクション</span><span class="sxs-lookup"><span data-stu-id="3ceca-120">Reflection</span></span>|<span data-ttu-id="3ceca-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-121">Optional attribute.</span></span> <span data-ttu-id="3ceca-122">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ceca-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="3ceca-123">シリアル化</span><span class="sxs-lookup"><span data-stu-id="3ceca-123">Serialization</span></span>|<span data-ttu-id="3ceca-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-124">Optional attribute.</span></span> <span data-ttu-id="3ceca-125">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3ceca-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="3ceca-126">シリアル化</span><span class="sxs-lookup"><span data-stu-id="3ceca-126">Serialization</span></span>|<span data-ttu-id="3ceca-127">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-127">Optional attribute.</span></span> <span data-ttu-id="3ceca-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="3ceca-129">シリアル化</span><span class="sxs-lookup"><span data-stu-id="3ceca-129">Serialization</span></span>|<span data-ttu-id="3ceca-130">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-130">Optional attribute.</span></span> <span data-ttu-id="3ceca-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="3ceca-132">シリアル化</span><span class="sxs-lookup"><span data-stu-id="3ceca-132">Serialization</span></span>|<span data-ttu-id="3ceca-133">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-133">Optional attribute.</span></span> <span data-ttu-id="3ceca-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="3ceca-135">Interop</span><span class="sxs-lookup"><span data-stu-id="3ceca-135">Interop</span></span>|<span data-ttu-id="3ceca-136">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-136">Optional attribute.</span></span> <span data-ttu-id="3ceca-137">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="3ceca-138">Interop</span><span class="sxs-lookup"><span data-stu-id="3ceca-138">Interop</span></span>|<span data-ttu-id="3ceca-139">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-139">Optional attribute.</span></span> <span data-ttu-id="3ceca-140">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="3ceca-141">Interop</span><span class="sxs-lookup"><span data-stu-id="3ceca-141">Interop</span></span>|<span data-ttu-id="3ceca-142">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-142">Optional attribute.</span></span> <span data-ttu-id="3ceca-143">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="3ceca-144">Name 属性</span><span class="sxs-lookup"><span data-stu-id="3ceca-144">Name attribute</span></span>  
  
|<span data-ttu-id="3ceca-145">Value</span><span class="sxs-lookup"><span data-stu-id="3ceca-145">Value</span></span>|<span data-ttu-id="3ceca-146">説明</span><span class="sxs-lookup"><span data-stu-id="3ceca-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ceca-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="3ceca-147">*type_name*</span></span>|<span data-ttu-id="3ceca-148">型名です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-148">The type name.</span></span> <span data-ttu-id="3ceca-149">この `<ImpliesType>` 要素により表される型がそれを含んでいる `<Type>` 要素と同じ名前空間にある場合、*type_name* には名前空間なしで型の名前を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3ceca-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="3ceca-150">それ以外の場合は、*type_name* には完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ceca-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="3ceca-151">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="3ceca-151">All other attributes</span></span>  
  
|<span data-ttu-id="3ceca-152">Value</span><span class="sxs-lookup"><span data-stu-id="3ceca-152">Value</span></span>|<span data-ttu-id="3ceca-153">説明</span><span class="sxs-lookup"><span data-stu-id="3ceca-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ceca-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="3ceca-154">*policy_setting*</span></span>|<span data-ttu-id="3ceca-155">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="3ceca-156">指定できる値は、`All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="3ceca-157">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ceca-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ceca-158">子要素</span><span class="sxs-lookup"><span data-stu-id="3ceca-158">Child Elements</span></span>  
 <span data-ttu-id="3ceca-159">[なし] :</span><span class="sxs-lookup"><span data-stu-id="3ceca-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ceca-160">親要素</span><span class="sxs-lookup"><span data-stu-id="3ceca-160">Parent Elements</span></span>  
  
|<span data-ttu-id="3ceca-161">要素</span><span class="sxs-lookup"><span data-stu-id="3ceca-161">Element</span></span>|<span data-ttu-id="3ceca-162">説明</span><span class="sxs-lookup"><span data-stu-id="3ceca-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ceca-163">\<タイプ></span><span class="sxs-lookup"><span data-stu-id="3ceca-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="3ceca-164">型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="3ceca-165">\<入力インスタンス化></span><span class="sxs-lookup"><span data-stu-id="3ceca-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="3ceca-166">構築されたジェネリック型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="3ceca-167">\<方法></span><span class="sxs-lookup"><span data-stu-id="3ceca-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="3ceca-168">メソッドにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ceca-169">解説</span><span class="sxs-lookup"><span data-stu-id="3ceca-169">Remarks</span></span>  
 <span data-ttu-id="3ceca-170">`<ImpliesType>` 要素は主にライブラリによる使用を想定しています。</span><span class="sxs-lookup"><span data-stu-id="3ceca-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="3ceca-171">これは、次のシナリオに対応します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="3ceca-172">ルーチンを 1 つの型にリフレクションする必要がある場合、2 番目の型にもリフレクションする必要がある。</span><span class="sxs-lookup"><span data-stu-id="3ceca-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="3ceca-173">スタティック分析で必要であると示されないため、2 番目の型の暗黙的なインスタンス化のメタデータをそれ以外の方法で使用できない。</span><span class="sxs-lookup"><span data-stu-id="3ceca-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="3ceca-174">最も一般的には、2 つの型は共有型引数を持つジェネリックなインスタンス化です。</span><span class="sxs-lookup"><span data-stu-id="3ceca-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="3ceca-175">`<ImpliesType>` 要素は、その親要素により指定される型へのリフレクションが必要な場合、`<ImpliesType>` 要素によって指定される型へのリフレクションも暗黙的に必要になるという前提により定義されました。</span><span class="sxs-lookup"><span data-stu-id="3ceca-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="3ceca-176">たとえば、次のリフレクション ディレクティブは、`Explicit<T>` と `Implicit<T>` の 2 つの型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ceca-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="3ceca-177">このディレクティブは、`Explicit` のインスタンス化に `Dynamic` ポリシー設定が定義されていない場合は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="3ceca-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="3ceca-178">たとえば、`Explicit<Int32>` の場合、`Implicit<Int32>` はそのパブリック メンバーをルートとしてインスタンス化され、そのメタデータが動的プログラミングで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3ceca-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="3ceca-179">1 つ以上のシリアライザーに適用される、実際の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ceca-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="3ceca-180">ディレクティブは、型付けされたものを何`IList<`*か*`>`として反映する必要`List<`*something*`>`があるという要件をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3ceca-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="3ceca-181">`<ImpliesType>` 要素は `<Method>` 要素内にも配置できます。これは、ジェネリック メソッドのインスタンス化が型のインスタンス化へのリフレクションを暗黙的に決定する場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="3ceca-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="3ceca-182">たとえば、関連付けられている  型と  型と共に、特定のライブラリが動的にアクセスするジェネリック メソッド `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)`<xref:System.Collections.Generic.List%601><xref:System.Array> を考えます。</span><span class="sxs-lookup"><span data-stu-id="3ceca-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="3ceca-183">これは次のように表すことができます。</span><span class="sxs-lookup"><span data-stu-id="3ceca-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ceca-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ceca-184">See also</span></span>

- [<span data-ttu-id="3ceca-185">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレン</span><span class="sxs-lookup"><span data-stu-id="3ceca-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="3ceca-186">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="3ceca-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="3ceca-187">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="3ceca-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
