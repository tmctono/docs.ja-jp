---
title: <MethodInstantiation>要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2c0354853e4725ba3e673fb9142c4a7a85d2121
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049620"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="a5efa-102">\<MethodInstantiation 化 > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="a5efa-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="a5efa-103">構築されたジェネリック メソッドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5efa-104">構文</span><span class="sxs-lookup"><span data-stu-id="a5efa-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5efa-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a5efa-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5efa-107">属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-107">Attributes</span></span>  
  
|<span data-ttu-id="a5efa-108">属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-108">Attribute</span></span>|<span data-ttu-id="a5efa-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="a5efa-109">Attribute type</span></span>|<span data-ttu-id="a5efa-110">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="a5efa-111">全般</span><span class="sxs-lookup"><span data-stu-id="a5efa-111">General</span></span>|<span data-ttu-id="a5efa-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-112">Required attribute.</span></span> <span data-ttu-id="a5efa-113">メソッド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="a5efa-114">全般</span><span class="sxs-lookup"><span data-stu-id="a5efa-114">General</span></span>|<span data-ttu-id="a5efa-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-115">Optional attribute.</span></span> <span data-ttu-id="a5efa-116">メソッドの名前付きパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="a5efa-117">複数の名前付きパラメーターはコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="a5efa-118">`Signature` 属性は、オーバー ロードされたメソッドを区別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="a5efa-119">全般</span><span class="sxs-lookup"><span data-stu-id="a5efa-119">General</span></span>|<span data-ttu-id="a5efa-120">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-120">Required attribute.</span></span> <span data-ttu-id="a5efa-121">ジェネリック型引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="a5efa-122">複数の引数が存在する場合は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="a5efa-123">リフレクション</span><span class="sxs-lookup"><span data-stu-id="a5efa-123">Reflection</span></span>|<span data-ttu-id="a5efa-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-124">Optional attribute.</span></span> <span data-ttu-id="a5efa-125">メソッドに関する情報の照会やメソッドの列挙を制御しますが、実行時の動的呼び出しは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="a5efa-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="a5efa-126">リフレクション</span><span class="sxs-lookup"><span data-stu-id="a5efa-126">Reflection</span></span>|<span data-ttu-id="a5efa-127">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-127">Optional attribute.</span></span> <span data-ttu-id="a5efa-128">コンストラクターまたはメソッドへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5efa-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="a5efa-129">このポリシーにより、実行時にメンバーを動的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="a5efa-130">Name 属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-130">Name attribute</span></span>  
  
|<span data-ttu-id="a5efa-131">値</span><span class="sxs-lookup"><span data-stu-id="a5efa-131">Value</span></span>|<span data-ttu-id="a5efa-132">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5efa-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="a5efa-133">*method_name*</span></span>|<span data-ttu-id="a5efa-134">メソッド名。</span><span class="sxs-lookup"><span data-stu-id="a5efa-134">The method name.</span></span> <span data-ttu-id="a5efa-135">メソッドの型は、親の [\<Type>](type-element-net-native.md) 要素または [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素により定義されます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="a5efa-136">シグネチャ属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-136">Signature attribute</span></span>  
  
|<span data-ttu-id="a5efa-137">値</span><span class="sxs-lookup"><span data-stu-id="a5efa-137">Value</span></span>|<span data-ttu-id="a5efa-138">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5efa-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="a5efa-139">*method_signature*</span></span>|<span data-ttu-id="a5efa-140">メソッドの名前付きパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="a5efa-141">複数のパラメーターが存在する場合はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="a5efa-142">引数属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="a5efa-143">値</span><span class="sxs-lookup"><span data-stu-id="a5efa-143">Value</span></span>|<span data-ttu-id="a5efa-144">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5efa-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="a5efa-145">*method_arguments*</span></span>|<span data-ttu-id="a5efa-146">ジェネリック型引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="a5efa-147">複数の引数が存在する場合は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a5efa-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="a5efa-148">各引数は、完全修飾型名で構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5efa-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="a5efa-149">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="a5efa-149">All other attributes</span></span>  
  
|<span data-ttu-id="a5efa-150">値</span><span class="sxs-lookup"><span data-stu-id="a5efa-150">Value</span></span>|<span data-ttu-id="a5efa-151">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5efa-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="a5efa-152">*policy_setting*</span></span>|<span data-ttu-id="a5efa-153">メソッドのこのポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="a5efa-154">指定できる値は、`Auto`、`Excluded`、`Included`、および `Required` です。</span><span class="sxs-lookup"><span data-stu-id="a5efa-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="a5efa-155">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5efa-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5efa-156">子要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-156">Child Elements</span></span>  
 <span data-ttu-id="a5efa-157">なし。</span><span class="sxs-lookup"><span data-stu-id="a5efa-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5efa-158">親要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-158">Parent Elements</span></span>  
  
|<span data-ttu-id="a5efa-159">要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-159">Element</span></span>|<span data-ttu-id="a5efa-160">説明</span><span class="sxs-lookup"><span data-stu-id="a5efa-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5efa-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="a5efa-161">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="a5efa-162">型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="a5efa-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="a5efa-163">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="a5efa-164">構築されたジェネリック型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5efa-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5efa-165">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5efa-165">Remarks</span></span>  
 <span data-ttu-id="a5efa-166">`<MethodInstantiation>` 要素は、対応するオープン ジェネリック メソッドのランタイム リフレクション ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a5efa-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5efa-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5efa-167">See also</span></span>

- [<span data-ttu-id="a5efa-168">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="a5efa-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="a5efa-169">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="a5efa-170">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="a5efa-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="a5efa-171">\<Method> 要素</span><span class="sxs-lookup"><span data-stu-id="a5efa-171">\<Method> Element</span></span>](method-element-net-native.md)
