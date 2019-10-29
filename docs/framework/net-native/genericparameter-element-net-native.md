---
title: <GenericParameter> 要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf2b06b14252f152c1eece6f9c0d317482a24b27
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039514"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="e5485-102">\<GenericParameter > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="e5485-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="e5485-103">ジェネリック型またはメソッドのパラメーターの型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e5485-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5485-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5485-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5485-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5485-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e5485-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5485-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5485-107">属性</span><span class="sxs-lookup"><span data-stu-id="e5485-107">Attributes</span></span>  
  
|<span data-ttu-id="e5485-108">属性</span><span class="sxs-lookup"><span data-stu-id="e5485-108">Attribute</span></span>|<span data-ttu-id="e5485-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="e5485-109">Attribute type</span></span>|<span data-ttu-id="e5485-110">説明</span><span class="sxs-lookup"><span data-stu-id="e5485-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="e5485-111">全般</span><span class="sxs-lookup"><span data-stu-id="e5485-111">General</span></span>|<span data-ttu-id="e5485-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-112">Required attribute.</span></span> <span data-ttu-id="e5485-113">ジェネリック パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="e5485-113">The name of the generic parameter.</span></span> <span data-ttu-id="e5485-114">たとえば、ジェネリック デリゲート <xref:System.Func%603> の場合、デリゲートの戻り値に実行時ポリシーを適用するための `Name` 属性の値は "TResult" です。</span><span class="sxs-lookup"><span data-stu-id="e5485-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="e5485-115">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e5485-115">Reflection</span></span>|<span data-ttu-id="e5485-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-116">Optional attribute.</span></span> <span data-ttu-id="e5485-117">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5485-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="e5485-118">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e5485-118">Reflection</span></span>|<span data-ttu-id="e5485-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-119">Optional attribute.</span></span> <span data-ttu-id="e5485-120">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="e5485-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="e5485-121">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e5485-121">Reflection</span></span>|<span data-ttu-id="e5485-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-122">Optional attribute.</span></span> <span data-ttu-id="e5485-123">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5485-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="e5485-124">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e5485-124">Serialization</span></span>|<span data-ttu-id="e5485-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-125">Optional attribute.</span></span> <span data-ttu-id="e5485-126">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e5485-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="e5485-127">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e5485-127">Serialization</span></span>|<span data-ttu-id="e5485-128">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-128">Optional attribute.</span></span> <span data-ttu-id="e5485-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="e5485-130">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e5485-130">Serialization</span></span>|<span data-ttu-id="e5485-131">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-131">Optional attribute.</span></span> <span data-ttu-id="e5485-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="e5485-133">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e5485-133">Serialization</span></span>|<span data-ttu-id="e5485-134">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-134">Optional attribute.</span></span> <span data-ttu-id="e5485-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="e5485-136">Interop</span><span class="sxs-lookup"><span data-stu-id="e5485-136">Interop</span></span>|<span data-ttu-id="e5485-137">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-137">Optional attribute.</span></span> <span data-ttu-id="e5485-138">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="e5485-139">Interop</span><span class="sxs-lookup"><span data-stu-id="e5485-139">Interop</span></span>|<span data-ttu-id="e5485-140">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-140">Optional attribute.</span></span> <span data-ttu-id="e5485-141">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="e5485-142">Interop</span><span class="sxs-lookup"><span data-stu-id="e5485-142">Interop</span></span>|<span data-ttu-id="e5485-143">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-143">Optional attribute.</span></span> <span data-ttu-id="e5485-144">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e5485-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="e5485-145">Name 属性</span><span class="sxs-lookup"><span data-stu-id="e5485-145">Name attribute</span></span>  
  
|<span data-ttu-id="e5485-146">[値]</span><span class="sxs-lookup"><span data-stu-id="e5485-146">Value</span></span>|<span data-ttu-id="e5485-147">説明</span><span class="sxs-lookup"><span data-stu-id="e5485-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e5485-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="e5485-148">*generic_parameter_name*</span></span>|<span data-ttu-id="e5485-149">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e5485-149">Required attribute.</span></span> <span data-ttu-id="e5485-150">ジェネリック型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="e5485-150">The name of the generic type parameter.</span></span> <span data-ttu-id="e5485-151">たとえば、ジェネリック デリゲート <xref:System.Func%603> の場合、*generic_parameter_name* の値 "TResult" によって、デリゲートの戻り値に実行時ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5485-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="e5485-152">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="e5485-152">All other attributes</span></span>  
  
|<span data-ttu-id="e5485-153">[値]</span><span class="sxs-lookup"><span data-stu-id="e5485-153">Value</span></span>|<span data-ttu-id="e5485-154">説明</span><span class="sxs-lookup"><span data-stu-id="e5485-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e5485-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="e5485-155">*policy_setting*</span></span>|<span data-ttu-id="e5485-156">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="e5485-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="e5485-157">指定できる値は、`All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="e5485-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="e5485-158">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5485-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5485-159">子要素</span><span class="sxs-lookup"><span data-stu-id="e5485-159">Child Elements</span></span>  
 <span data-ttu-id="e5485-160">なし。</span><span class="sxs-lookup"><span data-stu-id="e5485-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5485-161">親要素</span><span class="sxs-lookup"><span data-stu-id="e5485-161">Parent Elements</span></span>  
  
|<span data-ttu-id="e5485-162">要素</span><span class="sxs-lookup"><span data-stu-id="e5485-162">Element</span></span>|<span data-ttu-id="e5485-163">説明</span><span class="sxs-lookup"><span data-stu-id="e5485-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5485-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="e5485-164">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="e5485-165">コンストラクターまたはメソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e5485-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="e5485-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="e5485-166">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="e5485-167">クラスや構造体など、特定の型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e5485-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5485-168">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5485-168">Remarks</span></span>  
 <span data-ttu-id="e5485-169">`<GenericParameter>` 要素は [\<Method>](method-element-net-native.md) 要素または [\<Type>](type-element-net-native.md) 要素のいずれかの子で、ジェネリック型またはメソッド シグネチャでの名前によって指定される、特定のジェネリック型パラメーターにポリシーを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5485-169">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="e5485-170">`<GenericParameter>` 要素は、シリアライザーで使用する場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5485-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="e5485-171">次の例では、`<GenericParameter>` 要素を使用して、NewtonSoft の JSON シリアライザーの [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) メソッド オーバーロードの呼び出しで、`T` 型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e5485-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5485-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5485-172">See also</span></span>

- [<span data-ttu-id="e5485-173">\<Method> 要素</span><span class="sxs-lookup"><span data-stu-id="e5485-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="e5485-174">\<Type > 要素</span><span class="sxs-lookup"><span data-stu-id="e5485-174">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="e5485-175">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5485-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e5485-176">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e5485-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="e5485-177">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="e5485-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
