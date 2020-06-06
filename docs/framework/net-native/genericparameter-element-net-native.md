---
title: <GenericParameter>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: d0b18211206a8f9d4365ab3affe6d1c376003348
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128434"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="abd9f-102">\<GenericParameter>要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="abd9f-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="abd9f-103">ジェネリック型またはメソッドのパラメーターの型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abd9f-104">構文</span><span class="sxs-lookup"><span data-stu-id="abd9f-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abd9f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="abd9f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="abd9f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abd9f-107">属性</span><span class="sxs-lookup"><span data-stu-id="abd9f-107">Attributes</span></span>  
  
|<span data-ttu-id="abd9f-108">属性</span><span class="sxs-lookup"><span data-stu-id="abd9f-108">Attribute</span></span>|<span data-ttu-id="abd9f-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="abd9f-109">Attribute type</span></span>|<span data-ttu-id="abd9f-110">Description</span><span class="sxs-lookup"><span data-stu-id="abd9f-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="abd9f-111">全般</span><span class="sxs-lookup"><span data-stu-id="abd9f-111">General</span></span>|<span data-ttu-id="abd9f-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-112">Required attribute.</span></span> <span data-ttu-id="abd9f-113">ジェネリック パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="abd9f-113">The name of the generic parameter.</span></span> <span data-ttu-id="abd9f-114">たとえば、ジェネリック デリゲート <xref:System.Func%603> の場合、デリゲートの戻り値に実行時ポリシーを適用するための `Name` 属性の値は "TResult" です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="abd9f-115">リフレクション</span><span class="sxs-lookup"><span data-stu-id="abd9f-115">Reflection</span></span>|<span data-ttu-id="abd9f-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-116">Optional attribute.</span></span> <span data-ttu-id="abd9f-117">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="abd9f-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="abd9f-118">リフレクション</span><span class="sxs-lookup"><span data-stu-id="abd9f-118">Reflection</span></span>|<span data-ttu-id="abd9f-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-119">Optional attribute.</span></span> <span data-ttu-id="abd9f-120">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="abd9f-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="abd9f-121">リフレクション</span><span class="sxs-lookup"><span data-stu-id="abd9f-121">Reflection</span></span>|<span data-ttu-id="abd9f-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-122">Optional attribute.</span></span> <span data-ttu-id="abd9f-123">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="abd9f-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="abd9f-124">シリアル化</span><span class="sxs-lookup"><span data-stu-id="abd9f-124">Serialization</span></span>|<span data-ttu-id="abd9f-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-125">Optional attribute.</span></span> <span data-ttu-id="abd9f-126">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="abd9f-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="abd9f-127">シリアル化</span><span class="sxs-lookup"><span data-stu-id="abd9f-127">Serialization</span></span>|<span data-ttu-id="abd9f-128">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-128">Optional attribute.</span></span> <span data-ttu-id="abd9f-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="abd9f-130">シリアル化</span><span class="sxs-lookup"><span data-stu-id="abd9f-130">Serialization</span></span>|<span data-ttu-id="abd9f-131">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-131">Optional attribute.</span></span> <span data-ttu-id="abd9f-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="abd9f-133">シリアル化</span><span class="sxs-lookup"><span data-stu-id="abd9f-133">Serialization</span></span>|<span data-ttu-id="abd9f-134">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-134">Optional attribute.</span></span> <span data-ttu-id="abd9f-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="abd9f-136">Interop</span><span class="sxs-lookup"><span data-stu-id="abd9f-136">Interop</span></span>|<span data-ttu-id="abd9f-137">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-137">Optional attribute.</span></span> <span data-ttu-id="abd9f-138">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="abd9f-139">Interop</span><span class="sxs-lookup"><span data-stu-id="abd9f-139">Interop</span></span>|<span data-ttu-id="abd9f-140">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-140">Optional attribute.</span></span> <span data-ttu-id="abd9f-141">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="abd9f-142">Interop</span><span class="sxs-lookup"><span data-stu-id="abd9f-142">Interop</span></span>|<span data-ttu-id="abd9f-143">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-143">Optional attribute.</span></span> <span data-ttu-id="abd9f-144">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="abd9f-145">Name 属性</span><span class="sxs-lookup"><span data-stu-id="abd9f-145">Name attribute</span></span>  
  
|<span data-ttu-id="abd9f-146">値</span><span class="sxs-lookup"><span data-stu-id="abd9f-146">Value</span></span>|<span data-ttu-id="abd9f-147">[説明]</span><span class="sxs-lookup"><span data-stu-id="abd9f-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abd9f-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="abd9f-148">*generic_parameter_name*</span></span>|<span data-ttu-id="abd9f-149">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-149">Required attribute.</span></span> <span data-ttu-id="abd9f-150">ジェネリック型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="abd9f-150">The name of the generic type parameter.</span></span> <span data-ttu-id="abd9f-151">たとえば、ジェネリック デリゲート <xref:System.Func%603> の場合、*generic_parameter_name* の値 "TResult" によって、デリゲートの戻り値に実行時ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="abd9f-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="abd9f-152">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="abd9f-152">All other attributes</span></span>  
  
|<span data-ttu-id="abd9f-153">値</span><span class="sxs-lookup"><span data-stu-id="abd9f-153">Value</span></span>|<span data-ttu-id="abd9f-154">[説明]</span><span class="sxs-lookup"><span data-stu-id="abd9f-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abd9f-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="abd9f-155">*policy_setting*</span></span>|<span data-ttu-id="abd9f-156">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="abd9f-157">指定できる値は、`All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="abd9f-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="abd9f-158">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abd9f-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abd9f-159">子要素</span><span class="sxs-lookup"><span data-stu-id="abd9f-159">Child Elements</span></span>  
 <span data-ttu-id="abd9f-160">なし。</span><span class="sxs-lookup"><span data-stu-id="abd9f-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abd9f-161">親要素</span><span class="sxs-lookup"><span data-stu-id="abd9f-161">Parent Elements</span></span>  
  
|<span data-ttu-id="abd9f-162">要素</span><span class="sxs-lookup"><span data-stu-id="abd9f-162">Element</span></span>|<span data-ttu-id="abd9f-163">説明</span><span class="sxs-lookup"><span data-stu-id="abd9f-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="abd9f-164">コンストラクターまたはメソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="abd9f-165">クラスや構造体など、特定の型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-165">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abd9f-166">解説</span><span class="sxs-lookup"><span data-stu-id="abd9f-166">Remarks</span></span>  
 <span data-ttu-id="abd9f-167">要素は、 `<GenericParameter>` 要素または要素の子であり、 [\<Method>](method-element-net-native.md) [\<Type>](type-element-net-native.md) ジェネリック型またはメソッドシグネチャで名前によって指定される特定のジェネリック型パラメーターにポリシーを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="abd9f-167">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="abd9f-168">`<GenericParameter>` 要素は、シリアライザーで使用する場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="abd9f-168">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="abd9f-169">次の例では、要素を使用して、 `<GenericParameter>` `T` NewtonSoft JSON シリアライザーの[jsonconvert \<T> (String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm)メソッドオーバーロードの呼び出しで、型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abd9f-169">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abd9f-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="abd9f-170">See also</span></span>

- [<span data-ttu-id="abd9f-171">\<Method>Element</span><span class="sxs-lookup"><span data-stu-id="abd9f-171">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="abd9f-172">\<Type>Element</span><span class="sxs-lookup"><span data-stu-id="abd9f-172">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="abd9f-173">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="abd9f-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="abd9f-174">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="abd9f-174">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="abd9f-175">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="abd9f-175">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
