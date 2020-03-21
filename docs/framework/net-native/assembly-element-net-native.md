---
title: <Assembly>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
ms.openlocfilehash: f3cf65b185b1db3289a0dbb785c2b91431951cc2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181080"
---
# <a name="assembly-element-net-native"></a><span data-ttu-id="df639-102">\<アセンブリ>要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="df639-102">\<Assembly> Element (.NET Native)</span></span>
<span data-ttu-id="df639-103">指定したアセンブリ内のすべての型にランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="df639-103">Applies runtime reflection policy to all the types in a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df639-104">構文</span><span class="sxs-lookup"><span data-stu-id="df639-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df639-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="df639-105">Attributes and Elements</span></span>  
 <span data-ttu-id="df639-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="df639-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df639-107">属性</span><span class="sxs-lookup"><span data-stu-id="df639-107">Attributes</span></span>  
  
|<span data-ttu-id="df639-108">属性</span><span class="sxs-lookup"><span data-stu-id="df639-108">Attribute</span></span>|<span data-ttu-id="df639-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="df639-109">Attribute type</span></span>|<span data-ttu-id="df639-110">説明</span><span class="sxs-lookup"><span data-stu-id="df639-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="df639-111">全般</span><span class="sxs-lookup"><span data-stu-id="df639-111">General</span></span>|<span data-ttu-id="df639-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-112">Required attribute.</span></span> <span data-ttu-id="df639-113">アセンブリの簡易名を指定します。</span><span class="sxs-lookup"><span data-stu-id="df639-113">Specifies the simple name of an assembly.</span></span>|  
|`Activate`|<span data-ttu-id="df639-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="df639-114">Reflection</span></span>|<span data-ttu-id="df639-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-115">Optional attribute.</span></span> <span data-ttu-id="df639-116">コンストラクターへの実行時アクセスを制御して、インスタンスのアクティブ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="df639-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="df639-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="df639-117">Reflection</span></span>|<span data-ttu-id="df639-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-118">Optional attribute.</span></span> <span data-ttu-id="df639-119">アセンブリ内の型に関する情報の照会または型の列挙を制御しますが、実行時の動的アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="df639-119">Controls querying for information about or enumerating the types in the assembly, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="df639-120">リフレクション</span><span class="sxs-lookup"><span data-stu-id="df639-120">Reflection</span></span>|<span data-ttu-id="df639-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-121">Optional attribute.</span></span> <span data-ttu-id="df639-122">コンストラクター、メソッド、フィールド、プロパティ、およびイベントを含むすべての型のメンバーへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="df639-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="df639-123">シリアル化</span><span class="sxs-lookup"><span data-stu-id="df639-123">Serialization</span></span>|<span data-ttu-id="df639-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-124">Optional attribute.</span></span> <span data-ttu-id="df639-125">コンストラクター、フィールド、およびプロパティへの実行時アクセスを制御し、Newtonsoft の JSON シリアライザーなどのライブラリによって型インスタンスをシリアル化および逆シリアル化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="df639-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="df639-126">シリアル化</span><span class="sxs-lookup"><span data-stu-id="df639-126">Serialization</span></span>|<span data-ttu-id="df639-127">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-127">Optional attribute.</span></span> <span data-ttu-id="df639-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> クラスを使用するシリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="df639-129">シリアル化</span><span class="sxs-lookup"><span data-stu-id="df639-129">Serialization</span></span>|<span data-ttu-id="df639-130">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-130">Optional attribute.</span></span> <span data-ttu-id="df639-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> クラスを使用する JSON シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="df639-132">シリアル化</span><span class="sxs-lookup"><span data-stu-id="df639-132">Serialization</span></span>|<span data-ttu-id="df639-133">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-133">Optional attribute.</span></span> <span data-ttu-id="df639-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> クラスを使用する XML シリアル化のポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="df639-135">Interop</span><span class="sxs-lookup"><span data-stu-id="df639-135">Interop</span></span>|<span data-ttu-id="df639-136">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-136">Optional attribute.</span></span> <span data-ttu-id="df639-137">Windows ランタイムと COM に参照型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="df639-138">Interop</span><span class="sxs-lookup"><span data-stu-id="df639-138">Interop</span></span>|<span data-ttu-id="df639-139">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-139">Optional attribute.</span></span> <span data-ttu-id="df639-140">ネイティブ コードへの関数ポインターとしてデリゲート型をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="df639-141">Interop</span><span class="sxs-lookup"><span data-stu-id="df639-141">Interop</span></span>|<span data-ttu-id="df639-142">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="df639-142">Optional attribute.</span></span> <span data-ttu-id="df639-143">ネイティブ コードに構造体をマーシャリングするためのポリシーを制御します。</span><span class="sxs-lookup"><span data-stu-id="df639-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="df639-144">Name 属性</span><span class="sxs-lookup"><span data-stu-id="df639-144">Name attribute</span></span>  
  
|<span data-ttu-id="df639-145">Value</span><span class="sxs-lookup"><span data-stu-id="df639-145">Value</span></span>|<span data-ttu-id="df639-146">説明</span><span class="sxs-lookup"><span data-stu-id="df639-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df639-147">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="df639-147">*assembly_name*</span></span>|<span data-ttu-id="df639-148">ファイル拡張子のないアセンブリの簡易名です。</span><span class="sxs-lookup"><span data-stu-id="df639-148">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="df639-149">この属性は、<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="df639-149">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="df639-150">たとえば、Extensions.dll というアセンブリの名前は "Extensions" です。</span><span class="sxs-lookup"><span data-stu-id="df639-150">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span><br /><br /> <span data-ttu-id="df639-151">リテラル文字列 `*Application*` を指定して、アプリ パッケージ内のすべてのアセンブリに、読み込みの有無に関係なくポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="df639-151">You can also specify the literal string `*Application*` to apply policy to all assemblies in your app package, whether those assemblies are loaded or not.</span></span> <span data-ttu-id="df639-152">`*Application*` は、.NET Framework アセンブリにポリシーを適用しません。</span><span class="sxs-lookup"><span data-stu-id="df639-152">`*Application*` never applies policy to .NET Framework assemblies.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="df639-153">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="df639-153">All other attributes</span></span>  
  
