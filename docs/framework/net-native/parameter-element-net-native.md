---
title: <Parameter>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: c6dfc347d44a794ee8496c45ca879f9daab12b22
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128198"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="0522d-102">\<Parameter>要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="0522d-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="0522d-103">メソッドに渡された引数の型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="0522d-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0522d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0522d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0522d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0522d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0522d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0522d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0522d-107">属性</span><span class="sxs-lookup"><span data-stu-id="0522d-107">Attributes</span></span>  
  
|<span data-ttu-id="0522d-108">属性</span><span class="sxs-lookup"><span data-stu-id="0522d-108">Attribute</span></span>|<span data-ttu-id="0522d-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="0522d-109">Attribute type</span></span>|<span data-ttu-id="0522d-110">Description</span><span class="sxs-lookup"><span data-stu-id="0522d-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0522d-111">全般</span><span class="sxs-lookup"><span data-stu-id="0522d-111">General</span></span>|<span data-ttu-id="0522d-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-112">Required attribute.</span></span> <span data-ttu-id="0522d-113">パラメーター名。</span><span class="sxs-lookup"><span data-stu-id="0522d-113">The parameter name.</span></span> <span data-ttu-id="0522d-114">たとえば、メソッド シグネチャ `String.CompareTo(Object value)` の場合、`Name` 属性の値は "value" です。</span><span class="sxs-lookup"><span data-stu-id="0522d-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="0522d-115">リフレクション</span><span class="sxs-lookup"><span data-stu-id="0522d-115">Reflection</span></span>|<span data-ttu-id="0522d-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-116">Optional attribute.</span></span> <span data-ttu-id="0522d-117">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0522d-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0522d-118">リフレクション</span><span class="sxs-lookup"><span data-stu-id="0522d-118">Reflection</span></span>|<span data-ttu-id="0522d-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-119">Optional attribute.</span></span> <span data-ttu-id="0522d-120">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="0522d-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0522d-121">リフレクション</span><span class="sxs-lookup"><span data-stu-id="0522d-121">Reflection</span></span>|<span data-ttu-id="0522d-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-122">Optional attribute.</span></span> <span data-ttu-id="0522d-123">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0522d-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0522d-124">シリアル化</span><span class="sxs-lookup"><span data-stu-id="0522d-124">Serialization</span></span>|<span data-ttu-id="0522d-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-125">Optional attribute.</span></span> <span data-ttu-id="0522d-126">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0522d-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0522d-127">シリアル化</span><span class="sxs-lookup"><span data-stu-id="0522d-127">Serialization</span></span>|<span data-ttu-id="0522d-128">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-128">Optional attribute.</span></span> <span data-ttu-id="0522d-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0522d-130">シリアル化</span><span class="sxs-lookup"><span data-stu-id="0522d-130">Serialization</span></span>|<span data-ttu-id="0522d-131">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-131">Optional attribute.</span></span> <span data-ttu-id="0522d-132"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0522d-133">シリアル化</span><span class="sxs-lookup"><span data-stu-id="0522d-133">Serialization</span></span>|<span data-ttu-id="0522d-134">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-134">Optional attribute.</span></span> <span data-ttu-id="0522d-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0522d-136">Interop</span><span class="sxs-lookup"><span data-stu-id="0522d-136">Interop</span></span>|<span data-ttu-id="0522d-137">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-137">Optional attribute.</span></span> <span data-ttu-id="0522d-138">WinRT と COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0522d-139">Interop</span><span class="sxs-lookup"><span data-stu-id="0522d-139">Interop</span></span>|<span data-ttu-id="0522d-140">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-140">Optional attribute.</span></span> <span data-ttu-id="0522d-141">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0522d-142">Interop</span><span class="sxs-lookup"><span data-stu-id="0522d-142">Interop</span></span>|<span data-ttu-id="0522d-143">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0522d-143">Optional attribute.</span></span> <span data-ttu-id="0522d-144">値型をネイティブ コードにマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0522d-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0522d-145">Name 属性</span><span class="sxs-lookup"><span data-stu-id="0522d-145">Name attribute</span></span>  
  
|<span data-ttu-id="0522d-146">値</span><span class="sxs-lookup"><span data-stu-id="0522d-146">Value</span></span>|<span data-ttu-id="0522d-147">[説明]</span><span class="sxs-lookup"><span data-stu-id="0522d-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0522d-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="0522d-148">*parameter_name*</span></span>|<span data-ttu-id="0522d-149">ポリシーが適用されるメソッド パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="0522d-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="0522d-150">たとえば、メソッド シグネチャ `String.CompareTo(Object value)` の場合、`Name` 属性の値は "value" です。</span><span class="sxs-lookup"><span data-stu-id="0522d-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0522d-151">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="0522d-151">All other attributes</span></span>  
  
|<span data-ttu-id="0522d-152">値</span><span class="sxs-lookup"><span data-stu-id="0522d-152">Value</span></span>|<span data-ttu-id="0522d-153">[説明]</span><span class="sxs-lookup"><span data-stu-id="0522d-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0522d-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0522d-154">*policy_setting*</span></span>|<span data-ttu-id="0522d-155">このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="0522d-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="0522d-156">指定できる値は、`All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="0522d-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0522d-157">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0522d-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0522d-158">子要素</span><span class="sxs-lookup"><span data-stu-id="0522d-158">Child Elements</span></span>  
 <span data-ttu-id="0522d-159">なし。</span><span class="sxs-lookup"><span data-stu-id="0522d-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0522d-160">親要素</span><span class="sxs-lookup"><span data-stu-id="0522d-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0522d-161">要素</span><span class="sxs-lookup"><span data-stu-id="0522d-161">Element</span></span>|<span data-ttu-id="0522d-162">説明</span><span class="sxs-lookup"><span data-stu-id="0522d-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="0522d-163">コンストラクターまたはメソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="0522d-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0522d-164">解説</span><span class="sxs-lookup"><span data-stu-id="0522d-164">Remarks</span></span>  
 <span data-ttu-id="0522d-165">`<Parameter>`要素は要素の子であり、特定の [\<Method>](method-element-net-native.md) メソッドパラメーターにポリシーを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0522d-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="0522d-166">特定のメソッド パラメーターは、型ではなく名前で指定されます。</span><span class="sxs-lookup"><span data-stu-id="0522d-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="0522d-167">`Activate` や `Dynamic` などのポリシーの種類を表す属性が 1 つ以上必要です。</span><span class="sxs-lookup"><span data-stu-id="0522d-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0522d-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="0522d-168">See also</span></span>

- [<span data-ttu-id="0522d-169">\<Method>Element</span><span class="sxs-lookup"><span data-stu-id="0522d-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="0522d-170">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="0522d-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0522d-171">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="0522d-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="0522d-172">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="0522d-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
