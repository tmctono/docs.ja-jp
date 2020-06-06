---
title: <Namespace>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: 06d88a7b0f95c7c1dbe98818b847c92e08a57a19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180963"
---
# <a name="namespace-element-net-native"></a><span data-ttu-id="8cef7-102">\<Namespace>要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="8cef7-102">\<Namespace> Element (.NET Native)</span></span>
<span data-ttu-id="8cef7-103">指定した名前空間内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-103">Applies runtime reflection policy to all the types in a specified namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cef7-104">構文</span><span class="sxs-lookup"><span data-stu-id="8cef7-104">Syntax</span></span>  
  
```xml  
<Namespace Name="namespace_name"
           Activate="policy_type"
           Browse="policy_type"  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cef7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8cef7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cef7-107">属性</span><span class="sxs-lookup"><span data-stu-id="8cef7-107">Attributes</span></span>  
  
|<span data-ttu-id="8cef7-108">属性</span><span class="sxs-lookup"><span data-stu-id="8cef7-108">Attribute</span></span>|<span data-ttu-id="8cef7-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="8cef7-109">Attribute type</span></span>|<span data-ttu-id="8cef7-110">Description</span><span class="sxs-lookup"><span data-stu-id="8cef7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8cef7-111">全般</span><span class="sxs-lookup"><span data-stu-id="8cef7-111">General</span></span>|<span data-ttu-id="8cef7-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-112">Required attribute.</span></span> <span data-ttu-id="8cef7-113">名前空間の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-113">Specifies the name of the namespace.</span></span>|  
|`Activate`|<span data-ttu-id="8cef7-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="8cef7-114">Reflection</span></span>|<span data-ttu-id="8cef7-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-115">Optional attribute.</span></span> <span data-ttu-id="8cef7-116">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cef7-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="8cef7-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="8cef7-117">Reflection</span></span>|<span data-ttu-id="8cef7-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-118">Optional attribute.</span></span> <span data-ttu-id="8cef7-119">プログラム要素に関する情報の照会を制御しますが、実行時アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="8cef7-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="8cef7-120">リフレクション</span><span class="sxs-lookup"><span data-stu-id="8cef7-120">Reflection</span></span>|<span data-ttu-id="8cef7-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-121">Optional attribute.</span></span> <span data-ttu-id="8cef7-122">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cef7-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="8cef7-123">シリアル化</span><span class="sxs-lookup"><span data-stu-id="8cef7-123">Serialization</span></span>|<span data-ttu-id="8cef7-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-124">Optional attribute.</span></span> <span data-ttu-id="8cef7-125">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8cef7-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="8cef7-126">シリアル化</span><span class="sxs-lookup"><span data-stu-id="8cef7-126">Serialization</span></span>|<span data-ttu-id="8cef7-127">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-127">Optional attribute.</span></span> <span data-ttu-id="8cef7-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="8cef7-129">シリアル化</span><span class="sxs-lookup"><span data-stu-id="8cef7-129">Serialization</span></span>|<span data-ttu-id="8cef7-130">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-130">Optional attribute.</span></span> <span data-ttu-id="8cef7-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="8cef7-132">シリアル化</span><span class="sxs-lookup"><span data-stu-id="8cef7-132">Serialization</span></span>|<span data-ttu-id="8cef7-133">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-133">Optional attribute.</span></span> <span data-ttu-id="8cef7-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="8cef7-135">Interop</span><span class="sxs-lookup"><span data-stu-id="8cef7-135">Interop</span></span>|<span data-ttu-id="8cef7-136">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-136">Optional attribute.</span></span> <span data-ttu-id="8cef7-137">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="8cef7-138">Interop</span><span class="sxs-lookup"><span data-stu-id="8cef7-138">Interop</span></span>|<span data-ttu-id="8cef7-139">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-139">Optional attribute.</span></span> <span data-ttu-id="8cef7-140">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="8cef7-141">Interop</span><span class="sxs-lookup"><span data-stu-id="8cef7-141">Interop</span></span>|<span data-ttu-id="8cef7-142">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-142">Optional attribute.</span></span> <span data-ttu-id="8cef7-143">ネイティブ コードに構造体をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8cef7-144">Name 属性</span><span class="sxs-lookup"><span data-stu-id="8cef7-144">Name attribute</span></span>  
  
|<span data-ttu-id="8cef7-145">値</span><span class="sxs-lookup"><span data-stu-id="8cef7-145">Value</span></span>|<span data-ttu-id="8cef7-146">[説明]</span><span class="sxs-lookup"><span data-stu-id="8cef7-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8cef7-147">*namespace_name*</span><span class="sxs-lookup"><span data-stu-id="8cef7-147">*namespace_name*</span></span>|<span data-ttu-id="8cef7-148">名前空間の名前。</span><span class="sxs-lookup"><span data-stu-id="8cef7-148">The namespace name.</span></span> <span data-ttu-id="8cef7-149">\<Namespace>要素が、、または要素の子である場合 [\<Application>](application-element-net-native.md) [\<Library>](library-element-net-native.md) [\<Assembly>](assembly-element-net-native.md) 、 *namespace_name*は完全修飾名前空間名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cef7-149">If the \<Namespace> element is a child of an [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md), or [\<Assembly>](assembly-element-net-native.md) element, *namespace_name* must be a fully qualified namespace name.</span></span> <span data-ttu-id="8cef7-150">\<Namespace>要素が別の要素の子である場合 \<Namespace> 、 *namespace_name*は相対名前空間名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cef7-150">If the \<Namespace> element is a child of another \<Namespace> element, *namespace_name* must be a relative namespace name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8cef7-151">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="8cef7-151">All other attributes</span></span>  
  
|<span data-ttu-id="8cef7-152">値</span><span class="sxs-lookup"><span data-stu-id="8cef7-152">Value</span></span>|<span data-ttu-id="8cef7-153">[説明]</span><span class="sxs-lookup"><span data-stu-id="8cef7-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8cef7-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8cef7-154">*policy_setting*</span></span>|<span data-ttu-id="8cef7-155">名前空間内のすべての型について、このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-155">The setting to apply to this policy type for all types in the namespace.</span></span> <span data-ttu-id="8cef7-156">指定できる値は、`All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="8cef7-157">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cef7-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cef7-158">子要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-158">Child Elements</span></span>  
  
