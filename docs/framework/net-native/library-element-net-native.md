---
title: <Library> 要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce001ed25d7704301d7f809887a445e3492e93fc
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422535"
---
# <a name="library-element-net-native"></a><span data-ttu-id="cf002-102">\<ライブラリ > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="cf002-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="cf002-103">実行時にリフレクションに使用可能なメタデータを持つ型と型のメンバーを含むアセンブリを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf002-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="cf002-104">\<Directives> 要素</span><span class="sxs-lookup"><span data-stu-id="cf002-104">\<Directives> Element</span></span>  
<span data-ttu-id="cf002-105">\<Library> 要素</span><span class="sxs-lookup"><span data-stu-id="cf002-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf002-106">構文</span><span class="sxs-lookup"><span data-stu-id="cf002-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf002-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cf002-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cf002-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf002-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf002-109">属性</span><span class="sxs-lookup"><span data-stu-id="cf002-109">Attributes</span></span>  
  
|<span data-ttu-id="cf002-110">属性</span><span class="sxs-lookup"><span data-stu-id="cf002-110">Attribute</span></span>|<span data-ttu-id="cf002-111">説明</span><span class="sxs-lookup"><span data-stu-id="cf002-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="cf002-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cf002-112">Required attribute.</span></span> <span data-ttu-id="cf002-113">アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf002-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="cf002-114">この `<Library>` 要素の子要素によって、このアセンブリ内にある型と型のメンバーのランタイム リフレクション ポリシーが定義されます。</span><span class="sxs-lookup"><span data-stu-id="cf002-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="cf002-115">Name 属性</span><span class="sxs-lookup"><span data-stu-id="cf002-115">Name attribute</span></span>  
  
|<span data-ttu-id="cf002-116">値</span><span class="sxs-lookup"><span data-stu-id="cf002-116">Value</span></span>|<span data-ttu-id="cf002-117">説明</span><span class="sxs-lookup"><span data-stu-id="cf002-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf002-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="cf002-118">*assembly_name*</span></span>|<span data-ttu-id="cf002-119">ファイル拡張子のないアセンブリの簡易名です。</span><span class="sxs-lookup"><span data-stu-id="cf002-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="cf002-120">この属性は、<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="cf002-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="cf002-121">たとえば、Extensions.dll というアセンブリの名前は "Extensions" です。</span><span class="sxs-lookup"><span data-stu-id="cf002-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="cf002-122">アセンブリのメタデータの条件付きインクルードをサポートする特殊な形式の *assembly_name* については、「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf002-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf002-123">子要素</span><span class="sxs-lookup"><span data-stu-id="cf002-123">Child Elements</span></span>  
  
|<span data-ttu-id="cf002-124">要素</span><span class="sxs-lookup"><span data-stu-id="cf002-124">Element</span></span>|<span data-ttu-id="cf002-125">説明</span><span class="sxs-lookup"><span data-stu-id="cf002-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf002-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="cf002-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="cf002-127">特定のアセンブリ内のすべての型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cf002-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="cf002-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="cf002-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="cf002-129">特定の名前空間内のすべての型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cf002-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="cf002-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="cf002-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="cf002-131">クラスや構造体などの特定の型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cf002-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="cf002-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="cf002-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="cf002-133">構築されたジェネリック型にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cf002-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="cf002-134">たとえば、[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 要素を使用して `List<String>` 型のポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf002-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf002-135">親要素</span><span class="sxs-lookup"><span data-stu-id="cf002-135">Parent Elements</span></span>  
  
|<span data-ttu-id="cf002-136">要素</span><span class="sxs-lookup"><span data-stu-id="cf002-136">Element</span></span>|<span data-ttu-id="cf002-137">説明</span><span class="sxs-lookup"><span data-stu-id="cf002-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf002-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="cf002-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="cf002-139">ランタイム ディレクティブ ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cf002-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf002-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf002-140">Remarks</span></span>  
 <span data-ttu-id="cf002-141">[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 要素には、0 個以上の `<Library>` 要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cf002-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="cf002-142">`<Library>` 要素は、実行時に必要なメタデータを持つプログラム要素を定義するためのコンテナーとして機能します。この要素はポリシーを表しません。</span><span class="sxs-lookup"><span data-stu-id="cf002-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="cf002-143">コンパイル時に、コンパイラ ツールは `<Library>` 要素により指定されたライブラリでのみ、その子要素により示されるプログラム要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="cf002-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="cf002-144">一方、[\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 要素の子要素により示されるプログラム要素を検索する場合、コンパイラ ツールは .NET Framework コア ライブラリを含むすべてのライブラリを検索します。</span><span class="sxs-lookup"><span data-stu-id="cf002-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="cf002-145">`<Library>` ディレクティブは、条件付きで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf002-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="cf002-146">場合の名前、`<Library>`要素が起動し、末尾がアスタリスク (\*)、`<Library>`ディレクティブでは、アスタリスクの間に指定したアセンブリがアプリによって参照されている場合にのみ効果があります。</span><span class="sxs-lookup"><span data-stu-id="cf002-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="cf002-147">たとえば、次のランタイム ディレクティブは、Utilities.dll アセンブリがアプリによって参照されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf002-147">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf002-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf002-148">See also</span></span>

- [<span data-ttu-id="cf002-149">\<Application > 要素</span><span class="sxs-lookup"><span data-stu-id="cf002-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)
- [<span data-ttu-id="cf002-150">\<ディレクティブ > 要素</span><span class="sxs-lookup"><span data-stu-id="cf002-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)
- [<span data-ttu-id="cf002-151">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="cf002-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="cf002-152">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="cf002-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
