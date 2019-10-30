---
title: <Field> 要素 (.NET ネイティブ)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 2a63b88c399a999cd00750dee1614352cea10e80
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128415"
---
# <a name="field-element-net-native"></a><span data-ttu-id="853d6-102">\<Field > 要素 (.NET ネイティブ)</span><span class="sxs-lookup"><span data-stu-id="853d6-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="853d6-103">フィールドにランタイム リフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="853d6-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="853d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="853d6-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="853d6-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="853d6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="853d6-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="853d6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="853d6-107">属性</span><span class="sxs-lookup"><span data-stu-id="853d6-107">Attributes</span></span>  
  
|<span data-ttu-id="853d6-108">属性</span><span class="sxs-lookup"><span data-stu-id="853d6-108">Attribute</span></span>|<span data-ttu-id="853d6-109">属性の型</span><span class="sxs-lookup"><span data-stu-id="853d6-109">Attribute type</span></span>|<span data-ttu-id="853d6-110">説明</span><span class="sxs-lookup"><span data-stu-id="853d6-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="853d6-111">全般</span><span class="sxs-lookup"><span data-stu-id="853d6-111">General</span></span>|<span data-ttu-id="853d6-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="853d6-112">Required attribute.</span></span> <span data-ttu-id="853d6-113">フィールド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="853d6-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="853d6-114">リフレクション</span><span class="sxs-lookup"><span data-stu-id="853d6-114">Reflection</span></span>|<span data-ttu-id="853d6-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="853d6-115">Optional attribute.</span></span> <span data-ttu-id="853d6-116">フィールドに関する情報の照会やフィールドの列挙を制御しますが、実行時の動的アクセスは有効にしません。</span><span class="sxs-lookup"><span data-stu-id="853d6-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="853d6-117">リフレクション</span><span class="sxs-lookup"><span data-stu-id="853d6-117">Reflection</span></span>|<span data-ttu-id="853d6-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="853d6-118">Optional attribute.</span></span> <span data-ttu-id="853d6-119">フィールドへの実行時アクセスを制御して、動的プログラミングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="853d6-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="853d6-120">このポリシーにより、実行時にフィールドを動的に設定または取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="853d6-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="853d6-121">シリアル化</span><span class="sxs-lookup"><span data-stu-id="853d6-121">Serialization</span></span>|<span data-ttu-id="853d6-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="853d6-122">Optional attribute.</span></span> <span data-ttu-id="853d6-123">フィールドへの実行時アクセスを制御して、型インスタンスを Newtonsoft の JSON シリアライザーなどのライブラリによってシリアル化できるようにしたり、データ バインディングで使用できるようにしたりします。</span><span class="sxs-lookup"><span data-stu-id="853d6-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="853d6-124">Name 属性</span><span class="sxs-lookup"><span data-stu-id="853d6-124">Name attribute</span></span>  
  
|<span data-ttu-id="853d6-125">[値]</span><span class="sxs-lookup"><span data-stu-id="853d6-125">Value</span></span>|<span data-ttu-id="853d6-126">説明</span><span class="sxs-lookup"><span data-stu-id="853d6-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="853d6-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="853d6-127">*method_name*</span></span>|<span data-ttu-id="853d6-128">フィールド名。</span><span class="sxs-lookup"><span data-stu-id="853d6-128">The field name.</span></span> <span data-ttu-id="853d6-129">フィールドの種類は、親 [\<Type>](type-element-net-native.md) または [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="853d6-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="853d6-130">その他すべての属性</span><span class="sxs-lookup"><span data-stu-id="853d6-130">All other attributes</span></span>  
  
|<span data-ttu-id="853d6-131">[値]</span><span class="sxs-lookup"><span data-stu-id="853d6-131">Value</span></span>|<span data-ttu-id="853d6-132">説明</span><span class="sxs-lookup"><span data-stu-id="853d6-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="853d6-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="853d6-133">*policy_setting*</span></span>|<span data-ttu-id="853d6-134">フィールドのこのポリシーの種類に適用する設定です。</span><span class="sxs-lookup"><span data-stu-id="853d6-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="853d6-135">指定できる値は、`Auto`、`Excluded`、`Included`、および `Required` です。</span><span class="sxs-lookup"><span data-stu-id="853d6-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="853d6-136">詳細については、「[ランタイム ディレクティブのポリシー設定](runtime-directive-policy-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="853d6-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="853d6-137">子要素</span><span class="sxs-lookup"><span data-stu-id="853d6-137">Child Elements</span></span>  
 <span data-ttu-id="853d6-138">なし。</span><span class="sxs-lookup"><span data-stu-id="853d6-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="853d6-139">親要素</span><span class="sxs-lookup"><span data-stu-id="853d6-139">Parent Elements</span></span>  
  
|<span data-ttu-id="853d6-140">要素</span><span class="sxs-lookup"><span data-stu-id="853d6-140">Element</span></span>|<span data-ttu-id="853d6-141">説明</span><span class="sxs-lookup"><span data-stu-id="853d6-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="853d6-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="853d6-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="853d6-143">型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="853d6-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="853d6-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="853d6-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="853d6-145">構築されたジェネリック型とそのすべてのメンバーにリフレクション ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="853d6-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="853d6-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="853d6-146">Remarks</span></span>  
 <span data-ttu-id="853d6-147">フィールドのポリシーが明示的に定義されていない場合は、その親要素の実行時ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="853d6-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853d6-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="853d6-148">See also</span></span>

- [<span data-ttu-id="853d6-149">ランタイム ディレクティブ要素</span><span class="sxs-lookup"><span data-stu-id="853d6-149">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="853d6-150">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="853d6-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="853d6-151">ランタイム ディレクティブ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="853d6-151">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