|<span data-ttu-id="8cef7-159">要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-159">Element</span></span>|<span data-ttu-id="8cef7-160">説明</span><span class="sxs-lookup"><span data-stu-id="8cef7-160">Description</span></span>|  
|-------------|-----------------|  
|`<Namespace>`|<span data-ttu-id="8cef7-161">親名前空間内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-161">Applies runtime reflection policy to all types in a parent namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="8cef7-162">型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-162">Applies reflection policy to a type.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="8cef7-163">構築されたジェネリック型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-163">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8cef7-164">親要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-164">Parent Elements</span></span>  
  
|<span data-ttu-id="8cef7-165">要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-165">Element</span></span>|<span data-ttu-id="8cef7-166">説明</span><span class="sxs-lookup"><span data-stu-id="8cef7-166">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="8cef7-167">実行時にリフレクションで使用可能なメタデータを持つ、アプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-167">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="8cef7-168">要素には、 [\<Application>](application-element-net-native.md) 0 個以上の要素を含めることができ [\<Assembly>](assembly-element-net-native.md) ます。</span><span class="sxs-lookup"><span data-stu-id="8cef7-168">The [\<Application>](application-element-net-native.md) element can have zero, one, or more [\<Assembly>](assembly-element-net-native.md) elements.</span></span>|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="8cef7-169">指定したアセンブリ内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-169">Applies runtime reflection policy to all the types in a specified assembly.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="8cef7-170">実行時にリフレクションに使用可能なメタデータを持つ型と型のメンバーを含むアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-170">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="8cef7-171">要素には、 [\<Library>](library-element-net-native.md) 0 個または1個の要素を含めることができ [\<Assembly>](assembly-element-net-native.md) ます。</span><span class="sxs-lookup"><span data-stu-id="8cef7-171">The [\<Library>](library-element-net-native.md) element can have zero or one [\<Assembly>](assembly-element-net-native.md) element.</span></span>|  
|`<Namespace>`|<span data-ttu-id="8cef7-172">親名前空間内のすべての型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-172">Applies reflection policy to all types in a parent namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cef7-173">解説</span><span class="sxs-lookup"><span data-stu-id="8cef7-173">Remarks</span></span>  
 <span data-ttu-id="8cef7-174">`Activate` 属性、`Browse` 属性、`Dynamic`、および `Serialize` 属性はすべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8cef7-174">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="8cef7-175">いずれも存在しない場合、`<Namespace>` 要素は子要素のコンテナーとしてのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-175">If none are present, the `<Namespace>` element serves only as a container for child elements.</span></span> <span data-ttu-id="8cef7-176">存在する場合は、`<Namespace>` 要素は、指定された名前空間内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8cef7-176">If they are present, the `<Namespace>` element applies runtime reflection policy to all the types in the specified namespace.</span></span>  
  
 <span data-ttu-id="8cef7-177">要素の子である場合 [\<Assembly>](assembly-element-net-native.md) 、要素は、 `<Namespace>` 要素によって定義されたランタイムリフレクションポリシーをオーバーライドし [\<Assembly>](assembly-element-net-native.md) ます。</span><span class="sxs-lookup"><span data-stu-id="8cef7-177">When it is a child of the [\<Assembly>](assembly-element-net-native.md) element, the `<Namespace>` element overrides the runtime reflection policy defined by the  [\<Assembly>](assembly-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cef7-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cef7-178">See also</span></span>

- [<span data-ttu-id="8cef7-179">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="8cef7-179">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="8cef7-180">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="8cef7-180">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="8cef7-181">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="8cef7-181">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
