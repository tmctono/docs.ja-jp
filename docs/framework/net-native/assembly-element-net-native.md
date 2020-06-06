---
title: <Assembly>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
ms.openlocfilehash: f3cf65b185b1db3289a0dbb785c2b91431951cc2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181080"
---
# <a name="assembly-element-net-native"></a><span data-ttu-id="99c0c-102">\<Assembly>要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="99c0c-102">\<Assembly> Element (.NET Native)</span></span>
<span data-ttu-id="99c0c-103">指定したアセンブリ内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-103">Applies runtime reflection policy to all the types in a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="99c0c-104">Syntax</span></span>  
  
```xml  
<Assembly Name="assembly_name"
          Activate="policy_setting"  
          Browse="policy_setting"  
          Dynamic="policy_setting"  
          Serialize="policy_setting"  
          DataContractSerializer="policy_setting"  
          DataContractJsonSerializer="policy_setting"  
          XmlSerializer="policy_setting"  
          MarshalObject="policy_setting"  
          MarshalDelegate="policy_setting"  
          MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c0c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="99c0c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c0c-107">属性</span><span class="sxs-lookup"><span data-stu-id="99c0c-107">Attributes</span></span>  
  
|<span data-ttu-id="99c0c-108">属性</span><span class="sxs-lookup"><span data-stu-id="99c0c-108">Attribute</span></span>|<span data-ttu-id="99c0c-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="99c0c-109">Attribute type</span></span>|<span data-ttu-id="99c0c-110">Description</span><span class="sxs-lookup"><span data-stu-id="99c0c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="99c0c-111">全般</span><span class="sxs-lookup"><span data-stu-id="99c0c-111">General</span></span>|<span data-ttu-id="99c0c-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-112">Required attribute.</span></span> <span data-ttu-id="99c0c-113">アセンブリの簡易名を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-113">Specifies the simple name of an assembly.</span></span>|  
|`Activate`|<span data-ttu-id="99c0c-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="99c0c-114">Reflection</span></span>|<span data-ttu-id="99c0c-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-115">Optional attribute.</span></span> <span data-ttu-id="99c0c-116">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="99c0c-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="99c0c-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="99c0c-117">Reflection</span></span>|<span data-ttu-id="99c0c-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-118">Optional attribute.</span></span> <span data-ttu-id="99c0c-119">アセンブリ内の型に関する情報の照会または型の列挙を制御しますが、実行時の動的アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="99c0c-119">Controls querying for information about or enumerating the types in the assembly, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="99c0c-120">リフレクション</span><span class="sxs-lookup"><span data-stu-id="99c0c-120">Reflection</span></span>|<span data-ttu-id="99c0c-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-121">Optional attribute.</span></span> <span data-ttu-id="99c0c-122">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="99c0c-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="99c0c-123">シリアル化</span><span class="sxs-lookup"><span data-stu-id="99c0c-123">Serialization</span></span>|<span data-ttu-id="99c0c-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-124">Optional attribute.</span></span> <span data-ttu-id="99c0c-125">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="99c0c-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="99c0c-126">シリアル化</span><span class="sxs-lookup"><span data-stu-id="99c0c-126">Serialization</span></span>|<span data-ttu-id="99c0c-127">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-127">Optional attribute.</span></span> <span data-ttu-id="99c0c-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="99c0c-129">シリアル化</span><span class="sxs-lookup"><span data-stu-id="99c0c-129">Serialization</span></span>|<span data-ttu-id="99c0c-130">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-130">Optional attribute.</span></span> <span data-ttu-id="99c0c-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="99c0c-132">シリアル化</span><span class="sxs-lookup"><span data-stu-id="99c0c-132">Serialization</span></span>|<span data-ttu-id="99c0c-133">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-133">Optional attribute.</span></span> <span data-ttu-id="99c0c-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="99c0c-135">Interop</span><span class="sxs-lookup"><span data-stu-id="99c0c-135">Interop</span></span>|<span data-ttu-id="99c0c-136">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-136">Optional attribute.</span></span> <span data-ttu-id="99c0c-137">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="99c0c-138">Interop</span><span class="sxs-lookup"><span data-stu-id="99c0c-138">Interop</span></span>|<span data-ttu-id="99c0c-139">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-139">Optional attribute.</span></span> <span data-ttu-id="99c0c-140">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="99c0c-141">Interop</span><span class="sxs-lookup"><span data-stu-id="99c0c-141">Interop</span></span>|<span data-ttu-id="99c0c-142">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-142">Optional attribute.</span></span> <span data-ttu-id="99c0c-143">ネイティブ コードに構造体をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="99c0c-144">Name 属性</span><span class="sxs-lookup"><span data-stu-id="99c0c-144">Name attribute</span></span>  
  
|<span data-ttu-id="99c0c-145">値</span><span class="sxs-lookup"><span data-stu-id="99c0c-145">Value</span></span>|<span data-ttu-id="99c0c-146">[説明]</span><span class="sxs-lookup"><span data-stu-id="99c0c-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99c0c-147">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="99c0c-147">*assembly_name*</span></span>|<span data-ttu-id="99c0c-148">ファイル拡張子のないアセンブリの簡易名です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-148">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="99c0c-149">この属性は、<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-149">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="99c0c-150">たとえば、Extensions.dll というアセンブリの名前は "Extensions" です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-150">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span><br /><br /> <span data-ttu-id="99c0c-151">リテラル文字列 `*Application*` を指定して、アプリ パッケージ内のすべてのアセンブリに、読み込みの有無に関係なくポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="99c0c-151">You can also specify the literal string `*Application*` to apply policy to all assemblies in your app package, whether those assemblies are loaded or not.</span></span> <span data-ttu-id="99c0c-152">`*Application*` は、.NET Framework アセンブリにポリシーを適用しません。</span><span class="sxs-lookup"><span data-stu-id="99c0c-152">`*Application*` never applies policy to .NET Framework assemblies.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="99c0c-153">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="99c0c-153">All other attributes</span></span>  
  
|<span data-ttu-id="99c0c-154">値</span><span class="sxs-lookup"><span data-stu-id="99c0c-154">Value</span></span>|<span data-ttu-id="99c0c-155">[説明]</span><span class="sxs-lookup"><span data-stu-id="99c0c-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99c0c-156">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="99c0c-156">*policy_setting*</span></span>|<span data-ttu-id="99c0c-157">アセンブリ内のすべての型について、このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-157">The setting to apply to this policy type for all types in the assembly.</span></span> <span data-ttu-id="99c0c-158">指定できる値は、`All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-158">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="99c0c-159">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c0c-159">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c0c-160">子要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-160">Child Elements</span></span>  
  