|<span data-ttu-id="df639-154">Value</span><span class="sxs-lookup"><span data-stu-id="df639-154">Value</span></span>|<span data-ttu-id="df639-155">説明</span><span class="sxs-lookup"><span data-stu-id="df639-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df639-156">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="df639-156">*policy_setting*</span></span>|<span data-ttu-id="df639-157">アセンブリ内のすべての型について、このポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="df639-157">The setting to apply to this policy type for all types in the assembly.</span></span> <span data-ttu-id="df639-158">指定できる値は、`All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal`、および `Required All` です。</span><span class="sxs-lookup"><span data-stu-id="df639-158">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="df639-159">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df639-159">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df639-160">子要素</span><span class="sxs-lookup"><span data-stu-id="df639-160">Child Elements</span></span>  
  
|<span data-ttu-id="df639-161">要素</span><span class="sxs-lookup"><span data-stu-id="df639-161">Element</span></span>|<span data-ttu-id="df639-162">説明</span><span class="sxs-lookup"><span data-stu-id="df639-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df639-163">\<名前空間></span><span class="sxs-lookup"><span data-stu-id="df639-163">\<Namespace></span></span>](namespace-element-net-native.md)|<span data-ttu-id="df639-164">子名前空間内のすべての型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="df639-164">Applies reflection policy to all types in a child namespace.</span></span>|  
|[<span data-ttu-id="df639-165">\<タイプ></span><span class="sxs-lookup"><span data-stu-id="df639-165">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="df639-166">型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="df639-166">Applies reflection policy to a type.</span></span>|  
|[<span data-ttu-id="df639-167">\<入力インスタンス化></span><span class="sxs-lookup"><span data-stu-id="df639-167">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="df639-168">構築されたジェネリック型にリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="df639-168">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df639-169">親要素</span><span class="sxs-lookup"><span data-stu-id="df639-169">Parent Elements</span></span>  
  
|<span data-ttu-id="df639-170">要素</span><span class="sxs-lookup"><span data-stu-id="df639-170">Element</span></span>|<span data-ttu-id="df639-171">説明</span><span class="sxs-lookup"><span data-stu-id="df639-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df639-172">\<アプリケーション></span><span class="sxs-lookup"><span data-stu-id="df639-172">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="df639-173">実行時にリフレクションで使用可能なメタデータを持つ、アプリケーション全体の型と型のメンバーのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="df639-173">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="df639-174">[\<アプリケーション>](application-element-net-native.md)要素には、0 個、1`<Assembly>`つ、または複数の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="df639-174">The [\<Application>](application-element-net-native.md) element can have zero, one, or more `<Assembly>` elements.</span></span>|  
|[<span data-ttu-id="df639-175">\<図書館></span><span class="sxs-lookup"><span data-stu-id="df639-175">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="df639-176">実行時にリフレクションに使用可能なメタデータを持つ型と型のメンバーを含むアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="df639-176">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="df639-177">[\<ライブラリ>](library-element-net-native.md)要素には、0 または`<Assembly>`1 つの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="df639-177">The [\<Library>](library-element-net-native.md) element can have zero or one `<Assembly>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df639-178">解説</span><span class="sxs-lookup"><span data-stu-id="df639-178">Remarks</span></span>  
 <span data-ttu-id="df639-179">`<Assembly>` 要素は、アセンブリ内のすべての型の実行時ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="df639-179">The `<Assembly>` element defines runtime policy for all the types in an assembly.</span></span> <span data-ttu-id="df639-180">[\<ライブラリ](library-element-net-native.md)を指定するライブラリ>要素とは異なりますが、ランタイム リフレクション ポリシーを定義するためにその子要素に依存します。</span><span class="sxs-lookup"><span data-stu-id="df639-180">It differs from the [\<Library>](library-element-net-native.md) element, which specifies a library but depends on its child elements to define runtime reflection policy.</span></span> <span data-ttu-id="df639-181">`<Assembly>` 要素は、子要素でオーバーライドされない限り、アセンブリ内のすべての型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="df639-181">The `<Assembly>` element applies to all the types in an assembly unless they are overridden by a child element.</span></span>  
  
 <span data-ttu-id="df639-182">次の例では、`Name` 属性に "\*Application\*" という値を割り当てて、アプリ パッケージ内のアセンブリのすべての型に実行時ポリシーを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df639-182">The following example shows how you can apply runtime policy to all the types in assemblies within your app package by assigning the `Name` attribute a value of "\*Application\*".</span></span> <span data-ttu-id="df639-183">要素`<Assembly>`は[\<、アプリケーション>](application-element-net-native.md)要素の子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df639-183">The `<Assembly>` element must be a child of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>  
```  
  
 <span data-ttu-id="df639-184">`Activate` 属性、`Browse` 属性、`Dynamic`、および `Serialize` 属性はすべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="df639-184">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="df639-185">ただし、`<Assembly>` 要素にはこれらの属性のいずれか 1 つ以上を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="df639-185">However, the `<Assembly>` element must contain at least one of these attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df639-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="df639-186">See also</span></span>

- [<span data-ttu-id="df639-187">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="df639-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="df639-188">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレン</span><span class="sxs-lookup"><span data-stu-id="df639-188">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="df639-189">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="df639-189">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
