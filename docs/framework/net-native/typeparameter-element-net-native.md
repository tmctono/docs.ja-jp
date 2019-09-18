---
title: <TypeParameter>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0de00b9313b60b3a527dd0380ae90d82731a8c02
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049059"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="e56d8-102">\<TypeParameter > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="e56d8-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="e56d8-103">メソッドに渡される型引数により表される型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="e56d8-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e56d8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e56d8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e56d8-107">属性</span><span class="sxs-lookup"><span data-stu-id="e56d8-107">Attributes</span></span>  
  
|<span data-ttu-id="e56d8-108">属性</span><span class="sxs-lookup"><span data-stu-id="e56d8-108">Attribute</span></span>|<span data-ttu-id="e56d8-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="e56d8-109">Attribute type</span></span>|<span data-ttu-id="e56d8-110">説明</span><span class="sxs-lookup"><span data-stu-id="e56d8-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="e56d8-111">全般</span><span class="sxs-lookup"><span data-stu-id="e56d8-111">General</span></span>|<span data-ttu-id="e56d8-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-112">Required attribute.</span></span> <span data-ttu-id="e56d8-113"><xref:System.Type> 型のパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="e56d8-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="e56d8-114">たとえば、メソッド シグネチャ `Type.GetInterfaceMap(Type interfaceType)` の場合、`Name` 属性の値は "interfaceType" です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="e56d8-115">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e56d8-115">Reflection</span></span>|<span data-ttu-id="e56d8-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-116">Optional attribute.</span></span> <span data-ttu-id="e56d8-117">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e56d8-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="e56d8-118">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e56d8-118">Reflection</span></span>|<span data-ttu-id="e56d8-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-119">Optional attribute.</span></span> <span data-ttu-id="e56d8-120">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="e56d8-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="e56d8-121">リフレクション</span><span class="sxs-lookup"><span data-stu-id="e56d8-121">Reflection</span></span>|<span data-ttu-id="e56d8-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-122">Optional attribute.</span></span> <span data-ttu-id="e56d8-123">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e56d8-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="e56d8-124">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e56d8-124">Serialization</span></span>|<span data-ttu-id="e56d8-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-125">Optional attribute.</span></span> <span data-ttu-id="e56d8-126">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e56d8-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="e56d8-127">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e56d8-127">Serialization</span></span>|<span data-ttu-id="e56d8-128">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-128">Optional attribute.</span></span> <span data-ttu-id="e56d8-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="e56d8-130">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e56d8-130">Serialization</span></span>|<span data-ttu-id="e56d8-131">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-131">Optional attribute.</span></span> <span data-ttu-id="e56d8-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="e56d8-133">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e56d8-133">Serialization</span></span>|<span data-ttu-id="e56d8-134">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-134">Optional attribute.</span></span> <span data-ttu-id="e56d8-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="e56d8-136">Interop</span><span class="sxs-lookup"><span data-stu-id="e56d8-136">Interop</span></span>|<span data-ttu-id="e56d8-137">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-137">Optional attribute.</span></span> <span data-ttu-id="e56d8-138">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="e56d8-139">Interop</span><span class="sxs-lookup"><span data-stu-id="e56d8-139">Interop</span></span>|<span data-ttu-id="e56d8-140">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-140">Optional attribute.</span></span> <span data-ttu-id="e56d8-141">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="e56d8-142">Interop</span><span class="sxs-lookup"><span data-stu-id="e56d8-142">Interop</span></span>|<span data-ttu-id="e56d8-143">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-143">Optional attribute.</span></span> <span data-ttu-id="e56d8-144">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="e56d8-145">Name 属性</span><span class="sxs-lookup"><span data-stu-id="e56d8-145">Name attribute</span></span>  
  
|<span data-ttu-id="e56d8-146">値</span><span class="sxs-lookup"><span data-stu-id="e56d8-146">Value</span></span>|<span data-ttu-id="e56d8-147">説明</span><span class="sxs-lookup"><span data-stu-id="e56d8-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e56d8-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="e56d8-148">*parameter_name*</span></span>|<span data-ttu-id="e56d8-149"><xref:System.Type> 型のパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="e56d8-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="e56d8-150">たとえば、メソッド シグネチャ `Type.GetInterfaceMap(Type interfaceType)` の場合、`Name` 属性の値は "interfaceType" です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="e56d8-151">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="e56d8-151">All other attributes</span></span>  
  
|<span data-ttu-id="e56d8-152">値</span><span class="sxs-lookup"><span data-stu-id="e56d8-152">Value</span></span>|<span data-ttu-id="e56d8-153">説明</span><span class="sxs-lookup"><span data-stu-id="e56d8-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e56d8-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="e56d8-154">*policy_setting*</span></span>|<span data-ttu-id="e56d8-155">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="e56d8-156">指定できる値は、`All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="e56d8-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="e56d8-157">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e56d8-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e56d8-158">子要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-158">Child Elements</span></span>  
 <span data-ttu-id="e56d8-159">なし。</span><span class="sxs-lookup"><span data-stu-id="e56d8-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e56d8-160">親要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-160">Parent Elements</span></span>  
  
|<span data-ttu-id="e56d8-161">要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-161">Element</span></span>|<span data-ttu-id="e56d8-162">説明</span><span class="sxs-lookup"><span data-stu-id="e56d8-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e56d8-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="e56d8-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="e56d8-164">コンストラクターまたはメソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e56d8-165">Remarks</span><span class="sxs-lookup"><span data-stu-id="e56d8-165">Remarks</span></span>  
 <span data-ttu-id="e56d8-166">`<TypeParameter>` 要素は [\<Parameter>](parameter-element-net-native.md) 要素に似ていますが、<xref:System.Type> 型のパラメーターにのみ適用できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="e56d8-166">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="e56d8-167">これは、実行時に `Name` 属性により指定される型引数で表されるすべての型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e56d8-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="e56d8-168">たとえば、NewtonSoft の JSON シリアライザーには静的 `JsonConvert.DeserializeObject(String value, Type type)` メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e56d8-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="e56d8-169">次のリフレクション ディレクティブは、</span><span class="sxs-lookup"><span data-stu-id="e56d8-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="e56d8-170">`type` 引数により表されるランタイム型のメタデータをシリアル化で使用できるようにする必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e56d8-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="e56d8-171">これらのランタイム ディレクティブが次のソース コードを含むプロジェクトに適用された場合、</span><span class="sxs-lookup"><span data-stu-id="e56d8-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="e56d8-172">リフレクション ディレクティブによって、`StockQuote` 型のメタデータが実行時に NewtonSoft の JSON シリアライザーで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e56d8-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56d8-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="e56d8-173">See also</span></span>

- [<span data-ttu-id="e56d8-174">\<Method> 要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-174">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="e56d8-175">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="e56d8-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e56d8-176">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e56d8-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="e56d8-177">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="e56d8-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