|<span data-ttu-id="99c0c-161">要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-161">Element</span></span>|<span data-ttu-id="99c0c-162">説明</span><span class="sxs-lookup"><span data-stu-id="99c0c-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="99c0c-163">子名前空間内のすべての型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-163">Applies reflection policy to all types in a child namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="99c0c-164">型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-164">Applies reflection policy to a type.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="99c0c-165">構築されたジェネリック型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-165">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99c0c-166">親要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-166">Parent Elements</span></span>  
  
|<span data-ttu-id="99c0c-167">要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-167">Element</span></span>|<span data-ttu-id="99c0c-168">説明</span><span class="sxs-lookup"><span data-stu-id="99c0c-168">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="99c0c-169">実行時にリフレクションで使用可能なメタデータを持つ、アプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-169">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="99c0c-170">要素には、 [\<Application>](application-element-net-native.md) 0 個以上の要素を含めることができ `<Assembly>` ます。</span><span class="sxs-lookup"><span data-stu-id="99c0c-170">The [\<Application>](application-element-net-native.md) element can have zero, one, or more `<Assembly>` elements.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="99c0c-171">実行時にリフレクションに使用可能なメタデータを持つ型と型のメンバーを含むアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-171">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="99c0c-172">要素には、 [\<Library>](library-element-net-native.md) 0 個または1個の要素を含めることができ `<Assembly>` ます。</span><span class="sxs-lookup"><span data-stu-id="99c0c-172">The [\<Library>](library-element-net-native.md) element can have zero or one `<Assembly>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c0c-173">解説</span><span class="sxs-lookup"><span data-stu-id="99c0c-173">Remarks</span></span>  
 <span data-ttu-id="99c0c-174">`<Assembly>` 要素は、アセンブリ内のすべての型の実行時ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-174">The `<Assembly>` element defines runtime policy for all the types in an assembly.</span></span> <span data-ttu-id="99c0c-175">これは、 [\<Library>](library-element-net-native.md) ライブラリを指定する要素とは異なりますが、ランタイムリフレクションポリシーを定義するためにその子要素に依存します。</span><span class="sxs-lookup"><span data-stu-id="99c0c-175">It differs from the [\<Library>](library-element-net-native.md) element, which specifies a library but depends on its child elements to define runtime reflection policy.</span></span> <span data-ttu-id="99c0c-176">`<Assembly>` 要素は、子要素でオーバーライドされない限り、アセンブリ内のすべての型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="99c0c-176">The `<Assembly>` element applies to all the types in an assembly unless they are overridden by a child element.</span></span>  
  
 <span data-ttu-id="99c0c-177">次の例では、`Name` 属性に "\*Application\*" という値を割り当てて、アプリ パッケージ内のアセンブリのすべての型に実行時ポリシーを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="99c0c-177">The following example shows how you can apply runtime policy to all the types in assemblies within your app package by assigning the `Name` attribute a value of "\*Application\*".</span></span> <span data-ttu-id="99c0c-178">`<Assembly>`要素は要素の子である必要があり [\<Application>](application-element-net-native.md) ます。</span><span class="sxs-lookup"><span data-stu-id="99c0c-178">The `<Assembly>` element must be a child of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>  
```  
  
 <span data-ttu-id="99c0c-179">`Activate` 属性、`Browse` 属性、`Dynamic`、および `Serialize` 属性はすべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="99c0c-179">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="99c0c-180">ただし、`<Assembly>` 要素にはこれらの属性のいずれか 1 つ以上を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="99c0c-180">However, the `<Assembly>` element must contain at least one of these attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c0c-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="99c0c-181">See also</span></span>

- [<span data-ttu-id="99c0c-182">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="99c0c-182">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="99c0c-183">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="99c0c-183">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="99c0c-184">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="99c0c-184">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
