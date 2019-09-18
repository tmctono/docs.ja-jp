---
title: <Property>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54daf15c593327bf3255f40f6eb6931ffc8bd3c6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049312"
---
# <a name="property-element-net-native"></a><span data-ttu-id="607a2-102">\<プロパティ > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="607a2-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="607a2-103">プロパティにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="607a2-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="607a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="607a2-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="607a2-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="607a2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="607a2-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="607a2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="607a2-107">属性</span><span class="sxs-lookup"><span data-stu-id="607a2-107">Attributes</span></span>  
  
|<span data-ttu-id="607a2-108">属性</span><span class="sxs-lookup"><span data-stu-id="607a2-108">Attribute</span></span>|<span data-ttu-id="607a2-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="607a2-109">Attribute type</span></span>|<span data-ttu-id="607a2-110">説明</span><span class="sxs-lookup"><span data-stu-id="607a2-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="607a2-111">全般</span><span class="sxs-lookup"><span data-stu-id="607a2-111">General</span></span>|<span data-ttu-id="607a2-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="607a2-112">Required attribute.</span></span> <span data-ttu-id="607a2-113">プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="607a2-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="607a2-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="607a2-114">Reflection</span></span>|<span data-ttu-id="607a2-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="607a2-115">Optional attribute.</span></span> <span data-ttu-id="607a2-116">プロパティに関する情報の照会やプロパティの列挙を制御しますが、実行時の動的アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="607a2-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="607a2-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="607a2-117">Reflection</span></span>|<span data-ttu-id="607a2-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="607a2-118">Optional attribute.</span></span> <span data-ttu-id="607a2-119">プロパティへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="607a2-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="607a2-120">このポリシーによって、実行時にプロパティを動的に設定または取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="607a2-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="607a2-121">シリアル化</span><span class="sxs-lookup"><span data-stu-id="607a2-121">Serialization</span></span>|<span data-ttu-id="607a2-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="607a2-122">Optional attribute.</span></span> <span data-ttu-id="607a2-123">プロパティへの実行時アクセスを制御して、型インスタンスを Newtonsoft の JSON シリアライザーなどのライブラリによってシリアル化できるようにしたり、データ バインディングで使用できるようにしたりします。</span><span class="sxs-lookup"><span data-stu-id="607a2-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="607a2-124">Name 属性</span><span class="sxs-lookup"><span data-stu-id="607a2-124">Name attribute</span></span>  
  
|<span data-ttu-id="607a2-125">値</span><span class="sxs-lookup"><span data-stu-id="607a2-125">Value</span></span>|<span data-ttu-id="607a2-126">説明</span><span class="sxs-lookup"><span data-stu-id="607a2-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="607a2-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="607a2-127">*method_name*</span></span>|<span data-ttu-id="607a2-128">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="607a2-128">The property name.</span></span> <span data-ttu-id="607a2-129">プロパティの型は、親の [\<Type>](type-element-net-native.md) または [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素により定義されます。</span><span class="sxs-lookup"><span data-stu-id="607a2-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="607a2-130">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="607a2-130">All other attributes</span></span>  
  
|<span data-ttu-id="607a2-131">値</span><span class="sxs-lookup"><span data-stu-id="607a2-131">Value</span></span>|<span data-ttu-id="607a2-132">説明</span><span class="sxs-lookup"><span data-stu-id="607a2-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="607a2-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="607a2-133">*policy_setting*</span></span>|<span data-ttu-id="607a2-134">プロパティのこのポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="607a2-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="607a2-135">指定できる値は、`Auto`、`Excluded`、`Included`、および `Required` です。</span><span class="sxs-lookup"><span data-stu-id="607a2-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="607a2-136">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a2-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="607a2-137">子要素</span><span class="sxs-lookup"><span data-stu-id="607a2-137">Child Elements</span></span>  
 <span data-ttu-id="607a2-138">なし。</span><span class="sxs-lookup"><span data-stu-id="607a2-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="607a2-139">親要素</span><span class="sxs-lookup"><span data-stu-id="607a2-139">Parent Elements</span></span>  
  
|<span data-ttu-id="607a2-140">要素</span><span class="sxs-lookup"><span data-stu-id="607a2-140">Element</span></span>|<span data-ttu-id="607a2-141">説明</span><span class="sxs-lookup"><span data-stu-id="607a2-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="607a2-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="607a2-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="607a2-143">型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="607a2-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="607a2-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="607a2-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="607a2-145">構築されたジェネリック型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="607a2-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="607a2-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="607a2-146">Remarks</span></span>  
 <span data-ttu-id="607a2-147">プロパティのポリシーが明示的に定義されていない場合は、親要素の実行時ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="607a2-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="607a2-148">例</span><span class="sxs-lookup"><span data-stu-id="607a2-148">Example</span></span>  
 <span data-ttu-id="607a2-149">次の例では、リフレクションを使用して、`Book` オブジェクトをインスタンス化し、そのプロパティ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="607a2-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="607a2-150">プロジェクトの既定の default.rd.xml ファイルは、次のように示されます。</span><span class="sxs-lookup"><span data-stu-id="607a2-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="607a2-151">このファイルは、`All` クラスの `Activate` ポリシーに `Book` 値を適用します。これにより、リフレクションを介してクラス コンストラクターにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="607a2-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="607a2-152">`Browse` クラスの `Book` ポリシーは、その親名前空間から継承されます。</span><span class="sxs-lookup"><span data-stu-id="607a2-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="607a2-153">これは `Required Public` に設定され、メタデータが実行時に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="607a2-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="607a2-154">この例のソース コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="607a2-154">The following is the source code for the example.</span></span> <span data-ttu-id="607a2-155">変数`outputBlock`は、コントロール<xref:Windows.UI.Xaml.Controls.TextBlock>を表します。</span><span class="sxs-lookup"><span data-stu-id="607a2-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="607a2-156">ただし、この例をコンパイルして実行すると、[MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="607a2-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="607a2-157">`Book` 型のメタデータは使用可能になりましたが、プロパティの getter の実装は動的に使用可能になりませんでした。</span><span class="sxs-lookup"><span data-stu-id="607a2-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="607a2-158">このエラーは、次の 2 つの方法のいずれかを使用して修正できます。</span><span class="sxs-lookup"><span data-stu-id="607a2-158">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="607a2-159">[\<Type](type-element-net-native.md) 要素で `Book` 型の `Dynamic` ポリシーを定義する。</span><span class="sxs-lookup"><span data-stu-id="607a2-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="607a2-160">次の default.rd.xml ファイルのように、呼び出す getter を持つ各プロパティに入れ子になった [\<Property>](property-element-net-native.md) 要素を追加する。</span><span class="sxs-lookup"><span data-stu-id="607a2-160">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="607a2-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="607a2-161">See also</span></span>

- [<span data-ttu-id="607a2-162">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="607a2-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="607a2-163">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="607a2-163">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="607a2-164">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="607a2-164">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
