---
title: <TypeParameter> 要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b03c87c70fa1bfcd331f468d369632f4164300bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110215"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="77dc4-102">\<TypeParameter > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="77dc4-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="77dc4-103">メソッドに渡される型引数により表される型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77dc4-104">構文</span><span class="sxs-lookup"><span data-stu-id="77dc4-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77dc4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="77dc4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77dc4-107">属性</span><span class="sxs-lookup"><span data-stu-id="77dc4-107">Attributes</span></span>  
  
|<span data-ttu-id="77dc4-108">属性</span><span class="sxs-lookup"><span data-stu-id="77dc4-108">Attribute</span></span>|<span data-ttu-id="77dc4-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="77dc4-109">Attribute type</span></span>|<span data-ttu-id="77dc4-110">説明</span><span class="sxs-lookup"><span data-stu-id="77dc4-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="77dc4-111">全般</span><span class="sxs-lookup"><span data-stu-id="77dc4-111">General</span></span>|<span data-ttu-id="77dc4-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-112">Required attribute.</span></span> <span data-ttu-id="77dc4-113"><xref:System.Type> 型のパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="77dc4-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="77dc4-114">たとえば、メソッド シグネチャ `Type.GetInterfaceMap(Type interfaceType)` の場合、`Name` 属性の値は "interfaceType" です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="77dc4-115">リフレクション</span><span class="sxs-lookup"><span data-stu-id="77dc4-115">Reflection</span></span>|<span data-ttu-id="77dc4-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-116">Optional attribute.</span></span> <span data-ttu-id="77dc4-117">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="77dc4-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="77dc4-118">リフレクション</span><span class="sxs-lookup"><span data-stu-id="77dc4-118">Reflection</span></span>|<span data-ttu-id="77dc4-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-119">Optional attribute.</span></span> <span data-ttu-id="77dc4-120">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="77dc4-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="77dc4-121">リフレクション</span><span class="sxs-lookup"><span data-stu-id="77dc4-121">Reflection</span></span>|<span data-ttu-id="77dc4-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-122">Optional attribute.</span></span> <span data-ttu-id="77dc4-123">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="77dc4-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="77dc4-124">シリアル化</span><span class="sxs-lookup"><span data-stu-id="77dc4-124">Serialization</span></span>|<span data-ttu-id="77dc4-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-125">Optional attribute.</span></span> <span data-ttu-id="77dc4-126">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="77dc4-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="77dc4-127">シリアル化</span><span class="sxs-lookup"><span data-stu-id="77dc4-127">Serialization</span></span>|<span data-ttu-id="77dc4-128">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-128">Optional attribute.</span></span> <span data-ttu-id="77dc4-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="77dc4-130">シリアル化</span><span class="sxs-lookup"><span data-stu-id="77dc4-130">Serialization</span></span>|<span data-ttu-id="77dc4-131">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-131">Optional attribute.</span></span> <span data-ttu-id="77dc4-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="77dc4-133">シリアル化</span><span class="sxs-lookup"><span data-stu-id="77dc4-133">Serialization</span></span>|<span data-ttu-id="77dc4-134">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-134">Optional attribute.</span></span> <span data-ttu-id="77dc4-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="77dc4-136">Interop</span><span class="sxs-lookup"><span data-stu-id="77dc4-136">Interop</span></span>|<span data-ttu-id="77dc4-137">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-137">Optional attribute.</span></span> <span data-ttu-id="77dc4-138">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="77dc4-139">Interop</span><span class="sxs-lookup"><span data-stu-id="77dc4-139">Interop</span></span>|<span data-ttu-id="77dc4-140">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-140">Optional attribute.</span></span> <span data-ttu-id="77dc4-141">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="77dc4-142">Interop</span><span class="sxs-lookup"><span data-stu-id="77dc4-142">Interop</span></span>|<span data-ttu-id="77dc4-143">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-143">Optional attribute.</span></span> <span data-ttu-id="77dc4-144">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="77dc4-145">Name 属性</span><span class="sxs-lookup"><span data-stu-id="77dc4-145">Name attribute</span></span>  
  
|<span data-ttu-id="77dc4-146">[値]</span><span class="sxs-lookup"><span data-stu-id="77dc4-146">Value</span></span>|<span data-ttu-id="77dc4-147">説明</span><span class="sxs-lookup"><span data-stu-id="77dc4-147">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="77dc4-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="77dc4-148">parameter_name</span></span>*|<span data-ttu-id="77dc4-149"><xref:System.Type> 型のパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="77dc4-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="77dc4-150">たとえば、メソッド シグネチャ `Type.GetInterfaceMap(Type interfaceType)` の場合、`Name` 属性の値は "interfaceType" です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="77dc4-151">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="77dc4-151">All other attributes</span></span>  
  
|<span data-ttu-id="77dc4-152">[値]</span><span class="sxs-lookup"><span data-stu-id="77dc4-152">Value</span></span>|<span data-ttu-id="77dc4-153">説明</span><span class="sxs-lookup"><span data-stu-id="77dc4-153">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="77dc4-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="77dc4-154">policy_setting</span></span>*|<span data-ttu-id="77dc4-155">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="77dc4-156">指定できる値は、`All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="77dc4-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="77dc4-157">詳細については、「[ランタイム ディレクティブのポリシー設定](../../../docs/framework/net-native/runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77dc4-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77dc4-158">子要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-158">Child Elements</span></span>  
 <span data-ttu-id="77dc4-159">なし。</span><span class="sxs-lookup"><span data-stu-id="77dc4-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77dc4-160">親要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-160">Parent Elements</span></span>  
  
|<span data-ttu-id="77dc4-161">要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-161">Element</span></span>|<span data-ttu-id="77dc4-162">説明</span><span class="sxs-lookup"><span data-stu-id="77dc4-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77dc4-163">\<メソッド ></span><span class="sxs-lookup"><span data-stu-id="77dc4-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="77dc4-164">コンストラクターまたはメソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77dc4-165">Remarks</span><span class="sxs-lookup"><span data-stu-id="77dc4-165">Remarks</span></span>  
 <span data-ttu-id="77dc4-166">`<TypeParameter>` 要素は [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) 要素に似ていますが、<xref:System.Type> 型のパラメーターにのみ適用できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="77dc4-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="77dc4-167">これは、実行時に `Name` 属性により指定される型引数で表されるすべての型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="77dc4-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="77dc4-168">たとえば、NewtonSoft の JSON シリアライザーには静的 `JsonConvert.DeserializeObject(String value, Type type)` メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="77dc4-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="77dc4-169">次のリフレクション ディレクティブは、</span><span class="sxs-lookup"><span data-stu-id="77dc4-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="77dc4-170">`type` 引数により表されるランタイム型のメタデータをシリアル化で使用できるようにする必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="77dc4-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="77dc4-171">これらのランタイム ディレクティブが次のソース コードを含むプロジェクトに適用された場合、</span><span class="sxs-lookup"><span data-stu-id="77dc4-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="77dc4-172">リフレクション ディレクティブによって、`StockQuote` 型のメタデータが実行時に NewtonSoft の JSON シリアライザーで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="77dc4-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77dc4-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="77dc4-173">See also</span></span>

- [<span data-ttu-id="77dc4-174">\<メソッド > 要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="77dc4-175">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="77dc4-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="77dc4-176">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="77dc4-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="77dc4-177">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="77dc4-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
